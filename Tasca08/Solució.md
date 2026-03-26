# Guia d’Auditoria – TransLògic S.A.

## Introducció
Monitorització i auditoria del servidor per garantir control d’accessos i rendiment.

---

## 1. Monitorització de recursos
Accedim al Gestor de Tasques per veure CPU i RAM.

![Rendiment CPU/RAM](/Tasca08/IMG/1.png)

**Anàlisi:** CPU al 1%, memòria 1,9 GB usats (48%). Servidor sense estrès.

---

## 2. Detall de rendiment
Visió ampliada dels recursos.

![Detall rendiment](/Tasca08/IMG/2.png)

**Anàlisi:** Confirmem recursos per sota del límit.

---

## 3. Configuració d’auditoria
Activem auditoria d’inici de sessió (èxits i fracassos) a la política de seguretat local.

![Política d’auditoria](/Tasca08/IMG/3.png)

**Anàlisi:** Es registraran tots els intents d’accés.

---

## 4. Simulació d’incidents
Tanquem sessió i intentem entrar 4 vegades amb contrasenya incorrecta.

![Intent fallit](/Tasca08/IMG/4.png)

---

## 5. Anàlisi forense
Al Visor d’Esdeveniments (Seguretat) localitzem els intents fallits.

![Visor d’esdeveniments](/Tasca08/IMG/5.png)

**Event ID per errors d’inici de sessió:** **4625** (en aquest cas apareix 4771 per autenticació Kerberos, però l’estàndard és 4625).

---

## Conclusió
Servidor estable, auditoria funcional i evidències d’intents d’intrusió registrades.

---

## Conclusió
El servidor treballa correctament, l’auditoria està activada i els intents d’intrusió queden registrats per a futures anàlisis.
