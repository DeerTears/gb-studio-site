---
title: "Music"
draft: false
next: "/docs/sound-effects"
nextTitle: "D�wi�k"
---

# Wprowadzenie

GB Studio wewn�trznie korzysta z [GBT Player] (https://github.com/AntonioND/gbt-player), sterownika, kt�ry pobiera pliki .MOD i konwertuje je na format zrozumia�y dla Gameboy. Mo�na u�y� takiego oprogramowania jak [**OpenMPT**](https://openmpt.org/) (g��wnie dla systemu Windows, ale dzia�a r�wnie dobrze przy pomocy Wine na innych systemach) lub [**MilkyTracker**](https://milkytracker.titandemo.org/)(dzia�a natywnie na wielu systemach), w celu utworzenia muzyki trackera .MOD. Oczywi�cie mo�na korzysta� z innego oprogramowania, kt�re jest w stanie edytowa� pliki .MOD, takie jak [**BassoonTracker**](https://www.stef.be/bassoontracker/) (program przegl�darkowy), [**ProTracker**](https://16-bits.org/pt.php), oraz wiele innych.

# Rozpocz�cie pracy, pierwsze kroki

1. Utw�rz pusty projekt GB Studio, znajd� plik `resources/music/template.mod` i otw�rz go za pomoc� wybranego programu (trackera) do obs�ugi plik�w MOD.
   - **Zaleca si� edytowa� ten plik, aby uzyska� dok�adn� reprezentacj� instrument�w, kt�rych mo�na u�y�.**
   - U�ytkownicy MilkyTracker powinni zapisa� ten plik jako plik `.XM`. Zapisanie pliku .mod w MilkyTracker spowoduje jego uszkodzenie. Eksportuj utw�r jako plik .mod za ka�dym razem, gdy chcesz przetestowa� utw�r w grze.
2. Mo�esz usun�� przyk�adowy utw�r, ale ** MUSISZ ** zachowywa� nienaruszone instrumenty/d�wi�ki/przyk�ady.
3. U�yj listy instrument�w pokazanej w dalszej cz�ci tego dokumentu, aby wybra� ��dane d�wi�ki. Zmiana pr�bek w trackerze ** nie ** wp�ynie na to, jak brzmi� w grze.

Po zako�czeniu, dodaj pliki .mod do folderu `resources/music` w swoim projekcie. ** Cz�sto testuj swoj� piosenk� w grze, aby �ledzi� wszelkie s�yszalne r�nice w grze. ** (W grze, podczas gry. NIE w podgl�dzie!)

Nale�y jednak pami�ta�, �e nadal mamy do czynienia z trackerem. Poni�ej zamieszczono kr�tkie podsumowanie/om�wienie, jak program typu tracker funkcjonuje:

```
C-5 01 v64 ...
--- -- --- ---
 |   |  |   |
 |   |  |   +-- Kolumna efekt�w (zmiany g�o�no�ci, akord, panoramowanie itp.)
 |   |  +------ Warto�� g�o�no�ci, dla plik�w .MOD to nie ma znaczenia (wi�kszo�� przyk�ad�w tutaj
 |   |          pomija to i zamiast tego wy�wietla trzy kropki na swoim miejscu).
 |   +--------- Instrument
 +------------- Nuta i oktawa (nuta C w 5 oktawie. My�lnik mo�e by� znakiem #, co oznacza ostr� nut�, np. C#, D#)
```

Kana�y sk�adaj� si� w�a�nie z tego typu wierszy. Rz�dy mog� by� puste lub mog� by� cz�ciowo wype�nione (np. Tylko efektem). W sumie melodie (dla GB) sk�adaj� si� z 4 takich kolumn. 

Dokumentacja ta zawiera bloki kodu, zaczynaj�ce si� od `ModPlug Tracker MOD`. Ca�y ten blok mo�na skopiowa� do programu OpenMPT. Wszelkie dane skopiowane z OpenMPT wygl�daj� tak po wklejeniu do dowolnej aplikacji tekstowej.

# Wa�ne ograniczenia

Plik .MOD mo�e zawiera� ** TYLKO ** 4 kana�y. W przypadku innej ilo�ci (mniej, albo wi�cej) melodie nie b�d� poprawnie konwertowane.

** Ograniczenie te jest narzucone przez sam� konsol� Gameboy, kt�ra przez ca�y czas ma 4 kana�y polifonii.**

Ponadto mo�na u�ywa� tylko niekt�rych instrument�w na niekt�rych kana�ach. Na dole znajduje si� tabela, w kt�rej opisuje gdzie powinny si� znale�� instrumenty. Dzieje si� tak r�wnie� dlatego, �e Gameboy przypisuje instrumenty na podstawie kana�u, kt�ry jest wbudowany w bardzo krzemowy uk�ad i nie mo�na go zmieni�.

| Kana� #     | Rodzaj d�wi�ku    | Zakres nut<sup>1</sup> | Instrumenty | Efekty                |
| ----------- | ----------------  | ---------------------- | ----------- | --------------------- |
| Kana� 1 & 2 | Impulsy (Pulses)  | C3 do B8               | 1-4         | 0, B, C, D, E8, EC, F |
| Kana� 3     | Przebieg(Waveform)| C3 do B8               | 8-15        | 0, E8 i EC            |
| Kana� 4     | Szum    (Noise)   | Tylko C5               | 16-31       | B, C, D, E8, EC, F    |

*<sup>1</sup> ten zakres nut jest przeznaczony dla tracker�w, kt�re wy�wietlaj� swoje nuty w zakresie od C1 do C8, podobnie jak OpenMPT. Je�li u�ywasz trackera, kt�ry mo�e spa�� nawet do C0 (jak MilkyTracker), w�wczas zakresy nut s� o jedn� oktaw� (liczb�) ni�sze (na przyk�ad C3 do B8 w MPT brzmi tak samo jak C2 do B7 w MilkuTracker). *

# Ograniczenia g�o�no�ci

Kana�y 1, 2 i 4 maj� tylko jedn� czwart� zakresu g�o�no�ci obs�ugiwanego przez modu�y trackera (czyli od 0h do 40h). Obs�ugiwane g�o�no�ci s� nast�puj�ce:

`00, 04, 08, 0C, 10, 14, 18, 1C, 20, 24, 28, 2C, 30, 34, 38, 3C`

Wszelkie inne g�o�no�ci zostan� po prostu ograniczone do najbli�szej obs�ugiwanej warto�ci. (np. C40, domy�lna warto�� g�o�no�ci, zostaje ograniczona do C3C)

**G�o�no�ci powy�ej C40 nie s� obs�ugiwane i po konwersji b�d� zachowywa� si� nienormalnie.**

Podczas gdy w module trackera g�o�no�� resetuje si� przy ka�dej nowej nucie, nie zmienia si� ona po konwersji. Za��my nast�puj�cy scenariusz:

```
ModPlug Tracker MOD
|C-502...C40|
|...........|
|...........|
|...........|
|........C..|
|...........|
|E-502......|
```

W trackerze nuta E-5 wznawia si� przy pe�nej g�o�no�ci po efekcie C00.

W grze nie us�yszysz nuty E-5. Wynika to z faktu, �e C00 utrzymuje si� do momentu ustawienia innego efektu `Cxx`. Zasadniczo musisz wykona� nast�puj�ce czynno�ci:

```
ModPlug Tracker MOD
|C-502...C40|
|...........|
|...........|
|...........|
|........C..|
|...........|
|E-502...C40|
```

To dotyczy ka�dej wyst�puj�cej g�o�no�ci. Je�li masz nut� na C24, kt�ra stopniowo spada do, powiedzmy C18, to nadal musisz zresetowa� ka�d� now� nut� do C24 (lub wy�szej, lub ni�szej, w zale�no�ci od tego, co chcesz osi�gn��).

Tymczasem kana� 3 otrzymuje tylko �wier� **tego**, z zakresem g�o�no�ci `00, 10, 20, 40`. Poza tym b�dziesz musia� wprowadzi� instrument i nut�, aby zmiana g�o�no�ci mog�a przynie�� jakikolwiek efekt, chyba �e jest to efekt g�o�no�ci `C00`. Na przyk�ad ponownie:

```
ModPlug Tracker MOD
|C-511...C40|
|...........|
|...........|
|...........|
|........C20|
|...........|
|G-511...C40|

```

Nie us�yszysz �adnej zmiany g�o�no�ci C20 podczas gry, wi�c nale�y doda� nut�, aby zarejestrowa� zmian� g�o�no�ci.

```
ModPlug Tracker MOD
|C-511...C40|
|...........|
|...........|
|...........|
|C-511...C20|
|...........|
|G-511...C40|
```


# Dost�pne instrumenty

Liczby na tej li�cie reprezentuj� podstawowe 10 liczb, kt�re ka�de z tych instrument�w u�ywa w OpenMPT. Obok tych liczb (w nawiasach) znajduje si� podstawowy odpowiednik dla nich (base16) dla u�ytkownik�w MilkyTracker.

Kana�y impulsowe posiadaj� 4 instrumenty (od 1 do 4):

1. 25% impulsu
2. 50% impulsu (fala prostok�tna)
3. 75% impulsu (odwr�cony impuls 25%)
4. 12.5% impulsu

Instrumenty od 5 do 7 s� celowo pozostawiono puste.

Kana�y z przebiegiem (wave) posiadaj� 8 instrument�w (od 8 do 15):

8. Buzzy (Kod �r�d�owy nazywa to "losowym :P")
9. Ringy (przydatne dla SFX)
10. (A) Sync Saw
11. (B) Ring Saw
12. (C) Octave Pulse + Triangle
13. (D) Sawtooth
14. (E) Square
15. (F) Sine

Kana�y szum�w otrzymuj� najwi�cej instrument�w, cz�ciowo ze wzgl�du na to, jak szum dzia�a na Gameboyu. Instrumenty od 16 do 23 u�ywaj� okresowego (zap�tlonego) szumu na r�nych wysoko�ciach, podczas gdy instrumenty od 24 do 32 u�ywaj� szum�w pseudolosowych na r�nych wysoko�ciach.

Pseudonimy i opisy obok tych instrument�w nie s� oficjalne dla GBT Player, maj� na celu pom�c w identyfikacji tych instrument�w akustycznych na pierwszy rzut oka.

Okresowe szumy:

16. (10) "j�kanie" - Kwadratowy impuls oraz impuls o losowej szeroko�ci
17. (11) "rumble" - To samo co przebieg (waveform) tylko �e szybszy
18. (12) "silnik" - To samo co przebieg (waveform) ale znacznie szybszy
19. (13) "niski ton" - Brzmi podobnie jak D5
20. (14) "subharmonia" - Brzmi jak E5 + po�owa dodatkowego wzrostu
21. (15) "�redni ton" - Brzmi jak B5 + po�owa dodatkowego wzrostu
22. (16) "wydzi�k" - Brzmi jak D6 + po�owa dodatkowego wzrostu
23. (17) "wysoki ton" - Brzmi jak D7

Pseudolosowe szumy:

24. (18) "trz�sienie ziemi" - kwadrat z cienkim pulsem o losowych szeroko�ciach impulsu
25. (19) "statek kosmiczny" - To samo co przebieg (waveform) tylko �e szybszy
26. (1A) "ocean" - To samo co przebieg (waveform) ale znacznie szybszy
27. (1B) "dra�ni�cie" - (komentarz autora: chyba wiesz o co chodzi)
28. (1C) "glitch" - Do�� czysta pr�bka szumu bia�ego, niezwi�zana z innymi instrumentami
29. (1D) "wulkan" - Impuls o szybko zmieniaj�cej si� szeroko�ci impulsu
30. (1E) "krzyk" - To samo co przebieg (waveform) tylko �e szybszy
31. (1F) "static" - To samo co przebieg (waveform) ale znacznie szybszy

Nie ma instrument�w czytelnych dla GBT poza 31.

# Efekty

| EFEKT   |     NAZWA        | NOTATKI                                                      |
| :-----: | :-----------:    | :----------------------------------------------------------- |
| **0xy** |     Akord        | Gdzie `x` = druga nuta, `y` trzecia nuta w p�tonach. Podczas korzystania z tego efektu nale�y ustawi� instrument. |
| **Bxx** |     Skok         | Przejd� do okre�lonej pozycji w utworze, `xx`.               |
| **Cxx** |    Go�no��       | Ustawienie g�o�no�ci na xx. Zobacz **ograniczenia g�o�no�ci**, by dowiedzie� si� wi�cej. |
| **Dxx** | Przerwanie wzoru | Wczesne przej�cie do nast�pnego wzoru, gdzie `xx` oznacza rz�d, do kt�rego powinien przej�� w nast�pnym wzorze. U�ycie tego w ostatnim wzorze spowoduje uszkodzenie utworu poprzez odczytanie �mieciowych danych poza utworem. |
| **E8x** |  Panoramowanie   | Ustawienie panoramowania na `x`. `0-3` = w lewo,` 4-B` = �rodek, `C-F` = w prawo |
| **ECx** |   Wytnij nut�    | Wyci�cie nuty po `x` przej�ciach. `0 < x < szybko��-1`              |
| **Fxx** |  Ustaw szybko��  | Ustawia pr�dko�� utworu na `xx`. Prawid�owe warto�ci to od `01` do `1F`. Warto�� reprezentuje, ile ramek utw�r powinien poczeka� przed przej�ciem do innego wiersza. Ustawienie pr�dko�ci BPM nie ma wp�ywu na konwersj�. |

## Tabela szybko�ci

| Fxx warto�� (w trackerze) | BPM (w trackerze) | BPM (w grze) |
| ---------------------- | ---------------- | ------------- |
| **F01<sup>1</sup>**    | 750 BPM          | 900 BPM       |
| **F02<sup>1</sup>**    | 375 BPM          | 450 BPM       |
| **F03<sup>1</sup>**    | 250 BPM          | 300 BPM       |
| **F04<sup>1</sup>**    | 187.5 BPM        | 225 BPM       |
| F05                    | 150 BPM          | 150 BPM       |
| F06                    | 125 BPM          | 128.57 BPM    |
| F07                    | 107.14 BPM       | 112.50 BPM    |
| F08                    | 93.75 BPM        | 100 BPM       |
| F09                    | 83.33 BPM        | 90 BPM        |
| F0A                    | 75 BPM           | 81.82 BPM     |

To nie jest pe�na tabela, to tylko kilka najwy�szych pr�dko�ci. S�u�y tutaj do podkre�lenia niekt�rych rozbie�no�ci pr�dko�ci, cho� niewielkich, aby nie by�y bardzo zauwa�alne, z wyj�tkiem warto�ci oznaczonych 1.

Mo�na zauwa�y�, �e warto�� efektu F po przeliczeniu na dziesi�tne jest tylko dzielnikiem pr�dko�ci. Na przyk�ad F03 dzieli BPM przez 3 (�750/3 = 250� lub �900/3 = 300�).

Ze wzgl�du na konfiguracj� GB Studio, efekt F05 60 Hz, kt�ry da�by 180 BPM w grze, jest tutaj niemo�liwy.

* Podczas gdy nie jest w GB Studio, GBT ma flag� o nazwie `-speed`, kt�ra b�dzie obs�ugiwa� BPM inaczej, co wymaga�oby efekt�w F96 dla ka�dej pr�dko�ci, poniewa� nie b�dzie obs�ugiwa� �adnych wewn�trznych konwersji, aby zbli�y� pr�dko��. To jest pow�d, dla kt�rego F01 do F04 wymagaj� F96 w obu trybach, nie ma odpowiednika w szybko�ci �ledzenia. *

**1. Warto�ci oznaczone 1 wymagaj� dodatkowego efektu F96, aby utw�r brzmia� bli�ej pr�dko�ci po przekonwertowaniu lub ustawienie BPM utworu na 150. ** Ten efekt F96 mo�na usun��, gdy sko�czysz z utworem i nie b�dzie jakakolwiek r�nica, poniewa� GBT ignoruje to - to jest tylko tutaj, aby ustawi� BPM na co� bli�szego wersji w grze.

# Porady i triki

W tej sekcji zostanie om�wione kilka sztuczek, kt�rych mo�na u�ywa� z GBT, aby utw�r brzmia� lepiej ni� powinien.

### **1. Wysoka szybko��**

U�ywaj�c F01 do F04, mo�esz osi�gn�� znacznie wi�ksz� ziarnisto��, je�li chodzi o zmian� g�o�no�ci i tworzenie r�nego rodzaju d�wi�k�w. Oznacza to, �e przy wystarczaj�co du�ej pr�dko�ci mo�esz tworzy� bardziej zr�nicowane cia�a dla d�wi�k�w, z rodzajami obwiedni lub wyszukanymi efektami (jak echa 1-kana�owe, kt�re om�wi� tutaj za chwil�).

Ta sztuczka oznacza, �e przechodzisz od perkusji, kt�ra brzmi s�abo i prymitywnie, do czego� bardziej imponuj�cego.

Oto przyk�ad perkusji przy pr�dko�ci F02, kt�ry mo�e brzmie� dla ciebie dobrze.

```
ModPlug Tracker MOD
|C-526...C40
|C-527...C28
|........C20
|........C18
|........C10
|........C08
|........C04
|........C..
(to jest na kanale1 szumu)
```

Je�li jest d�u�szy ni� potrzebujesz, po prostu przytnij go, zaczynaj�c od do�u.

Mo�esz go r�wnie� u�y� do d�wi�k�w i innych rzeczy, takich jak kr�tkie nuty staccato lub zanikaj�ce flety.

**Je�li to zrobisz, pami�taj, �e sprz�t GB Sound ma irytuj�cy b��d, kt�ry resetuje faz� ka�dej fali na zestawie g�o�no�ci, co oznacza, �e mo�esz uzyska� drapliwy szum w kilku emulatorach, a tak�e prawdziwej konsoli GB.**

### **2. Echo w jednym kanale**

Dzia�a to na wi�kszo�ci pr�dko�ci. Jest to przydatne, gdy potrzebujesz melodii na tle powtarzaj�cego si� echa, frazy lub cokolwiek innego.

Aby to zilustrowa�, spr�buj� to zilustrowa� w ten spos�b, zamiast u�ywa� uk�adu trackera:

```
A _ B _ C _ E _ G _ E _ C _ B _ 
Bez 1kana�u Echo

    +-----+ +-----+ +-----+
A _ B a C b E c G e E g C e B c 
+-----+ +-----+ +-----+ +-----+
     
Z 1kana�em Echo (nuty posiadaj�ce ma�e litery s� echami)
```

Zauwa�, jak ka�da ma�a litera ma posta� 3 krok�w za g�o�niejszym kuzynem? Tak dzia�a sztuczka. Maj�c kr�tsze nuty, kt�re na ka�dym kroku maj� kolejn� cichsz� nut�, kt�ra jest daleko w tyle, uzyskujesz fajny efekt echa.

Nie potrafi� tego dobrze wyja�ni� za pomoc� tekstu, wi�c polecam sprawdzi� ten film przez **explod2a03** opisuj�cy, jak ta sztuczka dzia�a z lepszym przyk�adem i faktycznym d�wi�kiem:  https://www.youtube.com/watch?v=6GI9gngTn_Y

Najlepszym sposobem, aby to zrobi� w module trackera, jest skorzystanie z kana�u, kt�rego nie u�ywasz tymczasowo, skopiowanie sekwencji nutek, op�nienie go o 3 (lub tyle potrzebnych) rz�d�w, a nast�pnie klikni�cie prawym przyciskiem myszy zaznaczenia i klikni�cie ''Wzmocnienie...'' i ustawienie amplitudy na warto�� ni�sz� ni� 50%.

After that, you should have both channels "alternate". Select the entirety of the channel with the echoes (from top to bottom), go to the channel you want to merge the echoes with, right click, go to "Paste special", then click "Mix paste" (This should have a shortcut, might want to learn it as it can be fairly useful).Nast�pnie oba kana�y powinny by� ''alternatywne''. Wybierz ca�y kana� z echami (od g�ry do do�u), przejd� do kana�u, z kt�rym chcesz scali� echo, kliknij prawym przyciskiem myszy, przejd� do ''Wklej specjalnie'', a nast�pnie kliknij ''Wklej mix'' (ta opcja raczej posiada skr�t , mo�esz si� tego nauczy�, poniewa� mo�e by� do�� przydatne).

### 3. Szybkie koperty g�o�no�ci

�pieszysz si�? Nie ma problemu, ta prosta sztuczka stworzy koperty liniowe:

1. Wybierz dwie warto�ci g�o�no�ci / warto�� C dw�ch oddzielnych nut (w tym samym kanale) i wszystko pomi�dzy
2. Kliknij prawym przyciskiem myszy i najed� kursorem na ''Interpoluj'' (Interpolate)
3. Kliknij ''Kolumn� efekt�w'' (Effect column)
4. Gotowe!

Mo�esz si� zastanawia�, jak to zabrzmi w grze; c�, zabrzmi to tak blisko, jak to mo�liwe. G�o�no�ci, kt�rych nie mo�e odtworzy�, po prostu ogranicz� go do najbli�szych, kt�re mog� odtwarza�.

# Cz�sto zadawane pytania

**Q: Czy mog� u�y� plik�w mp3s?**

A: Nie.

**Q: Czy mog� u�y� tego pliku .MOD, znalezionego w internecie?**

A: Najprawdopodobniej nie. Tw�j plik .MOD musi by� specjalnie sformatowany w ramach tego, co otrzymujesz w `template.mod`, z wy�ej wymienionymi ograniczeniami.

**Q: Jak zatrzyma� odtwarzanie nuty?**

A: Albo ca�kowicie u�yj innej nuty, albo je�li chcesz j� wyciszy�, u�yj efektu `C00`.

**Q: M�j utw�r brzmi ca�kowicie �le po zbudowaniu! Dlaczego?**

A: Jest wiele powod�w, dla kt�rych mo�e tak by�. **Upewnij si�, �e tw�j utw�r jest zgodny ze wszystkim powy�szymi zasadami** (w szczeg�lno�ci upewnij si�, �e u�ywasz tylko obs�ugiwanych efekt�w, przestrzegasz przydzia��w kana��w i nie przekraczasz okre�lonych cz�stotliwo�ci).

Je�li u�ywasz ** MilkyTracker **, pami�taj, �e mo�e to uszkodzi� d�wi�k pliku .mod. Aby obej�� ten problem, zapisz jako `.XM`, jego natywnie obs�ugiwany format, a kiedy sko�czysz z utworem, wyeksportuj go jako utw�r .mod i wypr�buj w GB Studio.

**Q: Szybko�� mojego utworu jest nieprawid�owa! Jest znacznie szybsza w grze ni� w trackerze!**

A: Je�li u�ywasz efektu `Fxx` o warto�ci ** wy�szej ni� `F05` **, musisz pami�ta� o konwersjach od 50 Hz do 60 Hz. Format .mod zosta� pierwotnie opracowany dla komputer�w europejskich, kt�re dzia�a�y z cz�stotliwo�ci� 50 Hz, a Gameboy - z cz�stotliwo�ci� 60.** Aby to z�agodzi�, ustaw BPM na 150 zamiast na 125. **Je�li u�ywasz OpenMPT ( kt�ry nie mo�e ustawi� BPM z jakiegokolwiek powodu), efekt `F96` w utworze za�atwi spraw� (cho� zastosuj go jak najwcze�niej).

**Q:Czy mog� odtworzy� ten klip g�osowy/efekt d�wi�kowy/cokolwiek innego?**

A: Nie, nie na GBT. 

LSDj i bardziej zaawansowane sterowniki d�wi�ku dost�pne dla Gameboy obs�uguj� odtwarzanie pr�bek, ale zrobienie tego wymaga przeniesienia du�ej ilo�ci danych w kr�tkim czasie (oznacza to, �e w tym czasie mo�na odtwarza� tylko muzyk�).

**Q: Czy mog� u�y� innego narz�dzia do pisania muzyki?**

A: Je�li narz�dzie mo�e natywnie eksportowa� do .mod, spr�buj! Je�li nie, musisz przepisa� to, co napisa�e� do modu�u trackera, kt�ry mo�e zapisa� pliki .mod.

**Q: Czy mog� u�y� pliki MIDI?**

A: OpenMPT mo�e otwiera� pliki MIDI, ale b�dziesz musia� ci�ko pracowa�, aby przyci�� go do zaledwie 4 kana��w, z ograniczonymi tonami. Cz�sto �atwiej jest po prostu wprowadzi� dane r�cznie, poniewa� masz du�o wi�ksz� kontrol� nad wszystkim i masz lepszy obraz wszystkiego, co si� dzieje, je�li to zrobisz.

**Q: To troch� k�opotliwe. Jakie mam alternatywy?**

A: Na dzie� uko�czenia tego dokumentu, nie znam. Mo�liwe, �e w przysz�o�ci ludzie b�d� mogli tworzy� niestandardowe trackery lub narz�dzia dla GB Studio, ale do tego czasu jest to jedyny spos�b, w jaki mo�emy tworzy� muzyk� dla gier GB Studio.

Mo�esz zacz�� tworzy� utw�r w zupe�nie innym formacie ni� GB za pomoc� OpenMPT lub swojego trackera, poniewa� to lepiej nauczy ci�, co tak naprawd� robi tracker, przynajmniej moim zdaniem...

W sekcji Porady znajduje si� link, jak rozpocz�� korzystanie z OpenMPT, sugeruj� przeczytanie go!

**Q: U�y�em efektu D00 na moim ostatnim wzorze, aby powr�ci� do pierwszego, ale podczas gry odgrywa b��d po tym, jak raz zap�tli si�?**

A: U�yj efektu `Bxx`. U�ycie efektu D00 na ostatniej klatce spowoduje, �e GBT pomy�li, �e poza utworem jest wi�cej danych, co spowoduje, �e odczyta �mieciowe dane.

**Q: Korzystam z OpenMPT, a niekt�re nuty s� czerwone i brzmi� znacznie wy�ej/ni�ej ni� powinny!**

A: Przejd� do zak�adki ''Og�lne'' pod przyciskami Nowy plik, Otw�rz i Zapisz. Kliknij du�y przycisk obok pola ''Nazwa'' z napisem ''MOD (ProTracker), 4 kana�y''. Gdy ju� tam b�dziesz, wy��cz zar�wno ** Tryb ProTracker 1/2 (MOD) **, jak i ** Granice cz�stotliwo�ci Amigi. ** Jest tak dlatego, �e format tutaj jest przeznaczony do u�ytku z lini� komputer�w Amiga (tam w�a�nie by� wykorzystany), kt�ry ma ograniczenia cz�stotliwo�ci.

**Q: Utw�r zaczyna si� od jaki� �mieci.**

A: Je�li nie u�ywasz dw�ch pierwszych kana��w, wycisz je z efektem `C00`.

**Q: Czy mog� odtwarza� efekty d�wi�kowe?**

A: Jeszcze nie. Jedynym sposobem, w jaki mo�esz odtwarza� efekty d�wi�kowe, jest odtwarzanie go jako pliku muzycznego, ale to zabije bie��c� muzyk� i b�dziesz musia� j� ponownie uruchomi� po zako�czeniu odtwarzania efektu d�wi�kowego.

## Porady

- **Pami�taj, aby cz�sto zapisywa�, a tak�e tworzy� kopie zapasowe plik�w.** Jest to wa�ne we wszystkim, co robisz i warto o tym wspomnie�.
- [**je�li utkniesz, popro� o pomoc na serwerze Discord, w `# music-help`. **] (https://discord.gg/v9xAJCJ) Zwykle jest kilka os�b, kt�re ch�tnie pomog� w wi�kszo�ci przypadk�w.
- **Cz�sto wypr�buj swoj� muzyk� w swojej grze. ** Rzeczy nie brzmi� 1: 1, a wbudowany podgl�d po prostu odtwarza plik .mod zamiast budowa� muzyk� i wy�wietla� jej podgl�d.
- **Trzymaj si� prostoty!** Nie wskakuj do tego, pr�buj�c na�ladowa� to, co zrobi�o kilku artyst�w z LSDj lub jakimkolwiek innym narz�dziem, po prostu utkniesz.
- **Nie b�j si� pora�ki. ** Rozumiem, �e to rodzaj nieodpowiedniej wskaz�wki, ale to wa�ne. Twoja pierwsza piosenka nie b�dzie dobra i to jest w porz�dku. Oczywi�cie, nie uda ci si�, ale zdob�dziesz tak�e wiedz� na temat tego, co mog�e� zrobi� �le lub jak chcesz kontynuowa� swoj� przygod�.
- **OpenMPT ma instrukcj�, kt�ra pomo�e Ci zacz��. ** [Oto link] (https://wiki.openmpt.org/Tutorial:_Getting_Started), przeczytaj, je�li utkniesz (lub po prostu popro� o pomoc)
- [**Rzu� okiem, albo przeczytaj dokumentacj� odtwarzacza GBT. **] (https://github.com/AntonioND/gbt-player)
