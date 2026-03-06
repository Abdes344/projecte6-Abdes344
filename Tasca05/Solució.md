# T05: Top Secret, protegint els secrets
## Abdeslam Khfif Koubee
---
![imatge](/Tasca05/IMG/1.png)

El primer que haurem de fer sera anar al navegador que tinguem i instalarem el veracrypt

---

![imatge](/Tasca05/IMG/2.png)

Un cop instalat el veracrypt entrarem i ens surtiran 3 opcions nosaltres triarem la primera que diu "Crear un contenedor de archivos cifrado" 

---

![imatge](/Tasca05/IMG/3.png)

Aqui tindrem que triar entre un volumen comú o ocult nosaltres triarem el comú

---

![imatge](/Tasca05/IMG/4.png)

Ara triarem la ruta on volem ficar el nostre volum

---

![imatge](/Tasca05/IMG/5.png)

Aqui en el xifrat triarem el AES i en el hash el SHA-256. El AES xifra les dades de manera segura, i SHA-256 crea una empremta única per verificar la integritat

---

![imatge](/Tasca05/IMG/6.png)

Aqui ficarem la mida del nostre volum triarem 100 MB

---


![imatge](/Tasca05/IMG/7.png)

Ara ficarem una contrasenya que sigui segura ja que si fiquem una facil no ens deixara continuar 

---


![imatge](/Tasca05/IMG/8.png)

Ara el nostre volum el ficarem en FAT i en format complet i li donarem a formatejar 

---


![imatge](/Tasca05/IMG/9.png)

Aqui veiem que el nostre volum se ha creat amb exit 

---


![imatge](/Tasca05/IMG/10.png)

I aqui ja tindriem el volum creat 

---


![imatge](/Tasca05/IMG/11.png) 

Un cop dins del veracrypt i despres de crear el nostre volum seleccionarem la ruta on el vam ficar abans 


---


![imatge](/Tasca05/IMG/12.png)

Aqui seleccionarem el nostre volum 


---


![imatge](/Tasca05/IMG/13.png)

Aqui veiem que ja esta ficada la ruta del nostre volum  


---


![imatge](/Tasca05/IMG/14.png)  

Triarem una lletra qualsevol i ficarem la contrasenya que vam ficar abans que sigui segura i despres li donarem a montar 


---


![imatge](/Tasca05/IMG/15.png)

Aqui veiem que ja haurem montat el nostre volum 


---

![imatge](/Tasca05/IMG/16.png)

Veiem que s'ha creat just en la lletra que hem triat nosaltres 

---

![imatge](/Tasca05/IMG/18.png)

En el disc que acabem de veure crearem un arxiu que es dira "EXAMEN_FINAL.TXT" i ficarem cualsevol cosa 

---



![imatge](/Tasca05/IMG/19.png)

Ara anirem a documentos i crearem un arxiu anomenat "nota_final_curs.txt"


---

![imatge](/Tasca05/IMG/20.png)

I ficarem el seguent "l'alumne ha aprovat amb un 5"

---


![imatge](/Tasca05/IMG/21.png)

Entrarem a la terminal i ficarem la seguent comanda "certutil -hashfile nota_final_curs.txt.txt SHA256" Aquesta comanda calcula el hash SHA-256 del fitxer nota_final_curs.txt per verificar la seva integritat i mostra el resultat.


---


![imatge](/Tasca05/IMG/22.png)  

Ara crearem un altre arxiu pero en aquest cas ficarem que "l'alumne ha aprovat amb un 9"


---

![imatge](/Tasca05/IMG/23.png)  

I tornarem a ficar la comanda anterior 
