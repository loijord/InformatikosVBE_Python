# Informatikos VBE užduočių sprendimas su Python

## Apie

Bandant modeliuoti egzaminų uždavinių sprendimus su Python, aiškėja, koks galėtų būti kodo dizainas. Norėdamas gerai išlaikyti egzaminą, abiturientas turėtų ne tik gebėti laikytis tvarkingo kodo rašymo principų, bet ir mokėti remtis kitų parašytu kodu, jei tik jis atitinka šiuos principus. Taip pat eidamas į egzaminą turėti bendrą vaizdą, kokius maždaug algoritmus gali tekti rašyti (mano paties pilnas vaizdas dar nesusidaręs), mokėti išskaidyti algoritmus į aprašomus metodus ir žinoti, kokia kodo struktūra bus naudojama. 

### Kokia galėtų būti kodo struktūra, bendra visiems sprendimams? 

* Pagalvoti, koks duomenų tipas (`tuple`, `list`, `dict` ir pan.) yra tinkamiausias talpinti nuskaitytiems duomenims[1]. Parašyti duomenų nuskaitymui skirtą metodą, pavadintą `read`. Pagrindinė šio metodo dalis galėtų būti [Context Manager](https://book.pythontips.com/en/latest/context_managers.html) sakinys, užrašomas dažniausiai taip: 

```
with open(file, 'r') as f: 
    lines = f.read().split('\n')
```

Jei reikia, galima pasirašyti pagalbinius metodus, tokius kaip `read_blocks`. Read metodą siūlau rašyti taip, kad jame nebūtų jokių pašalinių žingsnių, skirtų duomenų procesinimui (pavyzdžiui laiko vertimo į sekundes). `read` metodas turėtų grąžinti duomenų struktūrą, kuri buvo apgalvota prieš rašant `read` metodą.
* Pagalvoti, kaip atrodo svarbiausios duomenų procesinimo dalys, pamėginti jas įvardyti ir aprašyti atskiruose metoduose. Pvz. 2018 metų uždaviniuose reikėjo tokių algoritmų: laiko reiškimo kitais vienetais, leksikografinio rūšiavimo, sveikosios tuple elementų dalybos, žodyno reikšmių sumažinimo pastoviu dydžiu, dviejų iteruojamų objektų panarinės atimties, minimalaus elementų radimo, elementų grupių sumavimo. Išanalizavus didesnę egzaminų uždavinių apimtį, turėtų pasimatyti, kad algoritmų turinys yra gana ribotas, tad belieka su jais būti susipažinus iš anksto, stengtis kuo geriau įvardinti ir pakomentuoti rašant kodą.
* `write` metodą siūlau daryti panašų į `read`. Nenaudoti jokių procesinimo žingsnių, o tik įrašyti duomenis į failą iš galutinai paruošto tam tikro duomenų tipo. Galima naudoti tokį [Context Manager](https://book.pythontips.com/en/latest/context_managers.html) sakinį:

```
with open(file, 'w') as f: 
    print(text, file=f, end='')
```

### Kaip galima ruoštis kodo rašymo daliai?

Mokytojui galima pasidaryti statistinę analizę, kokie algoritmai ir kaip dažnai pasitaiko programavimo užduotyse. Taip pat rasti būdų lanksčiai kartu su sprendimu pateikti mokiniui ne tik pilną egzamino užduoties sąlygą, bet ir atskiros sprendimo dalies sąlygą. Mokiniui, aišku, per kuo trumpesnį laiką persispręsti kuo paprastesnių algoritmų, panašių į jau minėtus, ir tada jau eiti prie jų komponavimo sprendžiant pilnas, nesuskaidytas uždavinių sąlygas. Pavyzdys, kaip tą daryti - mano repozitorijos `InformatikosVBE_Python` faile `auto_tasking.ipynb`.

Toje pačioje repozitorijoje po truputį atsiranda ir sprendimai (Mano bei dėstytojo Eimučio K.). Savo sprendimuose funkcijų aprašuose naudoju dokumentacines eilutes, kurios yra geras funkcijų komentavimo pavyzdys[2]. Taip pat, norėdamas automatizuoti egzamino uždavinių sprendimo skaidymą, rašau doktestus, bet tai nėra būtina daryti moksleiviui.

Pastabos:
[1] Tenka atsisakyti C++ kalboje įprasto struktūruotų duomenų tipo, nes tokio tipo ekvivalentas Python kalboje reikalauja gebėti aprašinėti atributus ir metodus klasių viduje.
[2] Naudoti `docstrings` vietoj komentarų ateina iš mano programavimo patirties, tačiau tai yra tik mano siūlymas.

## Kaip naudotis šia repozitorija?

* Parsisiųsti ir suinstaliuoti `Anaconda Prompt`
* Parsisiųsti ir suinstaliuoti `git`
* Pasijungti `Anaconda Prompt` terminalą ir suinstaliuoti reikiamus paketus naudojant komandas:

```
pip install nbimporter
conda install jupyter, numpy, pandas
```
    
* Tame pačiame terminale parašyti komandą, skirtą parsisiųsti šią repozitoriją į savo kompiuterį:

```
git clone https://github.com/loijord/InformatikosVBE_Python
```
    
* Kodus galima pasileisti pasijungus vidinį serverį per terminalą:

```
jupyter notebook
```
    
* Egzamino užduočių sąlygos ir sprendimai prieinamos aplankale [`exams`](https://github.com/loijord/InformatikosVBE_Python/tree/main/exams); sprendimai yra saugomi `spr.ipynb` failuose; reikiami failai saugomi tekstiniuose failuose
* Prie sprendimo dalių galima prieiti leidžiant kodą iš [`auto_tasking.ipynb`](https://github.com/loijord/InformatikosVBE_Python/blob/main/auto_tasking.ipynb) programos
* Pastabas galite siųsti paštu `simonas.mamaitis@gmail.com`
    
