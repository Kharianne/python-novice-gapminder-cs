---
title: Poznámky pro lektory
---

## O lekci

Lekce pokrývá první tři epizody původní lekce
[Plotting and Programming in Python](https://swcarpentry.github.io/python-novice-gapminder/)
ze Software Carpentry: spuštění JupyterLabu, proměnné a datové typy. Je psaná pro dospělé
začátečníky a vejde se do jednoho večera (zhruba 1,5–2 hodiny i se cvičeními).

Pokud chcete pokračovat, v původní lekci navazují epizody _Built-in Functions and Help_
a _Libraries_ (zatím jen anglicky).

## Terminologie

Python je plný anglických pojmů. Studující na ně narazí v chybových hláškách, v dokumentaci
i při hledání na internetu. Proto je v lekci necháváme anglicky a český význam dáváme
do závorky, když se pojem objeví poprvé:

| V lekci                      | Česky              | V kódu                 |
| ---------------------------- | ------------------ | ---------------------- |
| integer                      | celé číslo         | `int`                  |
| floating point number, float | desetinné číslo    | `float`                |
| string, character string     | textový řetězec    | `str`                  |
| tuple                        | n-tice             | `tuple`                |
| list                         | seznam             | `list`                 |
| index                        | index              | `[0]`                  |
| slice                        | výřez              | `[start:stop]`         |
| substring                    | podřetězec         |                        |
| built-in function            | vestavěná funkce   | `print`, `len`, `type` |
| floor division               | celočíselné dělení | `//`                   |
| modulo                       | zbytek po dělení   | `%`                    |
| dot notation                 | tečková notace     | `hodnota.real`         |

Obecné pojmy (proměnná, hodnota, funkce, argument, buňka) jsou česky. Názvy nabídek
a tlačítek v JupyterLabu (_File_, _Kernel_, _Command mode_…) zůstávají anglicky, protože
přesně tak je studující uvidí na obrazovce.

## Na co si dát pozor

- **Desetinná čárka.** Studující budou psát `3,14`. Python z toho neudělá chybu, ale tuple
  `(3, 14)`, a výsledky pak nedávají smysl. V epizodě o datových typech je na to samostatný box.
- **Diakritika v názvech proměnných.** `věk = 42` v Pythonu 3 projde, ale je lepší zvyknout si
  na názvy bez diakritiky (`vek`). V textech (stringech) diakritika nevadí.
- **Pořadí spouštění buněk.** V noteboocích je to nejčastější zdroj zmatků. Ukažte
  `Kernel -> Restart Kernel and Run All Cells...`.
- **Chybové hlášky jsou anglicky.** Ukažte, že nejdůležitější je poslední řádek, a přečtěte
  ho společně nahlas.
