---
title: "Elementy interfejsu"
draft: false
next: "/docs/music"
nextTitle: "Muzyka"
---

Projekt zawiera wiele plik�w w folderze `assets/ui` ze sta�ymi nazwami plik�w, kt�re definiuj� cz�ci interfejsu u�ytkownika twojej gry. Edycja tych plik�w pozwala zmieni� domy�ln� czcionk�, ustawi� ramk� okna i zmodyfikowa� kursor wyboru.

Je�li usuniesz kt�rykolwiek z plik�w w folderze interfejsu u�ytkownika, zostan� one zast�pione domy�lnymi zasobami przy nast�pnym tworzeniu gry, umo�liwiaj�c cofni�cie niepo��danych zmian.

## ascii.png

Edytuj ten plik, aby zmieni� czcionk� gry podczas rozmowy z aktorami w grze.

<img src="/img/ui/ascii.png" class="HelpSprite" style="width:384px; height:auto;"/>

## frame.png

Silnik gry u�ywa [9-plasterkowego skalowania / 9-slice scaling] (https://en.wikipedia.org/wiki/9-slice_scaling) poni�szego obrazu, aby utworzy� ramk� dla pola tekstowego. Edycja tego obrazu pozwoli na zmian� ramki tekstu lub ustawi� jednolity kolor dla tekstu.

<img src="/img/ui/frame.png" class="HelpSprite" style="width:72px; height:auto;"/>

## cursor.png

Ten obraz jest u�ywany jako kursor wyboru podczas pokazywania opcji wielokrotnego wyboru w grze.

<img src="/img/ui/cursor.png" class="HelpSprite" style="width:24px; height:auto;"/>

## emotes.png

Obraz ten odpowiada za wy�wietlanie emotikonek w chmurce, kt�re zostaj� wy�wietlane nad aktorami przy pomocy skrypt�w. Ka�da chmurka posiada rozmiar `16px` x `16px` i ka�da z chmurek reprezentuje nast�puj�ce emocje w kolejno�ci od lewej do prawej: _wykrzyknik(!)_, _pytanie(?)_, _serce_, _cisze_, _zdenerwowanie_, _pot_, _nutk� muzyczn�_, _sen_.

<img src="/img/ui/emotes.png" class="HelpSprite" style="width:384px; height:auto;"/>

## Wymagania

Z wyj�tkiem pliku `emotes.png`, kt�ry spe�nia standardowe wymagania sprite, plik PNG dla interfejsu u�ytkownika musi zawiera� tylko nast�puj�ce cztery kolory:

<div><div class="Swatch" style="background:#071821;"></div><div class="SwatchLabel">#071821</div></div>
<div><div class="Swatch" style="background:#306850;"></div><div class="SwatchLabel">#306850</div></div>
<div><div class="Swatch" style="background:#86c06c;"></div><div class="SwatchLabel">#86c06c</div></div>
<div><div class="Swatch" style="background:#e0f8cf;"></div><div class="SwatchLabel">#e0f8cf</div></div>

<div class="InfoBox">
Pobierz palet� kolor�w GB Studio dla:<br />
<a href="/assets/swatches/gb-studio-photoshop.aco">Adobe Photoshop</a><br />
<a href="/assets/swatches/gb-studio-aseprite.aseprite">Aseprite</a>
</div>
