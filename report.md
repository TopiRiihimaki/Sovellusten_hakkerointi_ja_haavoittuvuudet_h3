# a)

Latasin tehtävän (https://terokarvinen.com/loota/yctjx7/ezbin-challenges.zip) jonka jälkeen purin zip-tiedoston:
<img width="681" height="188" alt="image" src="https://github.com/user-attachments/assets/09c6b643-b73f-40f0-9ec7-44b4c0f05845" />

Ne purkautu challenges kansioon, johon sitten menin ja menin ohjeiden mukaisesti tehtävään.
<img width="702" height="134" alt="image" src="https://github.com/user-attachments/assets/b7dca3fb-67f1-4f4a-9c75-ed748ef53900" />

Ajoin tuon ohjelman
```

./passtr

```
Ohjelma avautui, ja kun laitoin väärän salasanan, antoi se tämmöisen:
<img width="661" height="96" alt="image" src="https://github.com/user-attachments/assets/21e8281c-8248-460b-9dc9-7b7717a823d1" />

Laitoin sitten ihan vaan strings ja ohjelman nimen, niin löysin sitä kautta sitten salasanan. Sitä ei oltu mitenkään piilotettu.

<img width="723" height="118" alt="image" src="https://github.com/user-attachments/assets/d632cdc2-d22a-4e97-af7e-46b655926761" />

Laitoin sitten tuon salasanan, josta sain sitten tämän:
<img width="724" height="84" alt="image" src="https://github.com/user-attachments/assets/9dee3918-5ad2-47c4-b3be-9f9323f2330c" />

#b)

Kopioin tuon passtr tiedoston ja loin uuden nimeltä fixedpasstr
```
cp passtr.c fixedpasstr.c

```
Minulla on tässä linuxissa asenettuna vscode, joten pystyin avaamaan tuon ihan vaan laittamalla code fixedpasstr.c

Kysyin tekoälyä luomaan minulle ohjelman, jolla minä saisin kaikki sala-hakkeri-321 merkit muutettua yhdellä ASCII muodossa (esim 115 --> 114 jne):

<img width="520" height="322" alt="image" src="https://github.com/user-attachments/assets/8c389fc8-fb9d-46bd-ae20-b5f0e397674b" />

(Ennen ku tämän voi ajaa, pitää sille antaa oikeudet ``` chmod +x <TIEDOSTON NIMI>```

Tässä tuo key kertoo, kuinka paljon se muuttuu. Sain tuosta tälläisen tulosteen:

<img width="728" height="55" alt="image" src="https://github.com/user-attachments/assets/c039e135-50b1-4dc0-85e0-8a0f94e4d160" />

Otin nämä talteen, koska minä aion käyttää näitä myöhemmin tuossa uudessa ohjelmassa.

## Uuden ohjelman luominen
Koska meillä nyt on tuo alkuperäinen passtr.c kopioituna nimellä fixedpasstr.c, niin avataan tuo fixed tiedosto

```
code fixedpasstr.c
```

Aikaisemman ohjelman ansiosta, minulla on nyt tuon salasanan ASCII joka on hiukan muokattu, jonka avulla minä loin tälläisen muuttujan:

<img width="395" height="89" alt="image" src="https://github.com/user-attachments/assets/2208f228-f91c-4584-86da-a2dadde958f5" />

Minä sitten käännän tämän salatun salasanan takaisin oikeaksi tällä koodin pätkällä:

<img width="352" height="106" alt="image" src="https://github.com/user-attachments/assets/b36822d1-e005-4ae2-98df-192eb6e13b1e" />

Tässä se käy nuo salatut ASCII läpi ja "nostaa" niitä yhdellä (minulla on muuttuja int key = 1; jota käytetään tuossa myös).

Tämän jälkeen vertaillaan käyttäjän antamaa syötettä ja salasanaa, joka on nyt käännetty takaisin oikeaksi:

<img width="785" height="250" alt="image" src="https://github.com/user-attachments/assets/39f42f6f-4049-42e5-af98-154b4fa3bf21" />

Nyt koska salasanaa ei ole kunnolla esillä missään koodissa, niin sitä ei voida löytää strings komennolla.

<img width="715" height="130" alt="image" src="https://github.com/user-attachments/assets/eba3eebe-8c81-463a-a677-da07b00a8e56" />

Alkuperäinen koodi:

<img width="776" height="307" alt="image" src="https://github.com/user-attachments/assets/e09ba2c7-4a6d-4804-aa07-f5763ba66879" />


Uudempi koodi:

<img width="1106" height="598" alt="image" src="https://github.com/user-attachments/assets/5ddf6a99-e147-417d-9314-34b06d6c0c11" />

(Ennen kuin C-ohjelman voi suorittaa, C-lähdekoodi pitää kääntää suoritettavaksi ohjelmaksi. Tämä tehdään `gcc`:llä esimerkiksi komennolla `gcc <TIEDOSTON NIMI>.c -o <UUSI NIMI>`. Tämän jälkeen valmis ohjelma voidaan suorittaa komennolla `./<UUSI NIMI>`.)


# c)

Latasin tehtävän ja purin sen unzip komennolla. 

Purettuani tiedoston, ajoin ohjelman

```
./packed
```

Ja latoin jotain, mutta sain siitä ilmoituksen, että se oli väärin.

<img width="627" height="96" alt="image" src="https://github.com/user-attachments/assets/7cdf0ed0-8fa6-4e9f-8894-d7cbc628477d" />

Koitin etsiä salasanaa ```strings``` komennolla, mutta en löytänyt mitään, vain osan salasanaa:

<img width="315" height="133" alt="image" src="https://github.com/user-attachments/assets/c832d6ac-8e52-47c2-843d-aec65439b130" />

(Laitoin tuon mikä tuossa näkyy, mutta se ei kelvannut)

Katsoin kuitenkin tuota vähän enemmän ja löysin tälläisen, joka herätti kiinnostukseni:
```
$Info: This file is packed with the UPX executable packer http://upx.sf.net $
$Id: UPX 4.21 Copyright (C) 1996-2023 the UPX Team. All Rights Reserved. $
```
Kysyin tekoälyltä, miten voisin hyödyntää tätä, johon se ehdotti, että lataan tuon UPX ja puran tuon sillä.

UPX pystyy lataamaan suoraan terminaalista seuraavasti:
```
 sudo apt update
 sudo apt install upx-ucl
```
Tämän jälkeen menin hakemistoon, missä tuo packd tehtävä oli ja purin sen
```
upx -d packd
```
(d = decompress)

Tämän jälkeen laitoin tuon strings komennon uudestaan, joka oli nyt muuttunut:

<img width="750" height="96" alt="image" src="https://github.com/user-attachments/assets/b5284fb7-9066-4d97-a2e9-3dd65aff6a56" />

Otin tuon salasanan tuosta ja kokeilin laittaa sen tuohon ohjelmaan ja se toimi:

<img width="737" height="96" alt="image" src="https://github.com/user-attachments/assets/3acc7578-da49-413c-a13e-200196ab6923" />

# Oma ajatukset

Pidin itse tehtävästä paljon. Tehtävä oli haastava, mutta juuri sopivasti.

# Tekoälyn käyttö (GPT-5.6 Luna)
- Auttanut komentojen kanssa
- Auttoi tekemään avustusohjelman
- Selittämään käsitteitä

# Lähteet

https://terokarvinen.com/application-hacking/


