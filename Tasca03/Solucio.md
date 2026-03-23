#T03: Missió Nginx: Migració d'Alt Rendiment i Arquitectura Lleugera

Aquesta guia resumeix el procés de migració d’Apache a Nginx, centrant-nos en els resultats i les decisions preses. Es mostren captures de pantalla que evidencien cada pas.

---

## 1. Preparació i instal·lació

Abans d’instal·lar Nginx, vam assegurar-nos que Apache no utilitzés els ports 80 i 443.  
Vam aturar i deshabilitar Apache per alliberar-los.

 – Verificació que els ports estan lliures després d’aturar Apache:  
![Ports lliures](/Tasca03/IMG/2.png)

Després vam instal·lar Nginx. El paquet es va descarregar i configurar automàticament.

 – Instal·lació de Nginx:  
![Instal·lació Nginx](/Tasca03/IMG/1.png)

Un cop instal·lat, vam iniciar el servei i comprovar que estava actiu.

 – Estat actiu de Nginx:  
![Estat Nginx](/Tasca03/IMG/3.png)

---

## 2. Configuració de Server Blocks (multidomini)

Vam crear l’estructura de directoris per als dos dominis dins de `/var/www`.  
Vam assignar els permisos adequats perquè Nginx pogués llegir els fitxers.

– Creació de directoris:  
![Directoris creats](/Tasca03/IMG/4.png)

 – Permisos i propietat:  
![Permisos](/Tasca03/IMG/5.png)

A continuació, vam definir els Server Blocks en fitxers dins de `/etc/nginx/sites-available/`.  
Cadascun especifica el nom del domini, l’arrel de documents i la pàgina d’error personalitzada.

 – Fitxer de configuració per a *academia.test*:  
![Config academia](/Tasca03/IMG/7.png)

 – Fitxer per a *projectenexus.test*:  
![Config projecte](/Tasca03/IMG/8.png)

Vam activar les configuracions mitjançant enllaços simbòlics a `sites-enabled`.

 – Enllaços creats:  
![Enllaços simbòlics](/Tasca03/IMG/6.png)

Abans de reiniciar, vam verificar que la sintaxi fos correcta.

 – Verificació de la configuració:  
![nginx -t](/Tasca03/IMG/9.png)

---

## 3. Personalització d’errors (404)

Per mostrar una pàgina d’error pròpia, vam crear directoris específics per a cada domini i vam generar un fitxer `404.html`.

 – Directoris d’error:  
![Directoris error](/Tasca03/IMG/16.png)

 – Contingut del 404.html per a *projectenexus.test*:  
![404 projecte](/Tasca03/IMG/17.png)

 – Contingut per a *academia.test*:  
![404 academia](/Tasca03/IMG/18.png)

Vam ajustar els permisos perquè Nginx pogués servir aquests fitxers.

 – Permisos finals:  
![Permisos finals](/Tasca03/IMG/19.png)

---

## 4. Seguretat HTTPS (SSL/TLS)

Per assegurar les comunicacions, vam generar un certificat autosignat amb OpenSSL.

 – Generació del certificat:  
![Generació SSL](/Tasca03/IMG/21.png)

Després vam modificar els Server Blocks per afegir el bloc HTTPS i la redirecció de HTTP a HTTPS.

 – Configuració del bloc HTTPS (vista parcial):  
![Config HTTPS](/Tasca03/IMG/23.png)

Vam tornar a verificar la configuració i reiniciar Nginx.

– Verificació final:  
![Verificació final](/Tasca03/IMG/22.png)

També vam actualitzar el fitxer `/etc/hosts` per poder accedir als dominis des del navegador.

 – Fitxer hosts:  
![Hosts](/Tasca03/IMG/20.png)

---

## 5. Optimització amb HTTP/2

En el bloc `listen` de les configuracions HTTPS vam afegir el paràmetre `http2`. Això activa el protocol HTTP/2, que millora el rendiment.  
Per comprovar-ho, podem utilitzar les eines de desenvolupador del navegador: la columna Protocol mostrarà `h2`.

---
