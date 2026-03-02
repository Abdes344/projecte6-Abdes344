# Migració a Nginx: Escalabilitat i Alt Rendiment 🚀⚡

## Introducció

La vostra implementació amb Apache ha estat un èxit i el client està satisfet. No obstant això, a la reunió d'estratègia tècnica d'ahir, la directiva va plantejar un nou repte: **l'escalabilitat**.  

Es preveu que Projecte Nexus rebi un pic de visites molt elevat durant la propera campanya de presentació. 📈  

Per aquest motiu, hem decidit obrir una línia de **recerca i desenvolupament (R+D)** per provar **Nginx**. Aquest servidor és conegut per la seva arquitectura orientada a esdeveniments, capaç de gestionar milers de connexions concurrents amb un consum de memòria molt inferior. 🖥️  

L'objectiu d'aquesta activitat és **replicar exactament la infraestructura** que vam muntar amb Apache, però utilitzant Nginx. Això ens permetrà comparar rendiment i tenir una alternativa d'altes prestacions al nostre catàleg de serveis.  

> ⚠️ **Nota important:** Recordeu que dos serveis no poden escoltar pel mateix port (80/443) simultàniament a la mateixa IP. Haureu d'aturar Apache abans de començar.

---

# 📋 Descripció de l'activitat

L'activitat consisteix en la **migració de la infraestructura web a un entorn Nginx sobre Ubuntu Server**.  

Heu de documentar tot el procés en l'informe tècnic. 📝  

---

# 🛠️ Tasques a Realitzar

## 1️⃣ Preparació de l'Entorn i Instal·lació

- Atureu i deshabiliteu el servei `apache2` per alliberar els ports 80 i 443.
- Instal·leu el servidor web **Nginx**.
- Verifiqueu que el servei està actiu.
- Comproveu que la pàgina de benvinguda de Nginx es mostra correctament al navegador. 🌐  

---

## 2️⃣ Configuració de Server Blocks (Multidomini)

- Aprofiteu l'estructura de carpetes ja creada:
  - `/var/www/nexus`
  - `/var/www/academia`

- Si cal, ajusteu els permisos (propietari `www-data`).
- Configureu dos **Server Blocks** (l'equivalent a VirtualHosts a Nginx) a:
