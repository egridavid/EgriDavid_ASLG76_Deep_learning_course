# 2018.10.02 / Deep Learning / Lecture 5



## Milestone

* Ha kagle, akkor több kell ami fent van
* Nézni kell ó, hogy mások mit csináltad
* Kell az train, test, valid lennie kell
* Twitter-en van minden, ami kell

## Deep learning hiradó

1. DeepMind Image Synthesis
   * GAN -> olyan AI, ami generál valalmit -> pl. kép
   * Érdekes a képet interpolációja -> férfiből nőbe átmegy a kép

## Kérdés

1. jogos kérdés -> lehetne máshol, de itt elég volt
   * Keras esetén alapból van minden rétegben
   * Volt olyan idő, amikor a no bias network a menő
   * Bias kérdés körbe járása is érdekes lenne nagyházinak

## Ismétlés

* Jó nagyházi téma lehet az aktivációs függvény körbe járása is
  * esetleg új fajta kipróbálása

## Mai anyag --> Konvolúciós hálók

* **jövőhéten szombaton is van óra --> előadás, gyak lesz összevonva**
* **Kedden a Continental-tól jön vendég --> deep learning műhelyet alapítottak --> ipari alkalmazások**

9. dia

   * osztáylozás --> konvolúciós hálók
   * A XOR problémánál az osztályozás is regresszióként fogalmaztuk meg
   * Sok osztálynál, más az aktiváció, hiba függvény

10. dia

    * Pénzügyben asszimetrikus hibafüggvény --> Regresszió esetén a hibafüggvényre

    * Regressziónál figyelni kell, hogy ha [-1,1] közé tanítjuk a hálót, akkor ne kelljen neki 5-t jósolni

    * one hot kódolás: A keresztentrópiához

      * |  a   | 1    | 100  |
        | :--: | ---- | ---- |
        |  b   | 2    | 010  |
        |  a   | 1    | 100  |
        |  a   | 1    | 100  |
        |  c   | 3    | 001  |

11. dia

    * Miért nem kellenek az új aktivációs, hiba függévények

12. dia

    * ugyan annak egy jobb modellje
    * de pl. a pontosság ugyan olyan maradt
    * Nem böntetjük azt amit nem talál el, csak azt veszi figyelmbe amit eltalál

## Kahoot

22. dia
    * Precision, Recall megadja, hogy az első vagy a másod fajú hibánk a nagy
    * sclearn-nek vannak erre csomagjai
    * mindig a mátrix + a számok

24. dia
    * A konvolúciós hálók felé mozdult el az egész iparág
    * CNN lavina
    * AlexNet-tel kezdődött el a deep learning





