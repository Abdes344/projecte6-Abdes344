# 🎤 P02: Presentació de la Proposta al Client

## 📖 Introducció

Heu arribat a l'etapa final del projecte.

Durant les darreres setmanes heu treballat en el disseny, desplegament, configuració i documentació de la infraestructura tecnològica per a **Nexus e-learning**.

Heu instal·lat servidors, configurat serveis web, desplegat plataformes LMS i analitzat diferents alternatives tecnològiques.

Ara arriba el moment més important:

> Convèncer el client que la vostra proposta és la millor opció. 🚀

Davant vostre no tindreu professors, sinó la direcció de **Nexus e-learning** (CEO i CTO), que haurà de decidir si aprova la vostra proposta o si selecciona una alternativa de la competència.

L'objectiu no és explicar tecnologia.

L'objectiu és demostrar que la vostra solució és:

* ⚡ Eficient
* 🔒 Segura
* 📈 Escalable
* 💰 Rendible
* 🌱 Sostenible

---

# 🎯 Objectius de la presentació

Durant aquesta activitat haureu de demostrar que sou capaços de:

* Sintetitzar informació tècnica complexa.
* Defensar decisions tecnològiques.
* Justificar una proposta amb criteris professionals.
* Comunicar-vos amb un client no tècnic.
* Presentar una solució viable i realista.

---

# ⏱️ Format de la presentació

## Durada

### Exposició

**12 minuts**

### Torn de preguntes

**5 minuts**

---

## Suport visual

Podeu utilitzar:

* PowerPoint
* Google Slides
* Canva
* PDF interactiu

### Recomanacions

✅ Diapositives netes.

✅ Poc text.

✅ Gràfics i esquemes.

✅ Diagrames de xarxa propis.

❌ No llegir les diapositives.

---

## Codi de vestimenta

### Casual Professional 👔

Exemples:

* Camisa o polo.
* Pantalons adequats.
* Calçat correcte.

Eviteu:

* Roba esportiva.
* Samarretes informals.
* Aspecte descuidat.

Penseu que és una reunió amb un client real.

---

# 🏢 1. Context i necessitats del client

## Qui és Nexus e-learning?

Empresa dedicada a la formació online.

Necessita una plataforma moderna per oferir cursos i gestionar alumnes.

---

## Necessitats detectades

### ⚡ Rendiment

La plataforma ha de suportar múltiples usuaris simultanis.

### 💰 Cost controlat

Infraestructura eficient i assumible.

### 🌱 Sostenibilitat

Reduir consum energètic i recursos.

### 🔧 Facilitat de manteniment

Sistema fàcil d'administrar.

---

# 🌐 2. T04 — Duel de Titans: Apache vs Nginx

## 2.1 Comparativa tècnica

### Apache

#### Avantatges

* Molta documentació.
* Gran compatibilitat.
* Configuració flexible.

#### Inconvenients

* Major consum de recursos.
* Menor rendiment en alta concurrència.

---

### Nginx

#### Avantatges

* Alt rendiment.
* Menor consum de RAM.
* Millor escalabilitat.

#### Inconvenients

* Configuració inicial més complexa.

---

## 2.2 Experiència real (Obligatori)

Expliqueu:

### Apache

* Problemes trobats.
* Errors de configuració.
* Dificultats reals.

### Nginx

* Facilitat o dificultat d'ús.
* Problemes resolts.
* Experiència pràctica.

---

## 2.3 Mètriques

Exemples:

| Aspecte            | Apache   | Nginx        |
| ------------------ | -------- | ------------ |
| Temps instal·lació | X min    | X min        |
| Consum RAM         | Mitjà    | Baix         |
| Configuració       | Flexible | Estructurada |
| Escalabilitat      | Bona     | Molt bona    |

---

## 2.4 Decisió final

### 🏆 Servidor escollit: Nginx

### Justificació

* Millor rendiment.
* Menor consum de recursos.
* Escalabilitat superior.
* Adequat per a una acadèmia online.

---

# 🎓 3. T11 — Moodle vs Canvas LMS

## 3.1 Comparativa funcional

### Moodle

#### Avantatges

* Molt flexible.
* Gran ecosistema de plugins.
* Potent sistema d'avaluació.

#### Inconvenients

* Corba d'aprenentatge superior.
* Interfície menys moderna.

---

### Canvas

#### Avantatges

* Interfície moderna.
* Fàcil d'utilitzar.
* Experiència d'usuari excel·lent.

#### Inconvenients

* Menys personalització.
* Menys funcionalitats avançades.

---

## 3.2 Experiència real (Obligatori)

Expliqueu:

### Moodle

* Temps invertit.
* Dificultats trobades.
* Configuracions realitzades.

### Canvas

* Facilitat d'instal·lació.
* Gestió dels cursos.
* Sensacions durant el projecte.

---

## 3.3 Mètriques

Exemples:

| Aspecte         | Moodle    | Canvas   |
| --------------- | --------- | -------- |
| Instal·lació    | Mitjana   | Ràpida   |
| Crear curs      | Flexible  | Intuïtiu |
| Gestió usuaris  | Avançada  | Senzilla |
| Personalització | Molt alta | Mitjana  |

---

## 3.4 Decisió final

### 🏆 LMS escollit: Moodle

### Justificació

* Major flexibilitat.
* Escalabilitat futura.
* Millor adaptació a entorns educatius.
* Ecosistema de plugins molt ampli.

---

# 🔗 4. Integració de la solució

## Arquitectura final

### Servidor Web

🌐 Nginx

### LMS

🎓 Moodle

### Sistema Operatiu

🐧 Ubuntu Server LTS

### Base de dades

🗄️ MariaDB

### Seguretat

🔒 HTTPS + Firewall + Backups

---

## Beneficis de la integració

* Rendiment elevat.
* Cost reduït.
* Facilitat d'escalat.
* Manteniment senzill.

---

# 💰 5. Viabilitat tècnica i econòmica

## Infraestructura

### VPS seleccionat

Servidor virtual ubicat a la Unió Europea.

---

## Recursos

### Materials

* VPS.
* Domini.
* Certificat SSL.

### Humans

* Administrador de sistemes.
* Responsable acadèmic.

---

## Cost estimat

| Element | Cost mensual |
| ------- | ------------ |
| VPS     | 5 €          |
| Domini  | 1 €          |
| SSL     | Gratuït      |
| Total   | 6 €/mes      |

---

# 🌱 6. Qualitat, manteniment i sostenibilitat

## Qualitat

* Monitorització.
* Backups.
* Actualitzacions periòdiques.

---

## Manteniment

* Gestió remota.
* Actualitzacions programades.
* Revisió de seguretat.

---

## Green IT

### Mesures aplicades

* Virtualització.
* Infraestructura eficient.
* Reducció de recursos físics.
* Menor consum energètic.

### Beneficis

🌱 Menys impacte ambiental.

💰 Menys costos operatius.

⚡ Major eficiència.

---

# 🏆 7. Conclusions i proposta final

## Solució proposada

### Plataforma LMS

🎓 Moodle

### Servidor Web

🌐 Nginx

### Infraestructura

☁️ VPS europeu

---

## Per què és la millor opció?

✅ Rendiment elevat.

✅ Cost molt reduït.

✅ Escalable.

✅ Segura.

✅ Sostenible.

✅ Adaptada al creixement futur de Nexus e-learning.

---

# 🎤 Missatge final

> La nostra proposta no només resol les necessitats actuals de Nexus e-learning, sinó que proporciona una infraestructura sòlida, escalable i sostenible preparada per créixer amb el negoci.

Gràcies per la vostra atenció. 🙌

**Alguna pregunta?** ❓

