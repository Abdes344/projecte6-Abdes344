# Guia de PKI i Signatura Digital – Nexus (versió resumida)
## Abdeslam Khfif

Al servidor Windows Server 2025 vam instal·lar el rol **AD CS** i el vam configurar com a **Enterprise Root CA**. També vam habilitar el portal web perquè els clients puguin descarregar els certificats (`http://192.168.2.8/certsrv`).

El client (Windows) té una IP estàtica per connectar-se al servidor:

![IPs servidor i client](/Tasca06/IMG2/1.png)  
– Taula amb IPs: servidor 192.168.2.8, client 192.168.2.13.

![Configuració IP client](/Tasca06/IMG2/2.png)  
 – IP estàtica posada a mà perquè sempre es connecti al servidor correcte.

---

Ara des del client baixem els certificats que necessitem.

 Descarregar certificats des del portal
Accedim al portal web i descarreguem dos fitxers:
- **Certificat arrel (CA)**: el necessitem perquè el sistema confiï en els certificats que emet la nostra CA.
- **Certificat personal (.pfx)**: conté la clau privada i el certificat del treballador.

![Portal de certificats](/Tasca06/IMG2/3.png)  
– Portal web amb els enllaços de descàrrega.

Un cop descarregats, els fitxers queden a la carpeta Descargas:

![Fitxers descarregats](/Tasca06/IMG2/4.png)  
cacert.pem (certificat arrel) i CertUser (certificat personal).

---

Per poder signar PDFs necessitem un programa que ho suporti. Instal·lem l’Acrobat Reader amb winget:


![Instal·lació amb winget](/Tasca06/IMG2/5.png)  
 – Cerca i instal·lació des de la línia de comandes.

![Instal·lador Acrobat](/Tasca06/IMG2/6.png)  
– Un cop descarregat, l’instal·lador s’executa automàticament.

---


Obrim certmgr.msc (administrador de certificats) i anem a **Entidades de certificación raíz de confianza**. Aquí importem el cacert.pem perquè Windows confiï en la nostra CA.

![Certmgr arrel](/Tasca06/IMG2/7.png)  
 – Seleccionem la carpeta on anem a importar.

![Importar arrel](/Tasca06/IMG2/8.png)  
 – Triem el fitxer cacert.pem.

Després de la importació, comprovem que apareix a la llista:

![Arrel instal·lada](/Tasca06/IMG2/9.png)  
 – El certificat ca.nexus7.test ja és una arrel de confiança.

---


Ara importem el certificat del treballador (amb la seva clau privada) a la carpeta **Personal**. Aquest serà el que utilitzarem per signar.

![Personal buit](/Tasca06/IMG2/10.png)  
 – Abans d’importar, la carpeta Personal està buida.

Un cop importat el CertUser.pfx (si té contrasenya, la demana), veiem el certificat instal·lat:

![Certificat personal instal·lat](/Tasca06/IMG2/12.png)  
 – Apareix el certificat ca.nexus7.test a la secció de certificats personals.

---

Obrim el document PDF amb l’Adobe Acrobat Reader (clic dret → «Abrir con» → Adobe Acrobat).

![Obrir PDF amb Acrobat](/Tasca06/IMG2/13.png)  
 – Seleccionem Acrobat per obrir el fitxer.

Dins l’Acrobat, anem a **Eines → Certificats → Signar digitalment**. Escollim el certificat que acabem d’instal·lar:

![Seleccionar certificat](/Tasca06/IMG2/14.png)  
 – Apareix el nostre certificat ca.nexus7.test.

Configurem l’aparença de la signatura (text o imatge) i la posem al document:

![Aparença signatura](/Tasca06/IMG2/15.png)  
– Escollim l’aspecte i veiem la data/hora.

Un cop signat, el document mostra la marca de signatura:

![Document signat](/Tasca06/IMG2/16.png)  
 – La signatura apareix amb el nom ca.nexus7.test.

---

L’Acrobat verifica automàticament la signatura. Si tot és correcte, es veu un missatge verd:

![Verificació correcta](/Tasca06/IMG2/17.png)  
 – El panell indica que la signatura és **vàlida** i l’identitat del firmant, també.

---
