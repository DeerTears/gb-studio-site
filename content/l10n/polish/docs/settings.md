---
title: "Ustawienia"
draft: false
---

<span class="new">Nowo�� od wer. 1.2.0</span>

W pasku _nawigacyjnym projektu_ w momencie wybrania menu _ustawienia_ spowoduje przej�cie do listy ustawie� projektu.

## Opcje dla GB Color

GB Studio ma ograniczon� obs�ug� GB Color, gdy gra dzia�a na kompatybilnym sprz�cie lub emulatorach. Obecnie dost�pne s� dwie opcje:

- **Tryb podw�jnej pr�dko�ci** - Gdy ta opcja jest w��czona, silnik gry mo�e w pe�ni wykorzysta� zwi�kszon� szybko�� procesora GB Color. W��czenie tej opcji zapobiega przeskakiwaniu muzyki podczas przechodzenia mi�dzy scenami.

- **W�asna paleta kolor�w** - Po w��czeniu tej opcji, mo�liwe b�dzie zast�pienie czterech kolor�w z palety kolor�w gry. Nale�y wybra� kolor, kt�ry ma zosta� zast�piony, a nast�pnie nale�y wprowadzi� warto�ci dla koloru czerwony, zielony i niebieski lub wprowad� warto�� koloru heksadecymalnego. Przycisk _zamie� na heks_ dopasowuje najbli�szy dost�pny kolor.

<img title="Color Palette" src="/img/screenshots/color-palette.png" width="513">

<img title="Color Palette Edit" src="/img/screenshots/color-palette-edit.png" width="513">

Korzystaj�c z w�asnej palety kolor�w, mo�na stworzy� drastycznie inny odcie� swojej gry! Spr�buj eksperymentowa�, aby zobaczy�, jakie ciekawe efekty mo�esz wykona�. Je�li nie podoba Ci si� ustawiona paleta kolor�w, zawsze mo�esz klikn�� przycisk _przywr�� domy�lne_, aby ponownie przywr�ci� oryginaln� palet� kolor�w.

<img title="Color Game" src="/img/screenshots/color-game.png" width="592">

## Sterowanie

Sekcja _sterowanie_ pozwala na nadpisanie domy�lnych ustawie� dotycz�cych element�w steruj�cych u�ywanych podczas gry z kompilacji internetowej i okna _uruchom_.

Aby edytowa� elementy steruj�ce przycisku, nale�y zaznaczy� pole wprowadzania. W momencie gdy pole jest pod�wietlone, nale�y nacisn�� przycisk, kt�ry chcesz przypisa�. Aby usun�� wszystkie przypisane klawisze, nale�y zaznaczy� pole, a nast�pnie nacisn�� klawisz _backspace_ na klawiaturze.

W celu przywr�cenia domy�lnych ustawie� dla sterowania, nale�y nacisn�� przycisk _przywr�� domy�lne_.

<img title="Controls" src="/img/screenshots/controls.png" width="507">

## Rodzaj kardrid�u

Sekcja _rodzaj kartrid�u_ pozwala na okre�lenie kontrolera banku pami�ci, kt�rego chcesz u�y� i czy bateria zostanie do��czona podczas eksportowania gry do fizycznego kardrid�u (wymaga dodatkowego sprz�tu i oprogramowania).

Je�li nie wiesz, co oznaczaj� te ustawienia, to najlepiej pozostaw je jako domy�lne (MBC5 + RAM + BATERIA). Ustawienia domy�lne mo�na przywr�ci� za pomoc� przycisku _przywr�� domy�lne_.

## W�asny nag��wek (Header dla wersji Web)

Istnieje mo�liwo�� u�ycia sekcji _w�asny nag��wek_, aby doda� zawarto�� do HTML `<head>` podczas generowania kompilacji dla wersji Web. Mo�esz u�y� tego, aby doda� dowolny niestandardowy CSS lub JavaScript do strony HTML wersji Web twojej gry.
