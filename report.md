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
Minulla on tässä linuxissa asenettuna vs coden, joten pystyin avaamaan tuon ihan vaan laittamalla code fixedpasstr.c

Kysyin tekoälyä luomaan minulle ohjelman, jolla minä saisin kaikki sala-hakkeri-321 merkit muutettua yhdellä ASCII muodossa (esim 115 --> 114 jne):

<img width="520" height="322" alt="image" src="https://github.com/user-attachments/assets/8c389fc8-fb9d-46bd-ae20-b5f0e397674b" />

Tässä tuo key kertoo, kuinka paljon se muuttuu. Sain tuosta tälläisen tulosteen:

<img width="728" height="55" alt="image" src="https://github.com/user-attachments/assets/c039e135-50b1-4dc0-85e0-8a0f94e4d160" />

Otin nämä talteen, koska minä aion käyttää näytä myöhemmin tuossa uudessa ohjelmassa.

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


