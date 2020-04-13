---
title: "T�a"
draft: false
next: "/docs/ui-elements"
nextTitle: "Elementy interfejsu"
---

Ka�da scena wymaga obrazu t�a, kt�ry okre�la jej wygl�d. Mo�na doda� t�o do gry, poprzez umieszczenie pliku t�a (PNG) do folderu projektu `assets/backgrounds`.

## Wymagania

Pliki t�a, musz� by� w formacie PNG oraz musz� zawiera� nast�puj�ce cztery kolory:

<div><div class="Swatch" style="background:#071821;"></div><div class="SwatchLabel">#071821</div></div>
<div><div class="Swatch" style="background:#306850;"></div><div class="SwatchLabel">#306850</div></div>
<div><div class="Swatch" style="background:#86c06c;"></div><div class="SwatchLabel">#86c06c</div></div>
<div><div class="Swatch" style="background:#e0f8cf;"></div><div class="SwatchLabel">#e0f8cf</div></div>

<div class="InfoBox">
Pobierz palet� kolor�w GB Studio dla:<br />
<a href="/assets/swatches/gb-studio-photoshop.aco">Adobe Photoshop</a><br />
<a href="/assets/swatches/gb-studio-aseprite.aseprite">Aseprite</a>
</div>

Kolory, kt�re nie s� jednym z powy�szych kod�w szesnastkowych, zostan� dopasowane do najbli�szego koloru. W przeciwie�stwie do obiekt�w, koloru `# 65ff00` nie mo�na u�ywa� na tle.

T�a s� podzielone na zestawy kafelk�w `8px` x `8px`, wi�c ca�kowity rozmiar obrazu musi by� wielokrotno�ci� `8px` zar�wno pod wzgl�dem szeroko�ci, jak i wysoko�ci. T�o ma minimalny rozmiar `160px` x `144px` (rozmiar ekranu), a obecnie t�o nie mo�e by� wi�ksze ni� `256px` x `256px`.

Obraz mo�e zawiera� jednocze�nie nie wi�cej ni� ** 192 ** unikalnych kafelk�w `8px` x `8px` ze wzgl�du na ograniczenia pami�ci. Oznacza to, �e nawet przy u�yciu najmniejszego mo�liwego rozmiaru t�a musisz powt�rzy� oko�o po�owy swoich p�ytek. Tam, gdzie to mo�liwe, powtarzaj kafelki mi�dzy obrazami, poniewa� zostan� one zgrupowane, oszcz�dzaj�c ca�kowity rozmiar gry. Zaleca si� u�ycie edytora map kafelk�w, takiego jak [Tiled](https://www.mapeditor.org/), aby zapewni� zgodno�� t�a z siatk� pikseli.
