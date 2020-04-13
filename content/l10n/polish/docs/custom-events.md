---
title: "W�asne zdarzenia"
draft: false
next: "/docs/assets"
nextTitle: "Zasoby"
---

<span class="new">Nowo�� od wer. 1.2.0</span>

_W�asne zdarzenia_ pozwalaj� tworzy� procedury wielokrotnego u�ytku w grze, kt�re mog� by� u�ywane w dowolnym skrypcie.

Klikni�cie w t�o mi�dzy scenami spowoduje na bocznym pasku programu uruchomienie _edytora projektu_, kt�ry wy�wietla list� _w�asnych zdarze�_ znajduj�cych si� w twoim projekcie, a tak�e przycisk _dodaj w�asne zdarzenie_.

W pierwszej kolejno�ci _w�asne zdarzenie_ musi zosta� nazwane, a nast�pnie mo�na rozpocz�� tworzenie skryptu w taki sam spos�b jak w przypadku _aktor�w_, _rozruch�w_ i _scen_.

## Parametry

Ilekro� zostanie dodane zdarzenie, kt�re odczytuje _zmienn�_, to zostanie to dodane do listy parametr�w wej�ciowych dla _w�asnego zdarzenia_, gdzie mo�na nada� temu wej�ciu konkretn� nazw�. Polecenia, kt�re wp�ywaj� na _aktor�w_, domy�lnie b�d� dotyczy� gracza, ale je�eli zostanie wybrany konkretny aktor przy pomocy selektora, to istnieje mo�liwo�� ustawienia tego zdarzenia by odczytywa�o warto�� _aktora_ z parametru wej�ciowego.

Dla przyk�adu, poni�sze w�asne zdarzenie sprawi by `Aktor A` kr�ci� si� w k�ko.

<img src="/img/screenshots/custom-event-dance.png" class="event-preview" />

To _w�asne zdarzenie_ mo�e zosta� wykorzystane na _aktorach_, _rozruchach_, _scenach_ i b�dzie to wygl�da� w nast�puj�cy spos�b.

<img src="/img/events/custom-event.png" class="event-preview" />

Je�eli kiedykolwiek zajdzie potrzeba edytowania _w�asnego zdarzenia_, to mo�na do niego powr�ci� przy pomocy u�yciu listy w�asnych zdarze�, kt�re wy�wietlaj� si� w _edytorze projektu_ lub te� przez wybranie _edytuj w�asne zdarzenie_ z menu rozwijanego zdarzenia.

<img src="/img/screenshots/custom-event-edit.png" class="event-preview" />
