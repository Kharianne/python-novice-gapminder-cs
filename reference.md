---
title: "Přehled a slovník"
---

## Přehled

## [Spuštění a ukončení](episodes/01-run-quit.md)

- Programy v Pythonu se ukládají do souborů s příponou `.py`.
- Kód můžete psát do textového souboru nebo do [Jupyter notebooku](https://jupyter.org/).
  - Jupyter notebooky mají příponu `.ipynb`.
  - JupyterLab spustíte z příkazové řádky příkazem `jupyter lab`.
    - V buňkách s Markdownem můžete kód popsat Markdownem nebo HTML.

## [Proměnné a přiřazení](episodes/02-variables.md)

- Hodnotu do proměnné uložíte pomocí `=`.
  - Stringy (textové řetězce) se píšou do uvozovek `'...'`.
  - Hodnoty typu integer (celá čísla) a float (desetinná čísla) se píšou bez uvozovek.
- Názvy proměnných mohou obsahovat písmena, číslice a podtržítka `_`.
  - Nesmí začínat číslicí.
  - Názvům, které začínají podtržítkem, se zatím vyhněte.
- Hodnoty vypíšete pomocí `print(...)`.
- Stringy jde indexovat.
  - Indexy se počítají od 0.
  - Pozici napíšete do hranatých závorek `[pozice]` za název proměnné.
  - Slice (výřez) vytvoříte zápisem `[start:stop]`. Dostanete kopii části původního stringu.
    - `start` je index prvního prvku.
    - `stop` je index prvku hned za posledním prvkem, který chcete.
- Délku stringu zjistíte pomocí `len(...)`.

## [Datové typy a převody typů](episodes/03-types-conversion.md)

- Každá hodnota má svůj typ a ten určuje, co s ní můžete dělat.
  - `int` je integer (celé číslo).
  - `float` je floating point number (desetinné číslo).
  - `str` je string (textový řetězec).
- Typ hodnoty nebo proměnné zjistíte built-in funkcí `type(...)`.
- Práce se stringy:
  - `+` stringy spojí.
  - `*` string zopakuje.
  - Číslo a string sečíst nejde.
    - String na integer převedete pomocí `int(...)`.
    - Číslo na string převedete pomocí `str(...)`.
- Desetinná místa se v Pythonu oddělují tečkou (`3.14`), ne čárkou.

## Slovník pojmů {#glossary}

Anglické pojmy z Pythonu tu najdete tak, jak je uvidíte v kódu, v chybových hláškách
a v dokumentaci. Český význam je v závorce.

Argument (_argument_)
: Hodnota, kterou předáváte funkci.

Built-in function (vestavěná funkce)
: Funkce, kterou má Python k dispozici vždycky, bez importu. Třeba `print`, `len` nebo `type`.

Element (prvek)
: Položka v listu (seznamu). U stringu jsou prvky jednotlivé znaky.

Float, floating point number (desetinné číslo)
: Typ pro čísla s desetinnou částí, třeba `3.14` nebo `-2.5`.

Floor division (celočíselné dělení)
: Dělení operátorem `//`, jehož výsledek se zaokrouhlí dolů.

Funkce (_function_)
: Kus kódu, který můžete zavolat a použít znovu.

Index (index)
: Pozice prvku. V Pythonu se počítá od 0.

Integer (celé číslo)
: Typ pro kladná i záporná celá čísla, třeba `3` nebo `-512`.

Jupyter notebook
: Interaktivní prostředí, ve kterém je pohromadě kód, text v Markdownu a výsledky.

Modulo (zbytek po dělení)
: Operátor `%`, který vrátí zbytek po celočíselném dělení.

Proměnná (_variable_)
: Název pro hodnotu.

Slice (výřez)
: Část stringu nebo listu, kterou získáte zápisem `[start:stop]`.

String (textový řetězec)
: Typ pro text. Píše se do jednoduchých nebo dvojitých uvozovek.

Substring (podřetězec)
: Část stringu.

Tuple (n-tice)
: Skupina hodnot oddělených čárkou, třeba `(3, 14)`.
