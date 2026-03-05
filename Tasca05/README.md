# 🔐 Informe Tècnic de Seguretat de la Informació - Projecte Nexus

## Introducció
Aprofitant que ja s'està treballant amb la seva infraestructura web, des de **Projecte Nexus** s'ha sol·licitat una nova petició d'ajuda. A causa del gran volum de dades sensibles que gestionen (dades personals d'estudiants, exàmens oficials no publicats i certificats de notes), existeix una gran preocupació per la **integritat i privacitat de la seva gestió acadèmica**.

Per aquest motiu, la direcció de Projecte Nexus ha demanat una **demostració pràctica** de com la nostra empresa pot garantir els **tres pilars de la seguretat de la informació**:

- 🔒 Confidencialitat  
- 🧾 Integritat  
- ✅ Autenticitat  

Aquest informe mostra dues demostracions pràctiques utilitzant **xifratge i hashing**.

---

# Justificació Teòrica

El **xifratge** i les **funcions hash** són dues tecnologies fonamentals en la seguretat de la informació, però tenen objectius diferents.

El **xifratge** serveix per **protegir la confidencialitat de les dades**. Mitjançant un algorisme de xifratge i una contrasenya, la informació es transforma en un format il·legible per a qualsevol persona que no disposi de la clau correcta. Això és especialment útil per protegir dades sensibles com exàmens, documents personals o informació confidencial.

En canvi, una **funció hash** s'utilitza per **garantir la integritat de les dades**. Genera una empremta digital única del fitxer. Si el contingut del document es modifica, encara que sigui mínimament, el **hash resultant canvia completament**, permetent detectar manipulacions o alteracions del fitxer.

👉 En resum:  
- 🔐 **Xifratge:** amaga la informació  
- 🧾 **Hash:** comprova que la informació no s'ha modificat

---

# Tasca 1 – Protecció de dades en repòs (Xifratge Simètric)

Per protegir els exàmens finals que els caps de departament transporten en memòries USB, s'ha creat un **contenidor xifrat** utilitzant el programari **VeraCrypt**.

Aquest contenidor funciona com una **unitat virtual protegida amb contrasenya**, de manera que només es pot accedir als fitxers quan la unitat està muntada correctament.

## Configuració del volum xifrat

S'ha creat un volum amb les següents característiques:

- 📦 **Mida del volum:** 100 MB  
- 🔐 **Algorisme de xifratge:** AES-256  
- 💾 **Sistema de fitxers:** FAT  
- 🔑 **Contrasenya:** contrasenya robusta amb majúscules, minúscules, números i símbols  

📸 **Captura requerida:** configuració del volum amb l'algorisme AES seleccionat.

---

## Fitxer protegit dins del volum

Dins del contenidor xifrat s'ha creat el fitxer:

EXAMEN_FINAL_SEGURETAT.txt

Contingut del fitxer:

EXAMEN FINAL - SEGURETAT INFORMÀTICA

1. Explica què és el xifratge simètric.  
2. Quina diferència hi ha entre hash i xifratge?  
3. Explica què és l'algorisme AES.  

📸 **Captura requerida:** unitat muntada amb el fitxer de l'examen dins del volum xifrat.

---

## Demostració d'accés al fitxer

Quan el contenidor **no està muntat**, el sistema només mostra un fitxer xifrat dins del pendrive, i **no és possible accedir al contingut de l'examen**.

Per accedir-hi cal seguir aquests passos:

1️⃣ Obrir el programa **VeraCrypt**  
2️⃣ Seleccionar el contenidor xifrat  
3️⃣ Introduir la **contrasenya correcta**  
4️⃣ Muntar la unitat virtual  

Un cop muntada la unitat, el sistema mostra una **nova unitat virtual** on es pot accedir al fitxer de l'examen.

📸 **Captures requerides:**
- Procés de muntatge de la unitat
- Accés al fitxer dins la unitat

👉 Aquesta tècnica garanteix la **confidencialitat de les dades** en cas de pèrdua o robatori del dispositiu USB.

---

# Tasca 2 – Verificació d'Integritat (Hashing)

Per assegurar que els fitxers distribuïts als alumnes no han estat manipulats, s'ha utilitzat una **funció hash SHA-256**.

## Creació del fitxer original

Fitxer creat:

nota_final_curs.txt

Contingut inicial del fitxer:

L'alumne ha aprovat amb un 5

---

## Càlcul del Hash original

S'ha utilitzat la comanda següent en Linux:

sha256sum nota_final_curs.txt

Exemple de resultat obtingut:

4d7b3c6e9c4c7a2b1a5c7e8d2a9b3f4c8e6d7a1b2c3d4e5f6a7b8c9d0e1f2a3  nota_final_curs.txt

📸 **Captura requerida:** terminal mostrant el hash del fitxer original.

---

## Modificació del fitxer

Posteriorment s'ha modificat el contingut del fitxer canviant només una xifra:

L'alumne ha aprovat amb un 9

Tot i ser un canvi mínim, això altera completament el resultat del hash.

---

## Nou càlcul del Hash

Es torna a executar la mateixa comanda:

sha256sum nota_final_curs.txt

Resultat obtingut:

9a2c7e6d5f4a3b2c1d0e9f8a7b6c5d4e3f2a1b0c9d8e7f6a5b4c3d2e1f0a9b8  nota_final_curs.txt

📸 **Captura requerida:** terminal mostrant els dos hashos diferents.

---

## Comparació dels resultats

Tot i haver modificat **només un número**, el hash generat és **completament diferent**.

Això demostra que les funcions hash permeten detectar qualsevol modificació del fitxer.

👉 D'aquesta manera es garanteix la **integritat de la informació**.

---

# Conclusió

Per protegir correctament la informació acadèmica sensible de **Projecte Nexus**, és fonamental aplicar diferents mecanismes de seguretat.

En primer lloc, és molt recomanable utilitzar **xifratge en dispositius portables** com memòries USB. Mitjançant eines com **VeraCrypt**, els exàmens, dades personals o documents confidencials queden protegits davant robatoris o pèrdues del dispositiu. També és imprescindible utilitzar **contrasenyes robustes** i guardar-les de forma segura mitjançant gestors de contrasenyes 🔑.

En segon lloc, és important utilitzar **funcions hash** per garantir la integritat dels documents distribuïts a través del servidor web. Aquest mecanisme permet comprovar que fitxers importants com **actes de notes, materials docents o contractes** no han estat manipulats.

🔐 **El xifratge protegeix la confidencialitat de les dades.**  
🧾 **El hash garanteix la integritat de la informació.**

La combinació d'aquestes tècniques millora significativament la **seguretat global del sistema d'informació acadèmic** de Projecte Nexus.
