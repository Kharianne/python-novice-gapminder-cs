# Notebooky pro lektory

V téhle složce je celá lekce jako Jupyter notebooky. Hodí se, pokud chcete učit přímo
z JupyterLabu a web lekce k tomu nepotřebujete. Každý notebook funguje sám o sobě,
obrázky jsou vložené přímo v něm a internet nepotřebuje.

| Soubor                          | Obsah                         |
| ------------------------------- | ----------------------------- |
| `01-spusteni-a-ukonceni.ipynb`  | 1. Spuštění a ukončení        |
| `02-promenne-a-prirazeni.ipynb` | 2. Proměnné a přiřazení       |
| `03-datove-typy.ipynb`          | 3. Datové typy a převody typů |
| `slovnik.ipynb`                 | Přehled a slovník pojmů       |

## Jak notebooky použít

1. Nainstalujte Python 3 a JupyterLab. Nejjednodušší je distribuce
   [Anaconda](https://www.anaconda.com/download), nebo stačí `python -m pip install jupyterlab`.
2. Zkopírujte si tuhle složku (nebo ji rozdejte studujícím) a spusťte v ní `jupyter lab`.
3. Otevřete notebook a buňky spouštějte postupně odshora klávesami <kbd>Shift</kbd>+<kbd>Enter</kbd>.

Co se hodí vědět:

- Buňky s kódem nemají uložené výstupy. Každý je uvidí až ve chvíli, kdy buňku spustí.
- Některé buňky schválně skončí chybou, protože ukazují chybové hlášky. _Run All_ se proto
  zastaví na první z nich, buňky je lepší spouštět jednu po druhé.
- Pod cvičeními je prázdná buňka, do které můžou studující psát vlastní kód
  (u cvičení s Markdownem buňka na text).
- Řešení cvičení jsou schovaná pod odkazem **Řešení**. Pokud je studujícím nechcete ukazovat,
  smažte buňky s řešením, než notebooky rozdáte.
- Poznámky k výuce (terminologie, na co si dát pozor) jsou v souboru
  [`../instructors/instructor-notes.md`](../instructors/instructor-notes.md).

## Úpravy

Notebooky se vytvářejí z epizod lekce (`episodes/*.md`) skriptem
[`../scripts/vytvor_notebooky.py`](../scripts/vytvor_notebooky.py). Když epizody upravíte,
spusťte v kořenové složce lekce:

```bash
python3 scripts/vytvor_notebooky.py
```

Skript notebooky vytvoří znovu, takže změny udělané přímo v notebookách by se ztratily.
Upravujte proto epizody, ne notebooky.

## Licence

Notebooky vycházejí z lekce
[Plotting and Programming in Python](https://swcarpentry.github.io/python-novice-gapminder/)
ze Software Carpentry, Copyright (c) [The Carpentries](https://carpentries.org/). Výukový
materiál je pod licencí [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.cs),
ukázky kódu pod licencí MIT. Českou verzi připravila Kateřina Volfová. Podrobnosti jsou
v souboru [`../LICENSE.md`](../LICENSE.md).

Když notebooky rozdáváte nebo upravujete, nechte v nich údaje o původu a licenci.
