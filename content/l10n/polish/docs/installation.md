---
title: "Instalacja"
date: 2018-01-28T14:14:44Z
draft: false
next: "/docs/getting-started"
nextTitle: "Rozpocz�cie pracy"
---

Najnowsz� wersj� programu mo�na znale�� na [na stronie Itch.io w sekcji Download](https://chrismaltby.itch.io/gb-studio) lub mo�esz pobra� [starsze wersje programu z tej strony](/downloads/older-versions).
## Windows

Dost�pne s� dwa pakiety instalacyjne programu GB Studio dla systemu Windows.

(1) Wersja _Squirrel Installer_ zawiera prosty instalator. Wystarczy plik rozpakowa�, uruchomi� aplikacj� i poczeka� chwilk� a� instalator zainstaluje aplikacje na tw�j komputer (na dysk C:\ ). Kiedy instalacja dobiegnie ko�ca, instalator automatycznie utworzy do programu skr�t na pulpicie i program GB Studio zostanie uruchomiony.
Program zostanie zainstalowany do `%LocalAppData%\gb_studio`, je�eli potrzebujesz zainstalowa� program w innym miejscu, to zaleca si� u�y� wersji manualnej. 

(2) Wersja _Manual_ to jest skompresowany plik zip, kt�ry posiada wszystkie pliki potrzebne dla programu. Plik zip nale�y rozpakowa� w dowolnym miejscu, a nast�pnie wystarczy uruchomi� plik `gb-studio.exe`, aby rozpocz�� prac� w programie.

## macOS

Dla systemy macOS nale�y rozpakowa� pobrany plik, a nast�pnie przenie�� `GB Studio.app` do folderu aplikacji (_Applications_). 

Je�eli wyst�pi� problemy podczas kompilacji lub uruchomienia twojej gry, by� mo�e zajdzie potrzeba zainstalowania Narz�dzia wiersza polece� Apple (_Apple's Command Line Tools_). W tym celu nale�y otworzy� `Aplikacje / Terminal.app`  (_`Applications/Terminal.app`_) i wprowadzaj�c nast�puj�ce polecenie.
```
xcode-select --install
```

## Ubuntu / Linuksy oparte na Debianie

W przypadku dystrybucji Linuksa opartych na Debianie, pobierz wersj� .deb i uruchom nast�puj�ce polecenia (Testowane na Ubuntu 18.10).

```
> sudo apt-get update
> sudo apt-get install build-essential
> sudo dpkg -i gb-studio_1.0.0_amd64.deb
> gb-studio
```

## Fedora / Linuksy oparte na RPM

W przypadku dystrybucji Linuksa opartych na RPM, pobierz wersj� .rpm i uruchom nast�puj�ce polecenia (Testowane na Fedorze 29).

```
> sudo yum install libXScrnSaver make lsb
> sudo rpm --ignoreos -i gb-studio-1.0.0.x86_64.rpm
> gb-studio
```
