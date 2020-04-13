---
title: "Aktorzy"
draft: false
next: "/docs/triggers"
nextTitle: "Rozruchy"
---

Aktorami w programie nazywa si� postacie jak i obiekty, kt�re mog� by� naniesione na scen� i z kt�rymi gracz mo�e wchodzi� w interakcje.

## Dodanie aktora

Aby doda� aktora na scen�, to nale�y nacisn�� przycisk _**+**_ na pasku _narz�dzi_, a nast�pnie wybra� pozycj� _aktor_ (lub przy pomocy skr�ty z klawiatury, nacisn�� klawisz **A**). Po tym, wystarczy wskaza� scen� i miejsce dla aktora.
<img src="/img/screenshots/add-actor.gif" style="width:300px"/>

_Boczny pasek_ programu wy�wietla ustawienia dla wybranego obiektu. Je�eli aktor zostanie zaznaczony to _boczny pasek_ programy wy�wietli ustawienia dla wybranego aktora. Przy pomocy ustawie� mo�na aktorowi nada� nazw�, zmieni� jego po�o�enie (co r�wnie� mo�na osi�gn�� przy pomocy przeci�gni�cia i upuszczenia), wybra� grafik� z arkusza [obiekt�w] (/ docs / sprites), pocz�tkowy kierunek, rodzaj ruchu oraz skrypt - odtwarzane polecenia, gdy gracz wejdzie w interakcj� z wybranym zdarzeniem.

## Rodzaj ruchu

Istnieje kilka r�nych rodzaj�w ruch�w do wyboru. Rodzaj ruchu nale�y wybra� w zale�no�ci od tego jak dane zdarzenie (aktor) ma si� zachowywa�, gdy gracz chodzi po scenie i wchodzi w interakcj� z zdarzeniem.

- **Brak** - Zdarzenie (aktor) wy�wietli pojedyncz� klatk� z arkusza graficznego.  
  Je�eli arkusz obiekt�w zawiera wi�cej ni� jedn� klatk�, to u�ytkownik b�dzie mia� mo�liwo�� wyboru, kt�r� klatk� program ma wy�wietli�. Istnieje mo�liwo�� p�niejszej modyfikacji za pomoc� polecenia _Aktor: klatka animacji_. Arkusz obiekt�w z wieloma klatkami umo�liwia tak�e animacj� aktora poprzez cykliczne odtwarzanie ka�dej klatki z okre�lon� pr�dko�ci�, kt�r� mo�na modyfikowa� za pomoc� polecenia _Aktor: szybko�� animacji_.\
  \
  Zdarzenie b�dzie zwr�cone tylko w pocz�tkowym, ustalonym kierunku (chyba, �e kierunek zostanie p�niej zmodyfikowany za pomoc� skryptu). Je�eli gracz wejdzie w interakcj� z tym zdarzeniem, to ono nie zmieni kierunku. Opcja ta jest przydatna dla np. Tabliczek albo innych nieruchomych przedmiot�w.

- **Obr�t twarz�** - Zdarzenie jest ustawione w pocz�tkowym kierunku, natomiast w momencie gdy gracz wejdzie w interakcj� z aktorem, zdarzenie obr�ci si� w stron� gracza, przed odtworzeniem skryptu. Funkcja ta sprawdza si� dla prostych postaci (np. NPC), kt�re maj� by� bardziej wra�liwe na dzia�ania gracza. 

- **Losowy obr�t** - Zdarzenie jest ustawione w pocz�tkowym kierunku, ale w ustalonych odst�pach czasu zdarzenie owy kierunek zmienia wykonuj�c obr�t (oczywi�cie w losowym kierunku). Funkcja ta sprawdza si� postaci, kt�re rozgl�daj� si� po otoczeniu.

- **Losowy krok** - Zdarzenie losowo zmienia kierunek i porusza si� po scenie w ustalonych odst�pach czasu. Funkcja ta jest przydatna dla postaci, kt�re przeszukuj� dany obszar. Uwaga: aktorzy, kt�rzy posiadaj� _losowy krok_ s� w stanie zablokowa� ruch gracza, zatem nie zaleca si� stosowania tego rodzaju ruchu w ciasnych miejscach, gdzie gracz mo�e utkn��, czekaj�c, a� aktor zejdzie z drogi.

_Uwaga_ Je�eli dla zdarzenie zastosowano brak ruchu (czyli z arkusza obiekt�w b�dzie u�ywa�o tylko jedn� klatk� animacji), w�wczas jedynym dost�pnym rodzajem ruchu b�dzie jedna statyczna klatka i nie zostan� wy�wietlone ustawienia do wyboru rodzaju ruchu i kierunku pocz�tkowego. 

## Limit klatek

Ze wzgl�du na ograniczenia sprz�towe, aktorom w ka�dej scenie mo�na przypisa� **tylko 25 unikatowych klatek** animacji. Gdzie tylko jest mo�liwe, zaleca si� stosowanie braku ruchu lub nie animowanych obiekt�w, aby zmniejszy� liczb� u�ywanych klatek. Innym sposobem na zmniejszenie liczby klatek jest ponowne u�ycie tego samego obiektu dla wielu aktor�w na scenie. Ponowne u�ycie tej samej grafiki z arkusza obiekt�w nie b�dzie wliczane do ca�kowitej liczby klatek sceny.

## Skryptowanie

Dla ka�dego aktora istnieje mo�liwo�� zdefiniowania dw�ch skrypt�w do wykonania: 
_Skrypt (naci�ni�cie przycisku)_ oraz _Skrypt (auto start)_. Program umo�liwia prze��czenie mi�dzy skryptami przy pomocy zak�adki. Kiedy aktor jest zaznaczony i na bocznym pasku zostanie wy�wietlone ustawienia aktora, to wystarczy zaznaczy� jedn� z dost�pnych zak�adek skryptu (_skrypt (naci�ni�cie przycisku)_ lub _skrypt (auto start)_).

Skrypt typu _Skrypt (naci�ni�cie przycisku)_ zostanie uruchomiony w momencie, gdy gracz b�dzie obok danego zdarzenia i zostanie naci�ni�ty przycisk _A_.

Skrypt typu _Skrypt (auto start)_ zostanie uruchomiony automatycznie jak tylko scena zostanie wczytana. Skrypty _skrypt (auto start)_ aktor�w posiadaj� pierwsze�stwo ni�eli skrypty _skrypt (auto start)_ sceny.

Kiedy zdarzenie jest zaznaczone to na _bocznym pasku_ zostaj� wy�wietlone ustawienia dla tego zdarzenia. Wystarczy wybra� przycisk _Dodaj polecenie_, aby otworzy� menu z dost�pn� list� polece�, za pomoc� kt�rych mo�na stworzy� w�asny skrypt dla zdarzenia.

Wi�cej informacji na temat skryptowania mo�na znale�� w temacie [Skryptowanie (polecenia zdarzenia)](/docs/scripting).
