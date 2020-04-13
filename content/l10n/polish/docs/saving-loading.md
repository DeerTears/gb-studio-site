---
title: "Zapisywanie i wczytanie"
draft: false
next: "/docs/project-editor"
nextTitle: "Edytor projektu"
---

## Zapisywanie

Aby zapisa� projekt, wybierz z menu opcj� `Plik> Zapisz` lub przy pomocy skr�tu z klawiatury Ctrl / Cmd + S. Je�li spr�bujesz zamkn�� projekt z niezapisanymi zmianami, to program powiadomi Ci� o tym. GB Studio wy�wietli odpowiedni komunikat, dzi�ki kt�remu b�dzie mo�na najpierw zapisa� projekt, a dopiero p�niej b�dzie mo�na wyj�� z programu. W systemie macOS wszelkie niezapisane zmiany w projekcie b�d� reprezentowane przez kropk� na przycisku zamykania okna.

## Wczytanie (ponowne otwarcie projektu)

Aby wczyta� projekt nad kt�rym si� ju� pracowa�o to nale�y u�y� przycisku _Otw�rz_ w pocz�tkowym oknie _Nowy projekt_, lub mo�na te� otworzy� projekt z menu g��wnego programu `Plik> Otw�rz`, a nast�pnie nale�y przej�� do folderu projektu i wybra� plik `.gbsproj`. 

## Kontrola wersji

Uk�ad folderu projektu jak i plik `.gbsproj` zosta�y zaprojektowane w taki spos�b aby wsp�pracowa�y z systemami kontrolnymi wersji, takimi jak [Git](https://git-scm.com/). Systemu kontrolne wersji umo�liwiaj� �atwe �ledzenie historii przy ka�dej zmianie wprowadzanej przez aplikacj� w nowej linii w pliku danych. Je�li chcesz u�y� kontroli wersji w swoim projekcie, mo�esz po prostu utworzy� repozytorium w folderze g��wnym projektu. 

Zaleca si� zignorowanie folderu kompilacji (folderu `build`) z repozytorium za pomoc� pliku `.gitignore` lub podobnego.

## Kopia zapasowa

Za ka�dym razem, gdy zapisujesz projekt, poprzednia wersja jest zapisywana w folderze projektu z rozszerzeniem `.gbsproj.bak`. Je�li kiedykolwiek zajdzie potrzeba przywr�cenia poprzedniej wersji projektu, to wystarczy zmieni� nazw� tego pliku, aby mie� rozszerzenie `.gbsproj`, a nast�pnie otworzy� ten plik.
