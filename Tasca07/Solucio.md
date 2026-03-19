## Guia d'implementació T07 - TransLògic S.A.

### 1. Revisió de l’estructura d’OUs
Abans de començar, vam revisar les OUs per tenir-ho tot ben endreçat. Vam crear OUs per departaments (gerencia, gestio, magatzem) i per equips, per poder aplicar polítiques específiques després. Això ens facilitarà la feina amb les GPO.

![Revisió estructura OUs](/Tasca07/IMG/1.png)

---

### 2. Polítiques de contrasenyes

#### 2.1 Política global (Default Domain Policy)
Vam modificar la política per defecte del domini perquè tots els usuaris tinguin una contrasenya mínima de 8 caràcters. Això ho fem des de l'editor de GPO, a `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy`.

![Editar Default Domain Policy](/Tasca07/IMG/1.png)
![Canvi longitud mínima a 8](/Tasca07/IMG/2.png)
![Confirmació 8 caràcters](/Tasca07/IMG/3.png)
![Vista general política contrasenyes](/Tasca07/IMG/5.png)

#### 2.2 Política per a Gerència (VIP)
Vam crear una GPO específica per a l'OU `gerencia`. Els directius han de tenir contrasenya de 18 caràcters i que caduqui cada 28 dies. La complexitat no l'activem perquè no volen massa lios.

![Ubicació OU gerencia](/Tasca07/IMG/4.png)
![Configuració mínim 18 caràcters](/Tasca07/IMG/7.png)
![Configuració caducitat 28 dies](/Tasca07/IMG/8.png)
![Assegurar que complexitat està desactivada](/Tasca07/IMG/6.png)

#### 2.3 GPO de millora (bonus)
Per als usuaris de magatzem vam implementar una política de bloqueig de pantalla automàtic als 5 minuts d'inactivitat. Això evita que si un treballador deixa l'ordinador sense vigilància, algú no autoritzat hi pugui accedir. És una mesura de seguretat molt pràctica per a una empresa logística.


---

### 3. Desplegament de programari

#### 3.1 Compartir la carpeta de recursos
Primer vam compartir la carpeta `soft` al servidor amb els fitxers `.msi` del 7zip i Firefox.

![Carpeta soft amb els MSI](/Tasca07/IMG/10.png)
![Compartir carpeta soft](/Tasca07/IMG/11.png)
![Permisos de la carpeta compartida](/Tasca07/IMG/12.png)

#### 3.2 GPO per a 7zip (assignat - gestio)
Vam crear una GPO per a l'OU `gestio` que instal·la el 7zip de manera automàtica. Així els administratius el tenen sempre sense fer res.

![Crear paquet d'instal·lació 7zip](/Tasca07/IMG/13.png)
![Paquet 7zip assignat](/Tasca07/IMG/14.png)

#### 3.3 GPO per a Firefox (publicat - gerencia)
Per als directius vam publicar el Firefox. D'aquesta manera ells decideixen si l'instal·len des del Panell de Control.

![Paquet Firefox publicat](/Tasca07/IMG/15.png)

#### 3.4 Resposta consultoria: com crear un .msi
Si una aplicació només té un `.exe`, podem crear un paquet `.msi` amb eines com **Advanced Installer**, **EMCO MSI Package Builder** o **WinINSTALL**. Bàsicament el que fan és capturar els canvis al sistema durant la instal·lació del `.exe` i generar un `.msi` personalitzat per desplegar-lo després amb GPO.

---

### 4. Perfils mòbils per a gestió

#### 4.1 Crear i compartir la carpeta `perfils`
Vam crear una carpeta `perfils` al servidor i la vam compartir per guardar-hi els perfils dels usuaris.


#### 4.2 Configurar la plantilla de l'usuari
Vam agafar un usuari plantilla del grup `gestio` i li vam assignar la ruta del perfil mòbil: `\\DC13\perfis\template_gestio`.

![Configuració perfil mòbil](/Tasca07/IMG/16.png)

#### 4.3 Crear usuari de prova i comprovar
Vam crear l'usuari `pro_gestio` i vam iniciar sessió amb ell. Automàticament se li va crear la carpeta del perfil al servidor.

![Creació usuari pro_gestio](/Tasca07/IMG/17.png)
![Inici de sessió de pro_gestio](/Tasca07/IMG/18.png)
![Carpeta del perfil creada al servidor](/Tasca07/IMG/19.png)

---

### 5. Redirecció de carpetes (Documents)

#### 5.1 Configurar la GPO de redirecció
Vam crear una GPO a nivell de domini per redirigir la carpeta `Documents` de cada usuari a la seva carpeta personal de xarxa (`\\DC13\perfils\%username%\Documents`).

![Opció de redirecció de carpetes](/Tasca07/IMG/20.png)
![Configuració redirecció a ruta de xarxa](/Tasca07/IMG/21.png)

#### 5.2 Comprovació
Des d'un client vam desar un fitxer de prova a "Documents". Després vam comprovar al servidor que el fitxer hi era.

![Fitxer de prova creat al client](/Tasca07/IMG/22.png)
![Fitxer de prova visible al servidor](/Tasca07/IMG/23.png)

---

### 6. Delegació de control per a l'ajudant (adminOU)

#### 6.1 Crear l'usuari adminOU
Vam crear l'usuari `adminOU` dins l'OU `Users`. Aquest serà l'auxiliar de suport.

![Creació usuari adminOU](/Tasca07/IMG/24.png)
![Usuari adminOU a la llista](/Tasca07/IMG/25.png)

#### 6.2 Delegar permisos sobre l'OU principal
Vam delegar el control de l'OU `translogic13.test` a l'usuari `adminOU`. Li vam donar permisos només per reiniciar contrasenyes i modificar grups. Res de crear usuaris.

![Inici assistent delegació](/Tasca07/IMG/26.png)
![Selecció de tasques delegades](/Tasca07/IMG/27.png)

---

### 0. Instal·lació de les eines RSAT

Abans de començar a tocar res, necessitem instal·lar les eines d'administració remota (RSAT) per poder gestionar l'Active Directory. Això ho fem des de l'Administrador del servidor, afegint la característica **"Herramientas de Active Directory Domain Services y Lightweight Directory Services"**.

veiem que hem seleccionat aquesta opció dins de l'apartat de característiques disponibles. Fixa't que a baix a la dreta diu "Agregar (2)" perquè segurament hem marcat també alguna eina addicional relacionada.

![Selecció de les eines RSAT per Active Directory](/Tasca07/IMG/28.png)

es confirma que estem afegint aquestes característiques al sistema abans de procedir amb la instal·lació.

![Confirmació d'afegir les característiques seleccionades](/Tasca07/IMG/29.png)

Un cop instal·lat això, ja tindrem accés a totes les consoles de gestió (Usuaris i equips, GPO, etc.) i podrem començar amb la revisió d'OUs i la creació de polítiques.

---

#### 6.3 Comprovació
Amb l'usuari `adminOU` vam intentar canviar la contrasenya d'un altre usuari i va funcionar. En canvi, a l'hora de crear un usuari nou, l'opció estava deshabilitada o donava error. Així confirmem que la delegació està ben feta.

