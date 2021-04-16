# PrevCons – igekötős szerkezetek adatbázisa

A _PrevCons_ (Preverb Constructions) egy nyílt hozzáférésű adatbázis, amely 21.038 igekötős hapaxot tartalmaz azok lehetséges vonzatkeretével együtt. Ezen felül számos meta-adat érhető el benne a hapaxok morfológiai szerkezetéről, szemantikájáról és konkrét szövegbeli előfordulásáról. Az adatbázisról a következő tanulmány nyújt részletes tájékoztatást: _(hamarosan)_.

### Az erőforrás szerkezete

A _PrevCons_ elérhető TSV fájlként (`PrevCons.tsv`) és SQLite adatbázisként is (`PrevCons.sqlite3`). Ezek pusztán a formátumukat tekintve térnek el egymástól, tartalmilag megegyeznek. A két formátumot az indokolja, hogy a számítógépes feldolgozáshoz praktikusabb lehet a TSV, a kézi adatelemzéshez pedig az SQLite-alapú megoldás. Az erőforrás 16 oszlopból áll, amelyek a következők:

1. `id`: az igekötős ige egyedi azonosítója

2. `prev`: igekötő

3. `verb`: igelemma

4. `actform`: az igekötős ige szóalakja

5. `argframe`: az igekötős ige lehetséges (automatikus módszerrel kinyert) vonzatkerete

6. `prev_prod`: az igekötő terjeszkedő produktivitása

7. `prev_hapaxes`: az igekötőt tartalmazó hapaxok darabszáma

8. `inputtype`: az ige esetében azonosított szóalkotási mód

9. `suffixtype`: a képző vagy hangzásséma típusa

10. `phonotype`: amennyiben hangzássémába illeszkedik az ige, itt látható a teljes CV-séma

11. `style`: a forrásmondat stílusregisztere

12. `region`: a régió, amelyből a forrásmondat származik

13. `w2v_input`: az automatikus klaszterezés bemeneti szava (ide szóképzéssel létrejött ige esetében az alapszó kerül, pl. _trollkodik_ ⟶ _troll_,  hangzássémás ige esetében ugyanaz, mint az igelemma)

14.	`w2v_cluster`: annak a klaszternek az azonosító száma, amelybe a `w2v_input` mező szava került a szóbeágyazás során

15.	`clause`: az a tagmondat, amely az igekötős igét tartalmazza

16.	`sent`: a teljes mondat, amely az igekötős igét tartalmazza

### Kiegészítő anyag

A `PrevCons.sqlite3` fájl böngészéséhez az `SQLite_útmutató.pdf` nyújt technikai segítséget.

### Licensz

A _PrevCons_ a [GPL-3.0](https://github.com/kagnes/prevcons/blob/master/LICENSE) licensz alá tartozik. Felhasználása esetén az alábbi publikáció hivatkozandó:

_(hamarosan)_
