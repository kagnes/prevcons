# PrevCons – igekötős igei hapaxok adatbázisa

A _PrevCons_ (Preverb Constructions) egy nyílt hozzáférésű adatbázis, amely 21038 igekötős hapaxot tartalmaz azok lehetséges vonzatkeretével együtt. Ezen felül számos metaadat érhető el benne a hapaxok morfológiai szerkezetéről, szemantikájáról és konkrét szövegbeli előfordulásáról. Az adatbázisról az oldal alján feltüntetett publikációk nyújtanak részletes tájékoztatást.

A _PrevCons_ webes keresőfelület segítségével is böngészhető: [https://aszalo.herokuapp.com/](https://aszalo.herokuapp.com/)

A keresőfelületet **[Indig Balázs](https://github.com/dlazesz)** készítette.

### Az erőforrás szerkezete

A _PrevCons_ elérhető TSV fájlként (`PrevCons.tsv`) és SQLite adatbázisként is (`PrevCons.sqlite3`). Ezek pusztán a formátumukat tekintve térnek el egymástól, tartalmilag megegyeznek. A két formátumot az indokolja, hogy a számítógépes feldolgozáshoz praktikusabb lehet a TSV, a kézi adatelemzéshez pedig az SQLite-alapú megoldás. Az erőforrás 16 oszlopból áll, amelyek a következők:

1. `id`: az igekötős ige egyedi azonosítója

2. `prev`: igekötő

3. `verb`: igelemma

4. `actform`: az igekötős ige szóalakja

5. `argframe`: az igekötős ige lehetséges (automatikus módszerrel kinyert) vonzatkerete

6. `prev_prod`: az igekötő terjeszkedő produktivitása (a PrevLex [2019/06/17-i verziója](https://github.com/kagnes/prevlex/commit/3ea0c759d79d6dde76ccdfc29a10d68d7d635093#diff-e7f337e76c4c22287aee5a15e611acb2bf98753a47d8a7be0ae3134aef463813) alapján)

7. `prev_hapaxes`: az igekötőt tartalmazó hapaxok darabszáma (a PrevLex [2019/06/17-i verziója](https://github.com/kagnes/prevlex/commit/3ea0c759d79d6dde76ccdfc29a10d68d7d635093#diff-e7f337e76c4c22287aee5a15e611acb2bf98753a47d8a7be0ae3134aef463813) alapján)

8. `inputtype`: az ige esetében azonosított szóalkotási mód

9. `suffixtype`: a képző vagy hangzásséma típusa

10. `phonotype`: amennyiben hangzássémába illeszkedik az ige, itt látható a teljes CV-séma

11. `style`: a forrásmondat stílusregisztere

12. `region`: a régió, amelyből a forrásmondat származik

13. `w2v_input`: az automatikus klaszterezés bemeneti szava (ide szóképzéssel létrejött ige esetében az alapszó kerül, pl. _trollkodik_ ⟶ _troll_,  hangzássémás ige esetében ugyanaz, mint az igelemma)

14. `w2v_cluster`: annak a klaszternek az azonosító száma, amelybe a `w2v_input` mező szava került a szóbeágyazás során

15. `clause`: az a tagmondat, amely az igekötős igét tartalmazza

16. `sent`: a teljes mondat, amely az igekötős igét tartalmazza

### Kiegészítő anyag

A `PrevCons.sqlite3` fájl böngészéséhez az `SQLite_útmutató.pdf` nyújt technikai segítséget.

### Licensz

A _PrevCons_ a [GPL-3.0](https://github.com/kagnes/prevcons/blob/master/LICENSE) licensz alá tartozik. Amennyiben felhasználja az adatbázist, kérem, hogy hivatkozza az alábbi publikációk egyikét:

Kalivoda Ágnes (2021). Az igekötők produktív kapcsolódási mintái. _Argumentum 17._ p. 56-82. [https://doi.org/10.34103/ARGUMENTUM/2021/4](https://doi.org/10.34103/ARGUMENTUM/2021/4)

    @article{kalivoda2021,
        title = {Az igekötők produktív kapcsolódási mintái},
        journal = {Argumentum},
        volume = {17},
        year = {2021},
        pages = {56--82},
        author = {Kalivoda, {\'A}gnes},
        DOI = {https://doi.org/10.34103/ARGUMENTUM/2021/4}
    }

Kalivoda Ágnes (2021). [_Igekötős szerkezetek a magyarban._ Doktori értekezés.](https://github.com/kagnes/phd_thesis) Pázmány Péter Katolikus Egyetem, Bölcsészet- és Társadalomtudományi Kar, Nyelvtudományi Doktori Iskola. Budapest. _Megjelenés alatt._

	@phdthesis{kalivoda2021,
		address = {Budapest},
		type = {Doktori értekezés},
		title = {Igekötős szerkezetek a magyarban},
		school = {Pázmány Péter Katolikus Egyetem, Bölcsészet- és Társadalomtudományi Kar, Nyelvtudományi Doktori Iskola},
		author = {Kalivoda, {\'A}gnes},
		year = {2021}
	}

