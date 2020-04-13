---
title: "Skryptowanie (polecenia zdarzenia)"
draft: false
next: "/docs/custom-events"
nextTitle: "W�asne zdarzenia"
---

Skrypty umo�liwiaj� dynamiczne kontrolowanie cz�ci gry na podstawie interakcji gracza. Za ich pomoc� mo�na ��czy� sceny, prowadzi� dialogi z postaciami albo tworzy� scenki przerywnikowe.

Kiedy jest zaznaczona scena, aktor lub rozruch w _�wiecie gry_, to _boczny pasek_ programu b�dzie zawiera� przycisk _dodaj polecenie_ w prawym dolnym rogu. Przy pomocy _dodaj polecenie_ mo�na przypisa� polecenia do wykonania. Je�li polecenia s� ju� wymienione w tym miejscu, s� one przeprowadzane od g�ry do do�u, jedno po drugim.

Podczas ustalenia polece� dla aktor�w, trzeba pami�ta�, �e polecenia zostan� uruchomione w momencie gdy gracz stanie obok aktora i naci�nie przycisk interakcji. Polecenia w zdarzenia typu _rozruch_, zostan� uruchomione w momencie, gdy gracz stoi na danym polu rozruchu, co mo�e okaza� si� przydatne podczas tworzenia drzwi mi�dzy scenami. Polecenia, kt�re s� ustalane w scenach, s� uruchamiane natychmiastowo po za�adowaniu danej sceny. Opcja ta przydatna jest do konfiguracji sceny na podstawie warto�ci zmiennych lub do rozpocz�cia scenki przerywnikowej.

## Dodaj polecenie

Po naci�ni�ciu przycisku _dodaj polecenie_ zostanie wy�wietlone rozwijana lista menu, zawieraj�ca polecenia do dodania. W momencie pisania na klawiaturze nazwy polecenia, zostanie uruchomiony filtr i zostan� wy�wietlone tylko te polecenia, kt�re b�d� zawiera�y wprowadzone has�a kluczowe. Mo�na te� przewija� pe�n� list� w celu znalezienia odpowiedniego polecenia. W celu dodania polecenia do skryptu zdarzenia, nale�y je zaznaczy� za pomoc� myszki lub pod�wietli� przy pomocy klawiatury i nacisn�� klawisz _Enter_.  

## Kopiuj / Wklej

Obok nazwy zdarzenia, po prawej stronie widnieje strza�ka w d�. Jej rozwini�cie powoduje wy�wietlenie menu kontekstowego, przy pomocy kt�rego mo�na skopiowa� polecenie do schowka. Klikni�cie strza�ki w d� na innym poleceniu pozwoli wklei� polecenie ze schowka przed lub po wybranym poleceniu, lub po prostu pozwoli to na wklejenie warto�ci z pierwszego polecenia do drugiego.

<span class="new">Nowo�� od wer. 1.2.0</span>

Mo�na tak�e przytrzyma� klawisz _Alt_, aby zmieni� wszystkie przyciski _dodaj polecenie_ na _wklej polecenie_, co pozwala na �atwe wklejenie skopiowanych polece� do polece� kontrolnych z rozga��zieniem.

## Polecenia tekstowe

- **Tekst: wiadomo��**  
Polecenie wy�wietla ramk� z dialogiem na dole ekranu. Jedna wiadomo�� maksymalnie mo�e zawiera� trzy wiersze, ka�dy wiersz mie�ci 18 znak�w (czyli ��cznie mo�na mie� 52 znaki). Prawdopodobnie b�dzie to jedno z najcz�stszych u�ywanych polece� skryptowych do interakcji z aktorami w grze.  
Gdy jest wy�wietlony tekst, okno dialogowe jest wy�wietlane od do�u do g�ry, po czym nast�puje wy�wietlenie tekstu metod� literka po literce i po interakcji gracza okno dialogowe znika przesuwaj�c si� po prostu w d�.
  <img src="/img/events/display-dialogue.png" class="event-preview" />
  <img src="/img/events/display-dialogue-preview.png" class="event-preview" />
  <br />

  - Przy pomocy przycisku _+_ mo�esz utworzy� sekwencj� dialogu, kt�ra zostanie zamkni�ta dopiero po wy�wietleniu ostatniej wiadomo�ci.  
    <span class="new">Newo�� od wer. 1.2.0</span>
  - Mo�esz wy�wietli� warto�� dowolnych zmiennych w polu tekstowym, u�ywaj�c identyfikatora zmiennej pokazanego w selektorze zmiennych (np. `$L0$` dla zmiennej lokalnej 0 i `$182$` dla zmiennej globalnej 182).
  - Mo�esz opcjonalnie wy�wietli� grafik� (awatara) po lewej stronie okna dialogowego, klikaj�c w opcj� _dodaj grafik� (awatara)_ i wybieraj�c obraz do u�ycia. Mo�esz wybra� dowoln� grafik� z _obiekt�w_ w grze. Grafika musi zawiera� tylko jedn� klatk� (`16px` x` 16px`). Ustawienie awatara zmniejszy liczb� dost�pnych znak�w w linii do 16 we wszystkich liniach.

- **Tekst: poka� wyb�r**  
  Polecenie przedstawia dwie opcje, gracz mo�e dokona� wyboru. Wybrana zmienna zostanie ustawiona na warto�� _Prawda_, je�eli zostanie wybrana pierwsza opcja, i na _Fa�sz_, je�li wybrana zostanie druga opcja.
  <img src="/img/events/display-multiple-choice.png" class="event-preview" />
  <img src="/img/events/display-multiple-choice-preview.png" class="event-preview" />

- **Tekst: wy�wietl menu** <span class="new">Newo�� od wer. 1.2.0</span>  
  Polecenie wy�wietla menu zawieraj�ce wiele opcji i ustawia okre�lon� zmienn� na warto�� wybranej opcji. Maksymalna ilo�� znak�w dla ka�dej pozycji menu, wynosi `6` znak�w.
  Opcja ta pozwala na wybranie schematu wyboru, `Menu` (pokazane poni�ej), wy�wietla opcje jako pojedyncza kolumna po prawej stronie ekranu gry. `Dialog` wy�wietla okno dialogowe na pe�nej szeroko�ci ekranu z dwoma kolumnami. Opcjonalnie mo�na ustawi� przycisk `B`, aby zamkn�� menu, ustawiaj�c zmienn� na `0`, a tak�e mo�na sprawi�, �e ostatni element menu zwr�ci `0` po wybranej opcji.
  <img src="/img/events/menu.png" class="event-preview" />
  <img src="/img/events/menu-preview.png" class="event-preview" />

- **Text: szybko�� animacji**  
  Polecenie odpowiada za ustawienia wy�wietlanego tekstu. Nale�y ustawi� szybko�� wy�wietlenia okna wiadomo�ci, szybko�� znikni�cia okna wiadomo�ci, oraz szybko�c wy�wietlania tekstu.
  <img src="/img/events/text-animation-speed.png" class="event-preview" />

## Polecenia sceny

- **Scena: zmie� scen� (teleport)**  
  Przej�cie do nowej sceny, z okre�lonymi wsp�rz�dnymi i kierunkiem dla gracza. Do zdarzenia zostanie dorysowana niebieska linia ��cz�ca zdarzenie teleportu z jego miejscem docelowym, gdzie na ko�cu zostanie umieszczona ikona wraz z kierunkiem obrotu <img src="/img/screenshots/destination-end.png" style="height:12px"/>. Istnieje mo�liwo�� przeci�gni�cia tej ikony mi�dzy scenami w celu dokonania modyfikacji zdarzenia.
  <img src="/img/events/switch-scene.png" class="event-preview" />
  <img src="/img/events/switch-scene-preview.png" class="event-preview" />

- **Scena: zapisz scen� do pami�ci**  
  Polecenie przechowuje aktualn� scen� jak i po�o�enie gracza w swojej pami�ci. Opcja ta pozwala na p�niejszy powr�t do tej dok�adnej lokalizacji za pomoc� polecenia _scena: wczytaj scen� z pami�ci_. Polecenie te b�dzie przydatne podczas tworzenia wszelkich system�w menu, kt�re wymagaj� przej�cia na inn� scen� (scen� menu). Wypada�o by przed poleceniem teleportu, wprowadzi� w�a�nie polecenie do zapisania sceny do pami�ci, po to, aby gracz m�g� powr�ci� na swoje miejsce przy pomocy polecenia _wczytaj scen� z pami�ci_.
  <img src="/img/events/scene-stack-push.png" class="event-preview" />

- **Scena: wczytaj scen� z pami�ci**  
  Przej�cie do ostatniej zapisanej sceny, kt�ra znajduje si� w pami�ci przy u�yciu okre�lonej pr�dko�ci przenikania. Poprzednia scena zostanie nast�pnie usuni�ta z pami�ci, wi�c przy nast�pnym u�yciu tego zdarzenia nast�pi przej�cie do sceny wcze�niejszej. 
  <img src="/img/events/scene-stack-pop.png" class="event-preview" />

- **Scene: wczytaj pierwsz� z pami�ci**  
  Przej�cie do pierwszej sceny zapisanej w pami�ci, na przyk�ad je�li masz wiele poziom�w scen menu, mo�esz u�y� jej, aby natychmiast powr�ci� do sceny gry. To wydarzenie spowoduje opr�nienie pami�ci z zapisanych scen.
  <img src="/img/events/scene-stack-pop-all.png" class="event-preview" />

- **Scena: wyczy�� stan pami�ci**  
  Czy�ci pami�� ze scen, aby nie mo�na by�o przywr�ci� do poprzednich scen.
  <img src="/img/events/scene-stack-clear.png" class="event-preview" />

## Polecenia zmiennej

Ka�dy projekt posiada 512 zmiennych, kt�re mo�na wsp�dzieli� we wszystkich skryptach w grze. <span class="new">Nowo�� od wer. 1.2.0</span> Dodatkowo ka�dy _aktor_, _rozruch_ i _scena_ posiadaj� 4 lokalne zmiennej, do kt�rych dost�p ma tylko ten konkretny byt (czyli tzw. zmienne w�asne). Zmienne lokalne (zmienne w�asne) s� przydatne do �ledzenia stanu specyficznego tego zdarzenia, np. Ile razy odby�a si� rozmowa z dan� postaci�, albo czy skrzynia jest otwarta lub zamkni�ta.

- **Zmienna: ustaw na 'Prawda'**  
  Ustawienie warto�ci wybranej zmiennej na _Prawda_.  
  <img src="/img/events/variable-true.png" class="event-preview" />

- **Zmienna: ustaw na 'Fa�sz'**  
  Ustawienie warto�ci wybranej zmiennej na _Fa�sz_.  
  <img src="/img/events/variable-false.png" class="event-preview" />

- **Zmienna: ustaw warto��**  
  Ustawienie wybranej zmiennej na konkretn� warto�� liczbow�.  
  <img src="/img/events/variable-value.png" class="event-preview" />

- **Zmienna: zwi�ksz o 1**  
  Polecenie zwi�kszy warto�� okre�lonej zmiennej o jeden, maksymalna warto�� wynosi _255_. Je�eli poprzednia warto�� wynosi�a _Fa�sz_, to teraz b�dzie to _1_ (a tak�e _Prawda_). Je�eli poprzednia warto�� by�a _Prawda_, to teraz b�dzie _2_.
  <img src="/img/events/variable-increment.png" class="event-preview" />

- **Zmienna: zmniejsz o 1**  
  Polecenie zmniejszy warto�� okre�lonej zmiennej o jeden, minimalna warto�� wynosi _0_. Je�eli poprzednia warto�� wynosi�a _prawda_, to teraz b�dzie to _0_ (a tak�e _Fa�sz_).
  <img src="/img/events/variable-decrement.png" class="event-preview" />

- **Zmienna: funkcje matematyczne**  
  Polecenie umo�liwia wykonanie r�nych funkcji matematycznych na zmiennej w celu manipulacji jej warto�ci�. Mo�na dodawa�, odejmowa�, mno�y�, dzieli�, a tak�e u�y� funkcji modulo (reszty z dzielenia). Jako warto�� mo�e pos�u�y� si� konkretna liczba, liczba losowa, albo liczba zawarta w innej zmiennej.
  _Uwaga:_ Zasi�g warto�ci zmiennej wynosi: `0-255`. Je�eli warto�� wyjdzie po za zasi�g, to warto�� zostani� zap�tlona (np. `254,255,0,1,2[...]`).  
  <img src="/img/events/variable-math.png" class="event-preview" />

- **Zmienna: ustaw flag�** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Ustaw warto�� zmiennej, w��czaj�c pojedyncze bity liczby 8-bitowej. Umo�liwia zapisanie 8 warto�ci prawda / fa�sz w jednej zmiennej. Ustawienie flag zast�pi poprzedni� warto�� zmiennej.
  <img src="/img/events/variable-flags-set.png" class="event-preview" />

- **Zmienna: dodaj flag�** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie ustawia zaznaczone flagi jako _Prawda_ na wybranej zmiennej. Wszystkie flagi, kt�re s� nie zaznaczone, b�d� przetrzymywa�y dalej swoj� poprzedni� ustalon� warto��.
  <img src="/img/events/variable-flags-add.png" class="event-preview" />

- **Zmienna: czy�� flagi** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie ustawia zaznaczone flagi jako _Fa�sz_ na wybranej zmiennej. Wszystkie flagi, kt�re s� nie zaznaczone, b�d� przetrzymywa�y dalej swoj� poprzedni� ustalon� warto��.
  <img src="/img/events/variable-flags-clear.png" class="event-preview" />

- **Zmienna: resetuj wszystkie zmienne do 'Fa�sz'**  
  Polecenie resetuje wszystkie zmienne, kt�re zosta�y u�yte w projekcie i ustawia je na warto�� _Fa�sz_.  
  <img src="/img/events/variable-reset-all.png" class="event-preview" />

## Polecenia warrunku (kontrolne)

- **Warunek: zmienna jest 'Prawda'**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli podana zmienna jest ustawiona jako _Prawda_.
  <img src="/img/events/if-true.png" class="event-preview" />

- **Warunek: zmienna jest 'Fa�sz'**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli podana zmienna jest ustawiona jako _Fa�sz_.
  <img src="/img/events/if-false.png" class="event-preview" />

- **Warunek: zmienna por�wnuje si� do warto�ci**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli podana zmienna spe�nia zasad� tak� jak "jest r�wna", "wi�ksza", "mniejsza" itp. do podanej warto�ci.
  <img src="/img/events/if-variable-value.png" class="event-preview" />

- **Warunek: zmienna por�wnuje si� do zmiennej**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli podana zmienna spe�nia zasad� tak� jak "jest r�wna", "wi�ksza", "mniejsza" itp. do podanej zmiennej.
  <img src="/img/events/if-variable-variable.png" class="event-preview" />

- **Warunek: zmienna ma flag�** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli flaga wybranej zmiennej jest ustawiona jako _Prawda_.
  <img src="/img/events/if-variable-flag.png" class="event-preview" />

- **Warunek: wci�ni�ty przycisk joypada**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli w danym momencie wykonywalnego skryptu zostan� naci�ni�te podane klawisze. _Uwaga_: Polecenie te nie czeka na wci�ni�cie przez u�ytkownika, skrypt jest po prostu wykonywalny. Je�eli skrypt ma poczeka� na wci�ni�cie przycisku, to nale�y u�y� polecenia _Przycisk Joypad: czekaj na przycisk_. Mimo tego, skrypt jest wykonany tylko raz. Je�eli chcesz uzyska� efekt, by skrypt zosta� uruchamiany za ka�dym razem, to zalecane jest zastosowanie polecenia _Przycisk Joypad: przypisz zdarzenie_. Conditionally execute part of the script if the specified joypad input is currently pressed. Will not wait for user input so use directly after a _Joypad Input: Pause Script Until Pressed_ event if waiting is required. Event will only execute once, if you wish to run a script every time a button is pressed use _Joypad Input: Attach Script To Button_ instead.
  <img src="/img/events/if-joypad-input.png" class="event-preview" />

- **Warunek: wsp�rz�dne aktora**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli wskazany aktor znajdzie si� w okre�lonej pozycji (X i Y) na scenie.
  <img src="/img/events/if-actor-position.png" class="event-preview" />

- **Warunek: kierunek obrotu aktora**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli wskazany aktor b�dzie zwr�cony w danym kierunku. 
  <img src="/img/events/if-actor-direction.png" class="event-preview" />

- **Warunek: stan gry zapisano**  
  Polecenie warunkowe, kt�re wykona polecenie znajduj�ce si� wewn�trz skryptu, je�eli istnieje zapisany stan gry.
  <img src="/img/events/if-game-saved.png" class="event-preview" />

- **Prze��cznik** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie warunkowe zawieraj�ce wiele opcji w zale�no�ci od warto�ci okre�lonej zmiennej. Najpierw nale�y wybra� ile opcji ma zosta� por�wnane do zmiennej, a nast�pnie ustawi� warto�� do por�wnania i jakie polecenia maj� zosta� wykonane po dopasowanej warto�ci.
  <img src="/img/events/switch.png" class="event-preview" />

- **P�tla**  
  Polecenie p�tli, to skrypt powtarzaj�cy w k�ko podan� cz�� kodu (st�d te� p�tla). Nale�y pami�ta�, aby zastosowa� jakie� wyj�cie z p�tli, gdy� w przeciwnym wypadku gracz utknie w danym momencie (i gra si� zawiesi). W celu zatrzymania p�tli mo�na u�y� polecenia _skrypt: zatrzymaj zdarzenie_ albo _scena: zmie� scen� (teleport)_.
  <img src="/img/events/loop.png" class="event-preview" />

- **Etykieta: okre�l / Etykieta: skocz do** <span class="new">Now�� od wer. 1.2.0</span>  
  Polecenie _Etykieta: okre�l_ definiuje pewne miejsce w kodzie skryptu, do kt�rego mo�na wr�ci� przy pomocy polecenia _Etykieta: skocz do_.
  _Uwaga:_ nazwa etykiety musi by� identyczna (przy poleceniach okre�lenia jak i skocz do) by polecenia mog�y dzia�a�. **Zalecana ostro�no��!**
  <img src="/img/events/label-goto.png" class="event-preview" />

- **Grupa polece�**  
  Owe polecenie nie jest kodem wykonywalnym, kt�ry mo�na odczu� w grze, ale pozwala na zgrupowanie sekwencji polece� w celu nadania im etykiety (strza�eczka w d� po prawej stronie i z menu _zmie� nazw� polecenia_). Pozwala to zwin�� polecenia w jeden blok.
  <img src="/img/events/event-group.png" class="event-preview" />

- **Skrypt: zatrzymaj zdarzenie (stop)**  
  Polecenie zatrzymuje wykonywanie obecnego zdarzenia.
  <img src="/img/events/script-stop.png" class="event-preview" />

- **Disable Else** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Je�li nie potrzebujesz dodatkowej opcji _w innym wypadku_ sprawdzaj�cej co si� stanie, je�eli warunek nie zostanie spe�niony to mo�na t� opcj� wy��czy�. Wystarczy z menu polecenia (po prawej stronie, strza�ka w d�) wybra� opcj� z menu _wy��cz opcj� inny wypadek_. To samo menu mo�e by� u�yte do przywr�cenia opcji _w innym wypadku_, je�li zajdzie taka potrzeba w p�niejszym czasie.
  <img src="/img/events/disable-else.png" class="event-preview" />

## Polecenia ekranu (kamery/punktu skupienia)

- **Ekran: przesu�**  
  Polecenie przesuwa punkt skupienia ekranu w inne, wyznaczone miejsce.
  <img src="/img/events/camera-move-to.png" class="event-preview" />

- **Ekran: powr�t do gracza**  
  Polecenie przywraca punkt skupienia na �rodku gracza, blokuj�c dan� pozycj�, by gracz by� zawsze w centrum.
  <img src="/img/events/camera-lock-to-player.png" class="event-preview" />

- **Ekran: wstrz�s**  
  Polecenie wywo�uje efekt wstrz�su ekranu, kt�ry mo�e trwa� 10 sekund.  
  <img src="/img/events/camera-shake.png" class="event-preview" />


## Polecenia ekranu (jako ca�o�ci)

- **Ekran: wyczyszczenie**  
  Ekran zostaje wyczyszczony do bia�ego koloru (jest to rodzaj przej�cia).
  <img src="/img/events/screen-fade-in.png" class="event-preview" />

- **Ekran: pojawienie**  
  Ekran zostaje wy�wietlony ponownie, efekt powrotu z bia�ego wyczyszczenia. 
  <img src="/img/events/screen-fade-out.png" class="event-preview" />

## Polecenia aktora

- **Actor: ustaw kierunek (obr�t)**  
  Polecenie s�u�y do ustawienia konkretnego aktora w wybranym kierunku.  
  <img src="/img/events/actor-set-direction.png" class="event-preview" />
  <img src="/img/events/actor-set-direction-preview.png" class="event-preview" />

- **Aktor: ustaw kierunek (obr�t) ze zmiennej** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie s�u�y do ustawienia konkretnego aktora w wybranym kierunku przy pomocy warto�ci zmiennej.
  <img src="/img/events/actor-direction-variables.png" class="event-preview" />

- **Aktor: ustaw po�o�enie**  
  Polecenie pozwala na zmian� po�o�enia aktora na scenie, poprzez wskazanie nowych wsp�rz�dnych.  
  <img src="/img/events/actor-position.png" class="event-preview" />

- **Aktor: ustaw po�o�enie ze zmiennej**  
  Polecenie pozwala na zmian� po�o�enia aktora na scenie przy pomocy warto�ci zmiennych.  
  <img src="/img/events/actor-position-variables.png" class="event-preview" />

- **Aktor: ustaw po�o�enie (wzgl�dnie)**  
  Polecenie s�u�y do ustawienia nowego po�o�enia dla wybranego aktora. Set the position in the scene of the specified actor relative to their current position.  
  <img src="/img/events/actor-relative-position.png" class="event-preview" />

- **Aktor: przesu�**  
  Polecenie sprawi by wybrany aktor poszed� do okre�lonej pozycji na scenie. Aktor zignoruje wszystkie kolizje na �cie�ce, zatem aby unikn�� przeszk�d na scenie, nale�y po��czy� wiele polece� (_aktor: przesu�_), w celu okre�lenia dok�adnej �cie�ki.
  <img src="/img/events/actor-move-to.png" class="event-preview" />

- **Aktor: przesu� (wzgl�dnie)**  
  Polecenie sprawy by wybrany aktor poszed� do okre�lonej pozycji na scenie (wzgl�dnie).
  <img src="/img/events/actor-relative-move.png" class="event-preview" />

- **Aktor: przesu� ze zmiennej**  
  Polecenie sprawy by wybrany aktor poszed� do okre�lonej pozycji na scenie przy pomocy warto�ci wskazanych zmiennych.  
  <img src="/img/events/actor-move-to-variables.png" class="event-preview" />

- **Aktor: zapisz po�o�enie do zmiennych**  
  Polecenie zapisuje aktualne po�o�enie wybranego aktora do dw�ch wskazanych zmiennych.  
  <img src="/img/events/actor-store-position.png" class="event-preview" />

- **Aktor: zapisz obr�t w zmiennej** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie zapisuje aktualny kierunek (obr�t) aktora do wskazanej zmiennej.  
  <img src="/img/events/actor-store-direction.png" class="event-preview" />

- **Aktor: odepchnij od gracza**  
  Polecenie odpycha aktualnego aktora od gracza o jedno pole. Istnieje mo�liwo�� wykonania odepchni�cia, a� do momentu napotkania przeszkody.
  <img src="/img/events/actor-push.png" class="event-preview" />

- **Aktor: chmurka z ikon�**  
  Polecenie wy�wietla chmurk�, kt�ra wy�wietla drobn� ikon� nad wybranym aktorem. Zazwyczaj mo�na wy�wietli� emocje jak np _Wykrzyknik(!)_, _Zapytanie(?)_, _Serduszko_, _Przerw�(...)_, _Zdenerwowanie_, _Pot_, _Muzyczn� nut�_ oraz _sen_. Istnieje mo�liwo�� zast�pienia tych grafik, jak i innych podstawowych grafik. Na ten temat mo�na poczyta� w dziale [Elementy interfejsu](/docs/ui-elements#emotes-png).  
  <img src="/img/events/actor-emote.png" class="event-preview" />
  <img src="/img/events/actor-emote-preview.png" class="event-preview" />

- **Aktor: klatka animacji**  
  Ustawienie konkretnej klatki animacji dla wybranego aktora.  
  <img src="/img/events/actor-set-frame.png" class="event-preview" />

- **Aktor: klatka animacji ze zmiennej** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Ustawienie konkretnej klatki animacji dla wybranego aktora przy pomocy warto�ci zmiennej.
  <img src="/img/events/actor-set-frame-variable.png" class="event-preview" />

- **Aktor: szybko�� animacji**  
  Ustawienie szybko�ci animacji dla wybranego aktora.  
  <img src="/img/events/actor-animation-speed.png" class="event-preview" />

- **Aktor: szybko�� ruchu**  
  Ustawienie szybko�ci ruchu dla wybranego aktora.   
  <img src="/img/events/actor-movement-speed.png" class="event-preview" />

- **Aktor: zmie� grafik� gracza**  
  Polecenie zmienia ustalon� grafik� dla gracza, kt�ra zosta�a ustalona w _edytorze projektu_. Zmiana grafik gracza jest przydzielona na sta�e i nawet b�dzie si� utrzymywa� przy zmianie scen i przej�cia. Je�eli zmiana grafiki ma by� tylko tymczasowa, to nale�y pami�ta�, aby ponownie u�y� tego polecenia w celu przywr�cenia w�a�ciwej grafiki.  
  <img src="/img/events/actor-player-spritesheet.png" class="event-preview" />

- **Aktor: wy��cz kolizj�** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie wy��cza ustawienia kolizji na wybranym aktorze. Je�eli zostanie wybrany aktor to gracz b�dzie m�g� przez niego przej��. Je�eli zostanie wybrany gracz, to gracz b�dzie w stanie przechodzi� przez wszystko (i aktor�w i kolizje na scenie).
  _Uwaga:_ Nawet je�eli kolizja zostaje wy��czona, to istnieje nadal mo�liwo�� interakcji z aktorami.
  <img src="/img/events/actor-collisions-disable.png" class="event-preview" />

- **Aktor: w��cz kolizj�** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie uruchamia (w��cza) ustawienia kolizji na wybranym aktorze.
  <img src="/img/events/actor-collisions-enable.png" class="event-preview" />

- **Aktor: wywo�aj zdarzenie**  
  Polecenie wywo�uje skrypt wskazanego aktora, tzw. na zawo�anie. Dzia�a to na zasadzie, jakby dosz�o do interakcji mi�dzy graczem, a wybranym zdarzeniem.
  <img src="/img/events/actor-invoke.png" class="event-preview" />

- **Aktor: schowaj (niewidzialny)**  
  Polecenie chowa wybranego aktora, by ten nie by� ju� widoczny na scenie. Ukryci aktorzy nie b�d� powodowali kolizji i te� nie mo�na z nimi wchodzi� w interakcje. Mo�na ukry� aktor�w (jak np. Gracza), po to by w skrypcie uruchomienia sceny mo�na by�o tworzy� ekran menu czy tytu� gry.
  <img src="/img/events/actor-hide.png" class="event-preview" />

- **Actor: poka� (widzialny)**  
  Polecenie wy�wietla wybranego aktora, powoduj�c, �e b�dzie znowu widoczny na scenie i mo�na by�o z nim wchodzi� w interakcje.  
  <img src="/img/events/actor-show.png" class="event-preview" />

## Polecenie obiekt�w

- **Obiekty: schowaj wszystkie**  
  Polecenie ukrywa wszystkie obiekty na scenie. Polecenie mo�e okaza� si� przydatne podczas tworzenia scenki przerywnikowej, gdzie gracz nie powinien by� widoczny poprzez dodanie do scenariusza pocz�tkowego sceny.
  <img src="/img/events/sprites-hide.png" class="event-preview" />

- **Obiekty: wy�wietl wszystkie**  
  Polecenie wy�wietla wszystkie obiekty na scenie, kt�re zosta�y wcze�niej schowane.  
  <img src="/img/events/sprites-show.png" class="event-preview" />

## Polecenia narzuty

- **Narzuta: poka� (widzialna)**  
  Polecenie wy�wietla czarne b�d� bia�e okno ekranu gry. Mo�na u�y� jako rodzaj zaciemnienia, a nast�pnie ods�oni�cia cz�ci t�a sceny, np. ekranu z logo dla projektu.
  <img src="/img/events/overlay-show.png" class="event-preview" />

- **Narzuta: schowaj (niewidzialna)**  
  Polecenie sprawia, �e narzuta staje si� niewidzalna.
  <img src="/img/events/overlay-hide.png" class="event-preview" />

- **Narzuta: przesu�**  
  Polecenie przenosi narzut� w nowe miejsce na ekranie.
  <img src="/img/events/overlay-move-to.png" class="event-preview" />

## Polecenia przycisku Joypada

- **Przycisk Joypad: czekaj na przycisk**  
  Wykonywalny skrypt jest wstrzymany i czeka na wci�ni�cie okre�lonego przycisku z Joypada (jak np. g�ra, d�, A/B).
  <img src="/img/events/joypad-pause.png" class="event-preview" />

- **Przycisk Joypad: przypisz zdarzenie**  
  Wykonanie okre�lonego skryptu za ka�dym razem, gdy zostanie naci�ni�ty okre�lony przycisk joypada. Je�eli skrypt zostanie przypisany do kierunku lub przycisku _A_, to ten skrypt zast�pi domy�lne dzia�anie w grze.
  <img src="/img/events/joypad-attach.png" class="event-preview" />

- **Przycisk Joypad: usu� przypisane zdarzenie**  
  Polecenie usuwa przypisany skrypt z przycisku joypada. Polecenie to przywraca domy�ln� funkcj� dla danego przycisku.
  <img src="/img/events/joypad-attach.png" class="event-preview" />

## Polecenia muzyki

- **Muzyka: odegraj utw�r**  
  Odtwarza plik muzyczny, opcjonalnie zap�tla plik po zako�czeniu.  
  <img src="/img/events/music-play.png" class="event-preview" />

- **Muzyka: stop**  
  Wstrzymuje aktualny odtwarzany plik muzyczny.  
  <img src="/img/events/music-stop.png" class="event-preview" />

## Sound Events

- **Sound: Play Effect** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Play a sound effect, choose from playing a beep with a given pitch, a tone with a given frequency or cymbal crash. Using [Custom Events](/docs/custom-events) you can combine multiple effects into a single reusable event to make jingles.  
  <img src="/img/events/sound-tone.png" class="event-preview" />
  <img src="/img/events/sound-beep.png" class="event-preview" />
  <img src="/img/events/sound-crash.png" class="event-preview" />

## Polecenia czasowe

- **Czekaj**  
  Wstrzymanie wykonywalnego skryptu, wstrzymanie mo�e trwa� do 10 sekund.  
  <img src="/img/events/wait.png" class="event-preview" />

- **Stoper: ustaw stoper** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie uruchamia niewidoczny stoper i w momencie kiedy dobiegnie koniec czasu, zostaje uruchomiony skrypt. Nale�y pami�ta�, �e stoper dzia�a we tle non stop i nawet jak dobiegnie do ko�ca, to zostanie odtworzony na nowo. W celu przerwania stopera nale�y u�y� polecenia _stoper: usu� stoper_ albo po prostu zmieni� scen� przy pomocy teleportu.
  <img src="/img/events/timer-set.png" class="event-preview" />

- **Stoper: resetuj stoper** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie zresetuje licznik z powrotem do zera. Skrypt zostanie wywo�any ponownie po pierwotnie okre�lonym czasie.
  <img src="/img/events/timer-restart.png" class="event-preview" />

- **Stoper: usu� stoper** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie wstrzyma i usunie wykonywanie stopera.
  <img src="/img/events/timer-disable.png" class="event-preview" />

## Polecenia stanu gry

- **Stan gry: zapisz**  
  Polecenie zapisuje aktualny stan gry.
  <img src="/img/events/data-save.png" class="event-preview" />

- **Stan gry: wczytaj**  
  Polecenie wczytuje poprzedni stan gry. 
  <img src="/img/events/data-load.png" class="event-preview" />

- **Stan gry: czy��**  
  Polecenie usuwa wszelakie wcze�niejsze zapisane stany gry.
  <img src="/img/events/data-clear.png" class="event-preview" />

## Polecenia inne

- **Komentarz** <span class="new">Nowo�� od wer. 1.2.0</span>  
  Polecenie nie zapewnia �adnej funkcji w grze, ale umo�liwia pozostawienie notatek w skryptach. Wpisany tekst jest automatycznie ustawiany w tytule zdarzenia, dzi�ki czemu mo�na zwin�� komentarz i nadal czyta� jego tre��.
  <img src="/img/events/comment.png" class="event-preview" />  
  Zawsze mo�na przy pomocy menu (po prawej stronie polecenia, strza�ka w d�) wybra� opcj� _wy��cz polecenie_, aby ono nie by�o brane pod uwag�. Mo�na _wy��cza�_ i _w��cza�_ dowolne polecenia. 
  Zdarzenia wy��czone zostan� pomini�te podczas uruchamiania w grze.
  <img src="/img/events/event-disable-menu.png" class="event-preview" />
  <img src="/img/events/event-disabled.png" class="event-preview" />
