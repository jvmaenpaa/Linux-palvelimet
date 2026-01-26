## x) Tiivistelmä ja humiot artikkelista
 - Käytä hyväksesi ohjesivuja (komento `man`) ja komentojen sisäänrakennettuja ohjeita (komento `"komento" --help`), jos tuntuu siltä, että olet jumissa tai komento ei toimi niin kuin pitäisi
 - Käytä ylläpitäjän oikeuksia (`sudo`) vain kun on pakko, sillä näillä oikeuksilla ajetut komennot vaikuttavat koko järjestelmään
 - Ole tarkkana kun nimeät tai siirrät hakemistoja/ tiedostoja `mv`- komennolla, sillä jos kummatkin komennossa mainitut parametrit ovat tiedostoja korvaa edellä mainittu toisena mainitun ilman erillistä varoitusta

## a) micro-editorin asennus

Micro-editorin asentaminen oli helppoa, ajoin vain komennon `sudo apt install micro` (huomaa ylläpitäjän oikeudet) ja valitsin "Y" jatkaakseni asennusta. Kun asennus oli valmis, sain editorin auki komennolla `micro`.

## b) komentoriviohjelmien asennus

Valitsin ladattaviksi vimin, wikitin ja glances:in. Aloitin asentamisen tarkastamalla saatavilla olevat paketit komennolla `sudo apt update`, jonka jälkeen asensin ensin vimin komennolla `sudo apt install vim`. 

Vim on yksi Linuxille asennettavista tekstieditoreista. En ole itse sitä käyttänyt, mutta ajatuksena olisi niin tehdä. VIMin käytön voi aloittaa kirjoittamalla komentokehotteeseen komennon `vimtutor`, joka avaa VIM Tutorin, jota seuraamalla opit VIMin perusteet.

<img width="948" height="811" alt="image" src="https://github.com/user-attachments/assets/cd4ab56a-741e-48ee-aad1-5f2ab26a8756" />
  
Sitten asensin wikitin, jonka asennus vaati ensin nodejs:n ja nodejs npm:n. Nodejs on siis ympäristö, jonka avulla voi ajaa JavaScriptiä selaimen ulkopuolella ja nodejs npm on nodejs:n mukana tulevan pakettienhallinta työkalu, jonka kautta wikit asennetaan.
Wikitn asennus siis ajetaan komennolla `npm install wikit -g`. Wikitin käyttö toimii komennolla `wikit artikkelin_nimi`. Kuva alla. 

<img width="956" height="789" alt="image" src="https://github.com/user-attachments/assets/dfdfc490-9acb-47d8-b6e8-1c5e7c41e752" />

Viimeisenä asensin Glances:in joka on järjestelmän valvonta työkalu. Asensin ohjelman komennolla `sudo apt install glances`. Ohjelma ajetaan komennolla `glances`. Kuva ohjelmasta alla.

<img width="1907" height="982" alt="image" src="https://github.com/user-attachments/assets/0949abd6-ac11-47f3-957a-723d359a7353" />

Tehtävänannossa kysyttiin, että voisiko kaikki kolme ohjelmaa asentaa samalla komennolla. Löysin ja tiedän miten komentoja pystyisi ketjuttamaan tai ajamaan samanaikaisesti, mutta en löytänyt mitään toimivaa ratkaisua johon saisin Wikitin asentamiseen tarvittavat paketit (nodejs ja nodejs npm) ladattua ensin. Yritin asentaa ohjelmia & operaattorilla, mikä ei suorita seuraavaa vaihetta, jos ensimmäinen ei onnistu mutta en saanut sitä jostain syystä toimimaan. Uskon, että tein tässä kohtaa jonkin virheen minkä takia komento ei toiminut. Kokeilemani komento oli `sudo apt install nodejs && sudo apt install nodejs npm && sudo apt install wikit wim glances`. Jouduin siis lopulta asentamaan ohjelmat erikseen. 

## c) Tärkeät hakemistot

Linuxin tärkeimpiä hakemistoja  ovat / (=root), /home/, /home/user/, /etc/, /media/ sekä /var/log/. 
Root hakemisto on Linuxin järjestelmä hierarkian huipulla ja se sisältää tärkeitä järjestelmä tiedostoja sekä hakemistoja. Esimerkkinä tällaisesta hakemistosta toimii /bin joka sisältää komentoja joita käyttää sekä järjestelmän ylläpitäjä sekä käyttäjät. Kyseiseen hakemistoon 
pääsee root hakemistosta komennolla `cd bin/`. Root hakemistoon pääsee komennolla `cd /`. Alla vilaus /bin/ hakemiston sisällöstä.

<img width="749" height="850" alt="image" src="https://github.com/user-attachments/assets/3b2bce28-fdef-409c-8fdd-ce80e7b9748f" />

Root hakemisto sisältää myös hakemiston /etc/, joka sisältää järjestelmän konfiguraatio tiedostoja, jotka kontrolloivat käyttäjärjestelmän ja asennettujen ohjelmien toimintaa. Esimerkiksi juuri asentamani Glances ohjelman konfiguraatio tiedoston. Kuva alla.

<img width="1810" height="538" alt="Screenshot 2026-01-26 105147" src="https://github.com/user-attachments/assets/dee687d5-f8ea-45b0-a181-24b8d242ceca" />

Ja tässä vielä Glances konfiguraatio tiedoston sisältöä.

<img width="883" height="930" alt="image" src="https://github.com/user-attachments/assets/dcc17285-091f-4010-83a9-465b88a237ea" />

Root hakemiston /media/ hakemisto sisältää alihakemistoja joita käytetään irroitettavan median kiinnityspaikkoina. Kiinnitykset voidaan tehdä myös muihin hakemistoihin. Hakemistoon pääsee komennolla `cd mdeia/` root hakemistosta. 

Root hakemiston /var/ hakemisto sisältää erilaisia data tiedostoja kuten hallinnollista ja loki dataa sekä väliaikaisia tiedostoja. Kyseisessä hakemistossa sijaitsee alihakemisto /log/, joka sisältää lokitiedostoja, jotka tallentaa erilaisia tapahtumia ja virheitä järjestelmän toimintaan ja ohjelmiin liittyen. Alla kuva tiedostosta boot.log, joka sisältää tietoja järjestelmän käynnistys hetkestä. 

<img width="1454" height="909" alt="image" src="https://github.com/user-attachments/assets/7b73c928-17d4-43dd-b20c-107ad7854e66" />

Home hakemistosta löytyy käyttäjien hakemistot, ja home hakemistoon pääsee komennolla `cd /home`. Alla näkyy oman järjestelmäni home kansion sisältö, joka siis on oman käyttäjäni hakemisto. 

<img width="375" height="80" alt="image" src="https://github.com/user-attachments/assets/becf1e71-917f-4283-80fc-af6506b868c1" />

Käyttäjän hakemisto (/home/user/) sisältää käyttäjä kohtaiset konfiguraatio tiedostot eri ohjelmille. Käyttäjän koti hakemistoon pääsee komennolla `cd user/` ja sisältää ainakin alla näkyvät hakemistot. 

<img width="743" height="57" alt="image" src="https://github.com/user-attachments/assets/22dcb0a0-7570-4a8c-a1b8-d4dd97aadfe0" />

## d) Grep

Grep-komentoa käytetään, kun halutaan etsiä tiettyä tekstiä teksti tiedostoista. Tein alla olevan tiedoston autot.txt polkuun /home/jonim/Documents/autot.txt, ja esittelen muutaman tavan käyttää grep komentoa sen avulla.

<img width="318" height="221" alt="image" src="https://github.com/user-attachments/assets/70917882-d9c3-4a9d-9889-4b3c380bda94" />

Kuvitellaan tilanne, jossa haluaisin tietää minkä värinen auto BMW on tiedostossa autot.txt, ja tiedämme missä autot.txt tiedosto sijaitsee niin voimme ajaa komennon vaikka root hakemistosta.

<img width="674" height="112" alt="image" src="https://github.com/user-attachments/assets/449005c0-3a44-4433-9cd8-c7c30ba54977" />

Komento tulostaa meille rivit missä mainitaan "BMW". 
Voimme myös hakea grep-komennolla tekstiä vaikka emme tietäisi haun kohteena olevan tiedoston tarkkaa sijaintia. Lisäämmä grep-komennon perään vain -r ja paikan etsiminen aloitetaan. Jos vaikka haluaisimme tietää missä tiedostossa mainitaan BMW niin voisimme kirjoittaa komennon seuraavalla tavalla.

<img width="1391" height="214" alt="image" src="https://github.com/user-attachments/assets/3878f909-cf5a-444c-982f-e68190a00976" />

Kuten huomaa niin laitoi haun alkavaksi ./home hakemistosta ja kun ajoin komennon niin se tulosti minulle polun mistä tiedosto löytyy ja sen/ne rivit missä BMW mainitaan.

## e) Pipe

Putket antavat mahdollisuuden käyttää yhden kommenon tulosta toisen komennon syötteenä. Esimerkiksi, jos haluamme esimerkiksi selata tiedoston autot.txt sisältä apuvälineessä less niin voimme putkittaa sen seuraavanlaisesti.

<img width="707" height="214" alt="image" src="https://github.com/user-attachments/assets/a34915d0-d7b9-46c9-9d2c-8ce6fc44e396" />

Ja alla vielä tulos.

<img width="394" height="1009" alt="image" src="https://github.com/user-attachments/assets/399cc576-57a2-4a5f-a9de-13e24e5550b1" />

## f) Rauta

Ajoin komennon `sudo lshw -short -sanitize` niin kuin tehtävänannossa sanottin ja tulos näkyy alla. 

<img width="1033" height="688" alt="image" src="https://github.com/user-attachments/assets/fd72b566-8f48-4342-a5dd-f39f22d2350f" />

Tuloksesta näkyy muutamia host-koneen tietoja, joita ovat virtualisointi alusta (VirtualBox) ja prosessorin malli (13th Gen Intel (R) Core (TM) i7-13700K. Prosessorista ei kuitenkaan näy ydinten määrää. Myöskään virtuaalikoneelle annettujen ytimien määrä ei tuloksesta näy. 







## Lähteet
Tehtävänanto: https://terokarvinen.com/linux-palvelimet/#h2-komentaja-pingviini
Artikkeli: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited
VIM: https://www.freecodecamp.org/news/vim-beginners-guide/
Wikit & nodejs: https://www.geeksforgeeks.org/linux-unix/wikit-in-linux/ & https://dev.to/asirsamr/what-is-nodejs-and-npm-a-beginners-guide-cl5
Grep: https://www.youtube.com/watch?v=Tc_jntovCM0
Pipes: https://www.youtube.com/watch?v=oyc_6UfoW3w
Linux FHS: https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html


