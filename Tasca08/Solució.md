# Guia d’Auditoria – TransLògic S.A.

## Introducció
Hem configurat la monitorització i auditoria del servidor per garantir el control d’accessos i el rendiment.

---

## 1. Monitorització de recursos
Accedim al Gestor de Tasques per comprovar l’estat de CPU i RAM.

![Rendiment CPU/RAM](/Tasca08/IMG/1.png)

**Anàlisi:** CPU al 1%, memòria utilitzada 1,9 GB (48%). Servidor sense estrès.

---

## 2. Configuració d’auditoria
Activem l’auditoria d’inici de sessió (èxits i fracassos) a la política de seguretat local.

![Política d’auditoria](/Tasca08/IMG/2.png)

**Anàlisi:** Es registraran tots els intents d’accés, tant correctes com fallits.

---

## 3. Simulació d’incidents
Tanquem sessió i intentem entrar 4 vegades amb un usuari vàlid però contrasenya incorrecta. Després entrem amb l’administrador.

![Intent fallit](/Tasca08/IMG/3.png)

---

## 4. Anàlisi forense
Al Visor d’Esdeveniments (Seguretat) trobem els intents fallits.

![Visor d’esdeveniments](/Tasca08/IMG/4.png)

**Event ID per errors d’inici de sessió:** **4625** (en aquest cas apareix 4771 per autenticació Kerberos, però el codi estàndard és 4625).

---

## Conclusió
El servidor treballa correctament, l’auditoria està activada i els intents d’intrusió queden registrats per a futures anàlisis.
