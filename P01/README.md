# 📑 P01: Producte Final – Memòria Tècnica de la Proposta

## 📖 Breu descripció

Tal com s'indica a la descripció del projecte, el repte no consisteix únicament a instal·lar serveis com Apache, Nginx, Moodle o Canvas LMS.

L'objectiu real és desenvolupar una proposta professional que permeti:

* 🎯 Entendre les necessitats del client.
* 🔍 Analitzar diferents alternatives tecnològiques.
* 💰 Estimar costos i recursos.
* 🌱 Incorporar criteris de sostenibilitat.
* 📈 Valorar la viabilitat del projecte.
* 🏢 Presentar una solució realista i professional.

La memòria tècnica simula el document que una empresa tecnològica entregaria a un client després d'analitzar els seus requeriments.

---

# 🎯 Objectiu principal

Demostrar la capacitat de passar de:

> "Configurar un servidor per practicar"

a

> "Dissenyar una solució tecnològica real per donar servei a una organització"

Aquesta memòria justificarà formalment l'assoliment de la competència:

> **"Planteja solucions a les necessitats del sector tenint en compte la seva viabilitat, els costos associats i elaborant un petit projecte."**

---

# 🏗️ Estructura de la Memòria Tècnica

La memòria haurà d'integrar tots els treballs desenvolupats durant el projecte.

---

# 1️⃣ Introducció

## Context del projecte

Presentació general del client i de la necessitat detectada.

### Aspectes a explicar

* Qui és el client.
* Quin problema necessita resoldre.
* Per què necessita una plataforma LMS.
* Objectius del projecte.

---

# 2️⃣ Anàlisi de necessitats

## Necessitats detectades

L'organització necessita:

* Formació online centralitzada.
* Gestió d'usuaris.
* Creació de cursos.
* Sistema d'avaluació.
* Escalabilitat futura.
* Entorn professional.
* Compliment normatiu europeu.

---

# 3️⃣ Comparativa tecnològica Apache vs Nginx

## Apache

### Avantatges

* Gran compatibilitat.
* Configuració molt flexible.
* Àmplia documentació.

### Inconvenients

* Major consum de recursos.
* Menor rendiment amb càrregues elevades.

---

## Nginx

### Avantatges

* Alt rendiment.
* Baix consum de memòria.
* Gran capacitat de concurrència.

### Inconvenients

* Configuracions inicials més complexes.
* Menys flexibilitat en alguns escenaris.

---

## Conclusió

Per a una plataforma LMS moderna amb múltiples usuaris simultanis es recomana:

🏆 **Nginx**

Motiu principal:

* Millor eficiència.
* Menor consum de recursos.
* Escalabilitat superior.

---

# 4️⃣ Comparativa Moodle vs Canvas LMS

## Moodle

### Punts forts

* Extremadament flexible.
* Gran ecosistema de plugins.
* Sistema d'avaluació molt avançat.
* Comunitat educativa molt extensa.

### Punts febles

* Interfície menys moderna.
* Corba d'aprenentatge superior.

---

## Canvas LMS

### Punts forts

* Interfície moderna.
* Experiència d'usuari molt intuïtiva.
* Configuració més senzilla.

### Punts febles

* Menor capacitat de personalització.
* Menys extensible que Moodle.

---

## Solució seleccionada

🏆 **Moodle**

### Justificació

* Major flexibilitat.
* Adaptació a necessitats educatives diverses.
* Possibilitat de creixement futur.
* Millor ecosistema de complements.

---

# 5️⃣ Estudi de sostenibilitat

## Green IT aplicat al projecte

La proposta incorpora mesures específiques de sostenibilitat.

### Accions implementades

#### ☁️ Virtualització

Reducció de maquinari físic.

#### ⚡ Infraestructura eficient

Optimització del consum energètic.

#### 💻 Desenvolupament sostenible

Optimització dels recursos de la plataforma.

#### ♻️ Allargament del cicle de vida

Reutilització i manteniment dels equips.

---

## Beneficis

* Menor consum energètic.
* Reducció d'emissions.
* Menors costos operatius.
* Major eficiència tecnològica.

---

# 6️⃣ Proposta tècnica final

## Solució recomanada

### Plataforma LMS

🏆 Moodle

### Servidor Web

🏆 Nginx

### Sistema Operatiu

🐧 Ubuntu Server LTS

### Base de dades

🗄️ MariaDB

### Seguretat

* HTTPS.
* Firewall.
* Còpies de seguretat automàtiques.

---

# 7️⃣ Requisits del VPS

Per garantir un funcionament correcte de Moodle es defineixen els següents requisits mínims:

| Component        | Requisit                |
| ---------------- | ----------------------- |
| CPU              | 4 vCPU                  |
| RAM              | 8 GB                    |
| Emmagatzematge   | 160 GB NVMe             |
| Sistema Operatiu | Ubuntu Server 24.04 LTS |
| Xarxa            | 1 Gbps                  |
| Ubicació         | Unió Europea            |
| Backup           | Recomanat               |

---

# 8️⃣ Estudi de mercat VPS

## Opció 1: OVHcloud

[OVHcloud](https://www.ovhcloud.com/es-es/vps/configurator/?utm_source=chatgpt.com)

### Característiques

* 6 vCore
* 12 GB RAM
* 100 GB NVMe

### Cost

💰 Aproximadament 8,49 €/mes + IVA.

### Avantatges

* Infraestructura europea.
* Protecció Anti-DDoS.
* Centres de dades a la UE.

---

## Opció 2: IONOS VPS L+

[IONOS VPS Cloud](https://www.ionos.es/servidores/cloud-vps?utm_source=chatgpt.com)

### Característiques

* 6 vCore
* 8 GB RAM
* 240 GB NVMe

### Cost

💰 Aproximadament 5 €/mes durant promoció.

### Avantatges

* Datacenters europeus.
* Compliment RGPD.
* Cost molt competitiu.

---

## Opció 3: Hetzner Cloud CX32

### Característiques

* 4 vCPU
* 8 GB RAM
* 80 GB NVMe

### Cost

💰 Aproximadament 7,59 €/mes.

### Avantatges

* Excel·lent relació qualitat-preu.
* Infraestructura alemanya.
* Gran rendiment.

---

## Opció 4: Scaleway

### Característiques

* Infraestructura cloud europea.
* Datacenters a França i Països Baixos.

### Avantatges

* Empresa europea.
* Plataforma moderna.
* Bona integració cloud.

---

# 🏆 VPS seleccionat

## IONOS VPS L+

### Motius de la selecció

✅ Compliment RGPD.

✅ Centres de dades europeus.

✅ Recursos suficients per Moodle.

✅ Cost reduït.

✅ Emmagatzematge NVMe ampli.

✅ Escalabilitat futura.

Segons les especificacions publicades per IONOS, el pla VPS L+ ofereix 6 vCores, 8 GB de RAM i 240 GB NVMe, complint els requisits previstos per al desplegament de Moodle.

---

# 💰 Estimació econòmica

| Element              | Cost mensual            |
| -------------------- | ----------------------- |
| VPS IONOS            | 5 €                     |
| Domini web           | 1 €                     |
| Backups              | Inclòs                  |
| Certificat SSL       | Gratuït (Let's Encrypt) |
| Cost total aproximat | 6 €/mes                 |

---

# 📈 Viabilitat del projecte

## Viabilitat tècnica

✅ Solució provada.

✅ Tecnologies madures.

✅ Escalable.

---

## Viabilitat econòmica

✅ Cost d'infraestructura molt reduït.

✅ Possibilitat de creixement progressiu.

✅ Inversió inicial baixa.

---

## Viabilitat sostenible

✅ Consum energètic optimitzat.

✅ Ús de virtualització.

✅ Reducció de recursos físics.

---

# 🎯 Conclusions finals

Després d'analitzar les alternatives tecnològiques, els costos i la sostenibilitat de la infraestructura, es proposa una solució basada en:

* 🏆 Moodle LMS
* 🏆 Nginx
* 🏆 Ubuntu Server
* 🏆 VPS IONOS ubicat a la Unió Europea

Aquesta proposta ofereix una combinació equilibrada de:

* Rendiment.
* Cost.
* Escalabilitat.
* Sostenibilitat.
* Facilitat de manteniment.

La solució permet cobrir les necessitats actuals del client i proporciona una base sòlida per a futures ampliacions del servei formatiu digital. 🚀🌱

