---
title: "Sceny"
draft: false
next: "/docs/player"
nextTitle: "Gracz"
---

Scena to pojedynczy ekran twojej gry (mo�na powiedzie� plansza, albo mapa wy�wietlana na ekranie), kt�ra mo�e sk�ada� si� z wielu [aktor�w](/docs/actors) jak i [rozruch�w](/docs/triggers). W zasadzie, gra sk�ada si� z uk�adu wielu scen, kt�re s� ze sob� po��czone przy pomocy _rozruch�w_ zawieraj�cymi polecenia zdarzenia _zmie� scen� (teleport)_.

## Dodanie nowej sceny

Aby doda� now� scen� do uk�adu scen, to nale�y nacisn�� przycisk _ ** + **_ w _narz�dziach_ a nast�pnie wybranie opcji _Scena_ z menu (mo�na pos�u�y� si� skr�tem z klawiatury, przycisk ** S **). W dowolne puste miejsce na _obszarze roboczym projektu_ (_Project Viewport_), nale�y klikn�� aby nowa scena zosta�a wy�wietlona.

<img src="/img/screenshots/add-scene.gif" style="width:300px"/>

W momencie kiedy nowa scena zosta�a dodana, na _bocznym pasku_ (_Editor Sidebar_) mo�na zmodyfikowa� informacje, takie jak nazwa, albo jakie t�o z projektu ma zosta� zastosowane dla wybranej sceny. Wi�cej informacji na temat dodawania obraz�w t�a mo�na znale�� w dokumentacji w temacie [t�a](/docs/backgrounds).

## Skryptowanie

Sceny posiadaj� zdarzenia _skrypt (auto start)_, kt�re mog� zosta� u�yte do uruchamiania zdarze�, gdy tylko scena zostanie wy�wietlona na ekranie. Po wybraniu sceny, na _bocznym pasku_ wystarczy zaznaczy� zak�adk� _skrypt (auto start)_, a nast�pnie wybra� przycisk _Dodaj polecenie_, aby otworzy� menu zdarze� i rozpocz�� tworzenie skryptu.  

Je�eli jakiekolwiek zdarzenie (Aktor) posiada wprowadzony skrypt _skrypt (auto start)_, to program sugeruje si� zasad�: Aktorzy posiadaj� pierwsze�stwo uruchomienia auto start. Gdy skrypt Aktor�w dobiegnie ko�ca, wtenczas program uruchomi skrypt auto start od sceny. 

Po wi�cej informacji zajrzyj do dokumentacji, dzia�u [Skryptowanie (polecenia zdarzenia)](/docs/scripting).
