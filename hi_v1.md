## Tehtävänanto
Tehtävänä oli luoda uusi Linux pohjainen virtuaalikone käyttäen VirtualBox virtualisointiohjelmistoa, sekä kirjoittaa tehtävän etenemisestä mahdollisimman selkeä raportti, jota seuraten kuka tahansa voisi luoda samankaltaisen virtuaalikoneen.

## Tehtävän tekoon käytetty laitteisto ja käyttöjärjestelmä

- Emolevy: ROG STRIX Z790-E GAMING WIFI
- Prosessori:	13th Gen Intel(R) Core(TM) i7-13700K, 3400 Mhz, 16 Core(s), 24 Logical Processor(s)
- Muisti: Samsung SSD 980 PRO with Heatsink 2TB
- Ram: Kingston 32GB (2 x 16GB) Fury Beast DDR5, 6000MHz, CL36, 1,
- Näytönohjain: NVIDIA GeForce RTX 3080
- Käyttöjärjestelmä: Microsoft Windows 11 Pro, Version	10.0.26100 Build 26100

## Alustus eli VirtualBoxin ja ISO-kuvan lataaminen

VirtualBoxin saa ladattua osoitteesta https://www.virtualbox.org/wiki/Downloads ja näytön vasemmasta laidassa näkyy ladattavissaa olevat versiot (kuva alla). Valtsin itse Windows Hosts-version, sillä tietokone jolla tehtävää tein on varustettu Windows- käyttöjärjestelmällä. Kun painoin kohasta "Windows Hosts" niin lataus alkoi heti ja se vei noin 10 minuuttia.

![virtualbox download](images/vbd.jpg)

Kun lataus oli valmis niin latasin Debianin ISO-kuvakkeen, joka siis sisältää Linux pohjainen käyttöjärjestelmän käyttöö tarvittavat tiedostot, osoitteesta  https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/. Valitsin asennettavaksi debian-live-13.3.0-amd64-xfce.iso ISO-kuvan tehtävänannon mukaisesti. Ja tämä versio löytyy aivan sivun loppupäästä eli jouduin hieman rullaamaan sivua alaspäin, jotta sen löysin.

<img width="934" height="365" alt="Screenshot 2026-01-20 173551" src="https://github.com/user-attachments/assets/9673a698-dcd0-4626-b57c-c64920ea8758" />

## Virtuaalikoneen luonti

Alustuksen jälkeen avasin VirtualBoxin ja pääsin pohjustamaan virtuaalikonetta. Ikkunan auettu klikkasin kohtaa "New" josta avautui "Create Virtual Machin"-ikkuna.

<img width="961" height="554" alt="Screenshot 2026-01-19 015039" src="https://github.com/user-attachments/assets/5f5ec4e0-1532-4829-8898-11fe01967465" />

Ikkunasta sain nimetä virtuaalikoneen, valita kansion jonne virtuaalikone tallenetaan sekä ISO kuvakkeen, joka siis on äsken lataamani debian. Ikkunasta valitsin myös käyttöjärjestelmän tyypin, alatyypin ja version. Valinnat näkyvät alla olevassa kuvassa.

<img width="733" height="579" alt="Screenshot 2026-01-19 021323" src="https://github.com/user-attachments/assets/82f27a90-948f-4ab7-b945-c350989dc4e0" />

Sitten siirryin kohtaan "Hardware", jossa määritin RAMia 4096 MB ja prosessoreita 4 kappaletta. Näitä voi laittaa enemmänkin mikäli koneessa, jolla tehtävää tekee, riittää tehot ja muisti. Otin myös EFIN käyttöön (merkattu punaisella alla olevassa kuvassa). Seuraavaksi määritin kovalevyn koon ja asetin sen 50 gigaan. Tätäkin voi laittaa enemmän, jos omassa koneessa on vapaata muistia. Sitte painoin "finish", ja kone olikin heti valmis käynnistettäväksi.

<img width="744" height="573" alt="Screenshot 2026-01-20 175508" src="https://github.com/user-attachments/assets/b7715a52-290f-4c35-a2bd-0edd335718f9" />

<img width="733" height="587" alt="Screenshot 2026-01-19 021413" src="https://github.com/user-attachments/assets/2a23657e-fdc3-4ff7-8fa3-7e54568eb075" />

## Ensimmäinen käynnistys ja Debianin asennus

Koneen käynnistyttyä auksei käynnistysvalikko, josta valittiin ensimmäinen vaihtoehto eli "Live system (amd64)", joka antaa sinun kokeilla Linuxia ennen sen varsinaista lataamista. Valinnan jälkeen eteeni aukesi työpöytä ja näytti, että kaikki toimii niin kuin pitää. Testasin kuitenkin, että saan yhteyden verkkoon avaamalla selaimen vasemmasta yläreunassa olevasta "Applications" valikosta. Kokeilin muutamaa eri sivua ja yhteys toimi niin kuin pitikin. 
Yhteydet testattuani ja hieman tarkasteltuani työpöytää, aloitin debianin asentamisen työpyödän kuvakkeesta "Install debian". Eteeni aukesi seuraavan kuvan mukainen ikkuna. 

Oletuksena tarjottin kieleksi american englantia, jonka valitsinkin, ja jatkoin painamlla kohtaa "Next" oikeasta alareunasta.

<img width="827" height="548" alt="Screenshot 2026-01-19 024838" src="https://github.com/user-attachments/assets/62ed6e7b-f080-4e0b-9219-970b511d792b" />

Seuraavaksi valitsin sijainnin klikkaamalla kartasta Suomea, ja jatkoin eteenpäin seuraavaan vaiheeseen.
<img width="935" height="794" alt="Screenshot 2026-01-19 024855" src="https://github.com/user-attachments/assets/66cac3cd-57b7-48d2-b6f6-fa535a50a5e3" />

Näppäimistöksi määritin näppäimistön asetukset alla olevan kuvan mukaisesti ja klikkasin taas kohtaa "Next".

<img width="854" height="421" alt="Screenshot 2026-01-19 024936" src="https://github.com/user-attachments/assets/136fce78-8796-4b73-9da8-c6b9f15d9f22" />

Sitten oli aika määrittää käyttäjän tiedot eli oma nimeni ja salasana. Ohjelma teki ehdotukset käyttäjänimelle sekä tietokoneen nimelle, joilla jatkoinkin eteenpäin. Jätä kohta "Log in automatically without asking for the password." tyhjäksi.

<img width="881" height="644" alt="Screenshot 2026-01-19 025225" src="https://github.com/user-attachments/assets/b8a2223b-f7e6-4fa7-a873-c5e577f7eb08" />

Seuraavaksi olikin tehtyjen määritysten yhteenveto ja tarkastus, jonka jälkeen asennust alkoi mikä vei noin 10 minuuttia. 

<img width="1274" height="800" alt="Screenshot 2026-01-19 025430" src="https://github.com/user-attachments/assets/67cc9202-e13e-4bbf-a381-85c8bba2d86c" />

Asennuksen jälkeen ohjelma ilmoittaa kaiken olevan valmist ja käynnistyy uudestaan, kun klikkaat oikeasta alakulmasta kohtaa "Done". Uudellenkäynnistyken jälkeen kirjauduin koneeseen sisään äsken luomillani tunnuksilla. 
Kun olin päässyt koneelle sisään testasin yhteydet uudelleen vierailemalla muutamilla verkkosivuilla, ja yhteydet toimivatkin niin kuin piti. 
Testattuani yhteydet avasin terminaalin tyäpöydän alalaidasta. 

<img width="1277" height="874" alt="Screenshot 2026-01-19 024740" src="https://github.com/user-attachments/assets/f248c4db-7f00-4c80-9cb0-a76ac49f3cce" />

Tarkoituksena oli tarkistaa mitä päivityksiä oli saatavilla ja päivittää kaikki mahdollinen. Aloitin syöttämällä komennon `sudo apt-get update` , joka hakee saatavilla olevat päivitykset.
!Huomio, että kun ajat sudo-komennon pyytää järjestelmä sinun salasanaasi. Salasana ei näy näytöllä vaan se syötetään "piilossa", joten älä säikähdä, jos näytölle ei tulostu tekstiä. 

<img width="787" height="138" alt="Screenshot 2026-01-19 030006" src="https://github.com/user-attachments/assets/7f9b1063-dbcd-4c95-8a16-7170d25beb5f" />







