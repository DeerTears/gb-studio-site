---
title: "Buduj swoj� gr�"
draft: false
next: "/docs/settings"
nextTitle: "Ustawienia"
---

## Gra

Po klikni�ciu przycisku _Uruchom_ (w prawym g�rnym rogu okna _edytora projektu_, przycisk play), program rozpocznie komplilacj� gry, a po jej zako�czeniu otworzy okno, w kt�rym mo�na gra� w aktualny projekt. Zobacz temat [Klawiatura - skr�ty klawiszy](/docs/keyboard-shortcuts), aby uzyska� szczeg�owe informacje na temat poruszania si� (patrz na dzia� _sterowanie podczas gry_).

## Terminal

W _nawigatorze projektu_ przejd� do menu _zbuduj i uruchom_, spowoduje to wy�wietlenie _terminalu_, gdzie zostanie wy�wietlony dziennik (log) kompilacji projektu. Mo�na przej�� do tego ekranu tak�e poprzez naci�ni�cie _uruchom_ podczas kompilacji. Ten ekran pokazuje, czy w kompilacji wyst�puj� b��dy, kt�re mog� pom�c w ich poprawieniu.

## Eksportuj jako ROM

Klikni�cie w przycisk _eksportuj jako ROM_ i program rozpocznie proces utworzenia pliku ROM w folderze projektu `$ PROJECT_ROOT / build / rom / game.gb`. Plik ROM jest to plik gry, kt�r� mo�na otworzy� na dowolnym emulatorze obs�uguj�cym konsol� Nintendo Gam Boy, takim jak [OpenEMU] (https://openemu.org/) lub [KiGB] (http://kigb.emuunlim.com/downloads.htm). 

## Eksportuj jako wersja Web

Mo�esz przes�a� ten folder na dowolny serwer sieciowy i przej�� do pliku `index.html`, aby zagra� w gr� w przegl�darce internetowej. Je�li korzystasz z przegl�darki internetowej na telefonie kom�rkowym lub tablecie, gra b�dzie r�wnie� zawiera� dotykowe elementy steruj�ce.

Je�li spakujesz folder `build / web`, mo�esz przes�a� go do [Itch.io] (https://itch.io) jako gra HTML. W takim przypadku zalecany rozmiar okienka ekranu to `480px` x `432px`.

## Rozwi�zywanie problem�w

W systemie macOS, je�li masz problemy z budowaniem lub uruchomieniem gry, mo�e by� r�wnie� konieczne zainstalowanie narz�dzi wiersza polecenia Apple, otwieraj�c `Applications / Terminal.app` i wprowadzaj�c nast�puj�ce polecenie.

```
xcode-select --install
```

W systemie Windows konieczne mo�e by� dodanie aplikacji do bia�ej listy/listy zaufanych program�w w oprogramowaniu antywirusowym, aby wykona� kompilacj�.
