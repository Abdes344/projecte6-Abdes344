# ⚔️ T04: Duel de titans — Apache vs Nginx

## 📖 Breu descripció

En aquesta pràctica s’ha realitzat una comparativa entre dos servidors web àmpliament utilitzats en entorns professionals:

* 🌐 Apache HTTP Server
* 🚀 Nginx

L’objectiu és analitzar el seu comportament sota diferents càrregues mitjançant proves de rendiment (benchmarking) utilitzant l’eina `ab` (ApacheBench).

---

# 🧪 Objectiu de les proves

* Simular trànsit real d’usuaris.
* Mesurar rendiment sota càrrega lleugera i extrema.
* Detectar diferències en:

  * Velocitat de resposta
  * Capacitat de concurrència
  * Estabilitat del servidor
  * Gestió d’errors

---

# 🛠️ Eina utilitzada

* `apache2-utils` (ApacheBench)

Comandes utilitzades:

```bash
ab -n 1000 -c 10 http://IP_SERVIDOR/
ab -n 10000 -c 100 http://IP_SERVIDOR/
```

---

# 📊 Proves realitzades

## 🟢 1. Càrrega lleugera (1000 peticions / 10 usuaris)

| Mètrica                 | Apache | Nginx  |
| ----------------------- | ------ | ------ |
| Time taken for tests    | X s    | X s    |
| Transfer rate           | X KB/s | X KB/s |
| Requests per second     | X RPS  | X RPS  |
| Time per request (mean) | X ms   | X ms   |
| Completed requests      | X      | X      |
| Failed requests         | X      | X      |

---

## 🔴 2. Prova d’estrès (10.000 peticions / 100 usuaris)

| Mètrica                 | Apache | Nginx  |
| ----------------------- | ------ | ------ |
| Time taken for tests    | X s    | X s    |
| Transfer rate           | X KB/s | X KB/s |
| Requests per second     | X RPS  | X RPS  |
| Time per request (mean) | X ms   | X ms   |
| Completed requests      | X      | X      |
| Failed requests         | X      | X      |

---

# 📈 Anàlisi comparativa

## 🌐 Apache HTTP Server

* Arquitectura basada en processos.
* Rendiment correcte en càrrega baixa.
* Pot augmentar consum de recursos amb alta concurrència.
* Més flexible en configuració (mòduls).

👉 En proves d’estrès pot mostrar més latència o errors si no està optimitzat.

---

## 🚀 Nginx

* Arquitectura asíncrona i basada en esdeveniments.
* Millor rendiment sota alta concurrència.
* Consum de recursos més eficient.
* Resposta més estable en escenaris de càrrega alta.

👉 Ideal per entorns amb trànsit intens o escalar serveis web.

---

# ⚖️ Conclusions

Després de les proves:

* 🟢 En càrrega lleugera: diferències moderades.
* 🔴 En càrrega alta: Nginx mostra millor estabilitat i rendiment.
* 🧱 Apache HTTP Server és més flexible però menys eficient sota estrès.

---

# 🧠 Decisió tècnica (context Nexus)

Per a un entorn com Nexus (plataforma e-learning):

* Es prioritza:

  * Escalabilitat
  * Rendiment sota càrrega
  * Eficiència de recursos

👉 Recomanació tècnica: **Nginx com a servidor principal**

---

# 🏁 Valor afegit de la pràctica

Aquesta comparativa no només mostra configuració tècnica, sinó:

* Capacitat d’anàlisi de rendiment real
* Interpretació de mètriques
* Presa de decisions basada en dades
* Simulació d’escenaris reals de producció

