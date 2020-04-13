---
title: "Gracz"
draft: false
next: "/docs/actors"
nextTitle: "Aktorzy"
---

## Pozycja startowa gracza

Pozycja startowa gracza jest widoczna w trybie _�wiat gry_ za pomoc� ikony <img src = "/ img / screenshots / player-start.png" style = "height: 12px" />. 

Klikni�cie t�a mi�dzy scenami spowoduje wy�wietlenie w _bocznym pasku_ informacji o projekcie, gdzie b�dzie mo�liwo�� ustawienia pozycji startowej gracza, obr�t jak i grafik� gracza, kt�r� mo�na wybra� z arkusza dost�pnych [obiekt�w](/docs/sprites).

Mo�na zmieni� pozycj� startow� gracza, poprzez z�apanie i przeci�gni�cie ikony <img src="/img/screenshots/player-start.png" style="height:12px"/> w odpowiednie (nowe) miejsce. Ikon� pozycji startowej gracza mo�na przeci�ga� mi�dzy scenami.


## Skryptowanie

Wi�kszo�� skrypt�w dla zdarze� Aktora mog� zosta� zastosowane do gracza. Dodatkowo mo�na u�y� polecenia _zmie� grafik� gracza_, aby zmieni� grafik� gracza podczas gry. Za pomoc� tej metody, gracz b�dzie posiada� now� grafik� nawet w czasie przechodzenia mi�dzy scenami. Je�eli zmiana grafiki jest tymczasowa, to nale�y pami�ta� o przywr�ceniu grafiki gracza do pierwotnego wizerunku.

Podczas prze��czania mi�dzy scenami gracz zawsze b�dzie widoczny w miejscu rozpocz�cia sceny, niezale�nie od jego poprzednich opcji widoczno�ci. Aby uzyska� efekt, gdzie gracz jest ukryty podczas uruchomienia sceny, np. Wy�wietlaj�c ekran tytu�owy lub przerywnik scenowy, to nale�y doda� polecenie _Schowaj (Aktor: schowaj)_ i wskaza� na gracza, przy skrypcie _uruchomienia (auto start)_. 
