## x) Tiivistelmä ja humiot artikkelista https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited#package-management--installing-software
 - Käytä hyväksesi ohjesivuja (komento `man`) ja komentojen sisäänrakennettuja ohjeita (komento `"komento" --help`), jos tuntuu siltä, että olet jumissa tai komento ei toimi niin kuin pitäisi
 - Käytä ylläpitäjän oikeuksia (`sudo`) vain kun on pakko, sillä näillä oikeuksilla ajetut komennot vaikuttavat koko järjestelmään
 - Ole tarkkana kun nimeät tai siirrät hakemistoja/ tiedostoja `mv`- komennolla, sillä jos kummatkin komennossa mainitut parametrit ovat tiedostoja korvaa edellä mainittu toisena mainitun ilman erillistä varoitusta

## a) micro-editorin asennus

Micro-editorin asentaminen oli helppoa, ajoin vain komennon `sudo apt install micro` (huomaa ylläpitäjän oikeudet) ja valitsin "Y" jatkaakseni asennusta. Kun asennus oli valmis, sain editorin auki komennolla `micro`.

## b) komentoriviohjelmien asennus

Valitsin ladattaviksi vimin, wikitin ja glances:in. . Aloitin asentamisen tarkastamalla saatavilla olevat paketit komennolla `sudo apt update`, jonka jälkeen asensin ensin vimin komennolla sudo apt install vim. 

Vim on yksi Linuxille asennettavista tekstieditoreista. En ole itse sitä käyttänyt, mutta ajatuksena olisi niin tehdä. VIMin käytön voi aloittaa kirjoittamalla komentokehotteeseen komennon `vimtutor`, joka avaa VIM Tutorin, jota seuraamalla opit VIMin perusteet.

<img width="948" height="811" alt="image" src="https://github.com/user-attachments/assets/cd4ab56a-741e-48ee-aad1-5f2ab26a8756" />
  
Sitten asensin wikitin, jonka asennus vaati ensin nodejs:n ja nodejs npm:n. Nodejs on siis ympäristö, jonka avulla voi ajaa JavaScriptiä selaimen ulkopuolella ja nodejs npm on nodejs:n mukana tulevan pakettienhallinta työkalu, jonka kautta wikit asennetaan.
Wikitn asennus siis ajetaan komennolla `npm install wikit -g`. Wikitin käyttö toimii komennolla `wikit artikkelin_nimi`. Kuva alla. 

<img width="956" height="789" alt="image" src="https://github.com/user-attachments/assets/dfdfc490-9acb-47d8-b6e8-1c5e7c41e752" />

Viimeisenä asensin Glances:in joka on järjestelmän valvonta työkalu. Asensin ohjelman komennolla `sudo apt install glances`. Ohjelma ajetaan komennolla `glances`. Kuva ohjelmasta alla.

<img width="1907" height="982" alt="image" src="https://github.com/user-attachments/assets/0949abd6-ac11-47f3-957a-723d359a7353" />

## c) Tärkeät hakemistot

Linuxin tärkeimpiä hakemistoja  ovat / (=root), /home/, /home/user/, /etc/, /media/ sekä /var/log/. 
Root hakemisto on Linuxin järjestelmä hierarkian huipulla ja se sisältää tärkeitä järjestelmä tiedostoja sekä hakemistoja. Esimerkkinä tällaisesta hakemistosta toimii /bin joka sisältää komentoja joita käyttää sekä järjestelmän ylläpitäjä sekä käyttäjät. Kyseiseen hakemistoon 
pääsee root hakemistosta komennolla `cd bin/`. Terminaalin avatessasi avautuu se yleensä hakemistoon /home/user/ niin root hakemistoon pääset komennolla `cd /`. Alla vilaus /bin/ hakemiston sisällöstä.

<img width="749" height="850" alt="image" src="https://github.com/user-attachments/assets/3b2bce28-fdef-409c-8fdd-ce80e7b9748f" />

Home hakemistosta löytyy käyttäjien hakemistot, ja home hakemistoon pääsee komennolla `cd /home`. Alla näkyy oman järjestelmäni home kansion sisältö, joka siis on oman käyttäjäni hakemisto. 

<img width="375" height="80" alt="image" src="https://github.com/user-attachments/assets/becf1e71-917f-4283-80fc-af6506b868c1" />

Käyttäjän hakemisto (/home/user/) sisältää käyttäjä kohtaiset konfiguraatio tiedostot eri ohjelmille. Käyttäjän koti hakemistoon pääsee komennolla `cd user/` ja sisältää ainakin alla näkyvät hakemistot. 

<img width="743" height="57" alt="image" src="https://github.com/user-attachments/assets/22dcb0a0-7570-4a8c-a1b8-d4dd97aadfe0" />

Lisää konfiguraatio tiedostoja löytyy /etc/ hakemistosta 










## Lähteet
https://www.freecodecamp.org/news/vim-beginners-guide/
https://www.geeksforgeeks.org/linux-unix/wikit-in-linux/
https://dev.to/asirsamr/what-is-nodejs-and-npm-a-beginners-guide-cl5
