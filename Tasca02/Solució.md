# T02: Missió Apache: Desplegament Multidomini i segur
## Abdeslam Khfif Koubee


![imatge](/Tasca02/IMG/1.png)
El primer que haurem de fer sera fer un "sudo apt update" per tenir tot actualitzat i correcte 



![imatge](/Tasca02/IMG/2.png)
El següent que farem sera instalar el apache2 



![imatge](/Tasca02/IMG/3.png)
I ara farem un sudo "systemctl enable apache2" per activar-ho i justament despres Es comprova l’usuari www-data al fitxer /etc/passwd i es canvien el propietari i els permisos del directori /var/www perquè pertanyi a www-data amb permisos 755


![imatge](/Tasca02/IMG/4.png)
Ara es creen els directoris dels projectes dins de /var/www, s’assigna www-data com a propietari i s’obre l’arxiu index.html amb nano per editar-lo.



![imatge](/Tasca02/IMG/5.png)
Un cop a dins ficarem el següent codi 





![imatge](/Tasca02/IMG/7.png)
Ara entrarem en el nano de academia i ficarem el següent codi 




![imatge](/Tasca02/IMG/8.png)
Ara es copien els fitxers de configuració per defecte d’Apache per crear-ne de nous per als llocs projectenexus i academia



![imatge](/Tasca02/IMG/9.png)
Ara fem la configuració d’un VirtualHost d’Apache editada amb GNU nano, on es defineix el domini projectenexus.test, el seu àlies, la ruta del directori arrel del lloc web i els fitxers de registre d’errors i accessos.



![imatge](/Tasca02/IMG/10.png)
Aqui farem el mateix que abans pero ho farem amb academia.test




![imatge](/Tasca02/IMG/11.png)
 ara fem un systemctl que recarrega i comprova l’estat del servei Apache2 des del terminal. El resultat indica que el servidor web està actiu i en execució




![imatge](/Tasca02/IMG/12.png)
Ara s’activen els llocs web projectenexus.test i academia.test utilitzant la comanda a2ensite des del terminal.
Posteriorment es recarrega el servei Apache2 amb systemctl reload apache2 per aplicar correctament la nova configuració.



![imatge](/Tasca02/IMG/13.png)
Ara fem un sudo nano /etc/hosts i fiquem el següent 



![imatge](/Tasca02/IMG/14.png)
A la imatge s’està editant amb GNU nano un fitxer de configuració d’Apache per crear un VirtualHost al port 80 del domini projectenexus.test. En la configuració es defineixen el DocumentRoot, els fitxers de logs d’error i accés, i una pàgina personalitzada per a l’error 404.




![imatge](/Tasca02/IMG/15.png)
A la imatge es veu una terminal on s’activa el mòdul SSL d’Apache amb la comanda sudo a2enmod ssl. Després, es reinicia el servei amb sudo systemctl restart apache2 per aplicar la nova configuració.





![imatge](/Tasca02/IMG/16.png)
A la imatge es veu una terminal on es crea un certificat SSL autosignat amb OpenSSL per a un servidor Apache. Durant el procés es demanen dades del servidor (país, ciutat, nom del domini, etc.) i finalment es genera el certificat.



![imatge](/Tasca02/IMG/17.png)




![imatge](/Tasca02/IMG/19.png)




![imatge](/Tasca02/IMG/20.png)




![imatge](/Tasca02/IMG/21.png)




![imatge](/Tasca02/IMG/22.png)
