## x)

## a) Apachen testaus

Testasin, että vastaako webbipalvelimeni localhost osoitteesta, ja kyllähän se vastasi. 

<img width="619" height="398" alt="Screenshot 2026-02-01 232441" src="https://github.com/user-attachments/assets/0e7bd7b4-ac03-43fd-b6fc-01dcba78a58e" />

Sivu näytti tältä, kun poistin tiedoston polusta "/var/www/html/index.html" ja sekoilin muutenkin tiedostojen kanssa, kun pyrin saamaan Apachen oman oletus sivun näkyviin. Jota siis en saanut näkyviin.

## b) apace2/access.log -analysointi

Lokiin pääsi käsiksi komennolla `sudo tail -f /var/log/apache2/access.log`. Tarkoituksena oli etsiä rivit, jotka syntyvät kun lataa omalta palvelimelta sivuja, ja nämä rivit löytyvät alla olevasta kuvasta. Avaan jokaisen rivin kohdan auki kuvan alla. 

<img width="1781" height="61" alt="image" src="https://github.com/user-attachments/assets/aa429dec-015e-41cc-a147-1dcf90e29fdf" />

1. 127.0.0.1, client Ip eli ip-osoite, josta pyyntö tuli.
2. -, paikka identd-käyttäjälle. Käytetty identd.protokollan kanssa, mutta sitä ei nykyaikaisissa järjestelmissä yleensä ole käytössä.
3. -, paikka autentikoidulle käyttäjälle. 
4. [01/Feb/2026:23:23:13 +0200], pyynnän aikaleima sisältäen päivän, ajan ja aikavyöhykkeen.
5. "GET /?C=D;O=A HTTP/1.1", on pyyntömenetelmä. Get on HTTP-meodi, /?C=D;O=A on pyydetty resurssi, HTTP/1.1 on HTTP-protokollan versio
6. 200, on HTTP-statuskoodi. 200 tarkoittaa että kaikki ok ja pyyntä onnistui.
7. 604, vastauksen koko bitteinä
8. "http//localhost/?C=N;O=A", kertoo sivun miltä pyyntä on tullut.
9. "Mozilla/5.0 (X11; Linux x86:64: rc:140.0) Gecko/20100101 Firefox/140.0", user-agent string, joka tunnistaa selaimen ja käyttöjärjestelmän.

##c) Etusivu uusiksi

Aloitin luomalla hakemiston komennolla `mkdir -p /home/jonim/publicsites/hattu, jonne tulen myöhemmin hattu.example.com html sivun. 
Sen jälkeen loin VirtualHost-tiedoston ja lisäsin sinne määritykset. 

!Tässä kohtaa sain AH00094 errorin enkä saanut sitä selvitettyä tehtävän palautus aikaan mennessä!


