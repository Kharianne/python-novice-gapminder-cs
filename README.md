# Python pro začátečníky: první kroky

> [!IMPORTANT]
> Tento repozitář vznikl v rámci studia předmětu [DigiCompEdu](https://kisk.phil.muni.cz/edutech)
> vyučovaném na katedře KISK Filozofické fakulty MUNI.

Česká verze prvních tří epizod lekce
[Plotting and Programming in Python](https://swcarpentry.github.io/python-novice-gapminder/)
ze Software Carpentry. Je pro dospělé, kteří s programováním začínají, a probírá spuštění
JupyterLabu, proměnné a základní datové typy.

- **Původní zdroj:** <https://swcarpentry.github.io/python-novice-gapminder/>
  (repozitář <https://github.com/swcarpentry/python-novice-gapminder>, stav ze 7. 10. 2026, commit `03c3931`)
- **Nový zdroj:** `https://FIXME.github.io/python-novice-gapminder-cs/` (doplním po zveřejnění)

## Původ a licence

Lekce vychází z díla, které je Copyright (c) [The Carpentries](https://carpentries.org/).
Původní lekci připravili Allen Lee, Nathan Moore, Sourav Singh, Olav Vahtras (eds.) a další
autoři (viz soubor `AUTHORS`). Výukový materiál je pod licencí
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.cs), ukázky kódu pod licencí MIT.

## Co jsem oproti původní lekci změnila

1. **Překlad:** do češtiny jsem přeložila úvodní stránku (Summary), pokyny k instalaci (Setup)
   a epizody _Running and Quitting_, _Variables and Assignment_ a _Data Types and Type Conversion_.
2. **Zkrácení:** nechala jsem jen první tři epizody. Epizody 4–20, data Gapminder (ZIP i CSV),
   obrázky k vynechaným epizodám a původní pomocné stránky jsem odstranila.
3. **Terminologie:** pojmy z Pythonu (integer, float, string, slice, built-in function…) zůstávají
   anglicky a český význam je v závorce. Studující se pak lépe vyznají v chybových hláškách
   a v dokumentaci. Názvy nabídek a tlačítek JupyterLabu jsou anglicky, tak jak je uvidí
   na obrazovce. Přehled je v poznámkách pro lektory a ve slovníku.
4. **Ukázky kódu:** proměnné mají české názvy bez diakritiky (`vek`, `jmeno`, `nazev_atomu`…)
   a texty ve stringech i ve výstupech jsou česky. Obrázek `2_indexing.svg` jsem upravila podle
   nového názvu proměnné. Všechny ukázky jsou ověřené spuštěním v Pythonu 3.13 a výstupy sedí.
5. **Nový obsah pro české studující:** box „Desetinná tečka, ne čárka“ (zápis `3,14` vytvoří tuple),
   poznámka o diakritice v názvech proměnných a vysvětlení posledního řádku chybové hlášky.
6. **Aktualizace a opravy:**
   - vypustila jsem zastaralou zmínku o Internet Exploreru,
   - vypustila jsem Anaconda Navigator, JupyterLab se v lekci spouští jen z příkazové řádky,
   - volbu `Restart & Run All` jsem přejmenovala na aktuální `Restart Kernel and Run All Cells...`,
   - odkaz do vynechané epizody o chybových hláškách teď vede do původní lekce,
   - opravila jsem řešení cvičení s vnořeným seznamem v Markdownu (odsazení o 4 mezery, ne o 2),
   - přesněji vysvětluju písmeno `j` u komplexních čísel a zápisy `4 j` a `4 + j`,
   - ve cvičení s dny v roce je rozsah 1–366 místo 1–365,
   - obrázek s indexováním má alternativní text a tabulka s Markdownem záhlaví sloupců.
7. **Pokyny k instalaci:** napsala jsem nový český postup (Anaconda, nebo `pip`). Stahování
   dat jsem vypustila, první tři epizody žádná nepotřebují.
8. **Odkazy:** odkazy na anglické zdroje jsou označené „(anglicky)“, odkaz na Markdown vede
   na českou Wikipedii a ukázkové odkazy v tabulce na python.org a jupyter.org.
9. **Značka:** odstranila jsem logo a značku Software Carpentry (jsou to registrované ochranné
   známky) a nahradila je vlastním neutrálním logem. Vypnula jsem měření návštěvnosti
   The Carpentries (`analytics`). V `config.yaml` jsem upravila název, jazyk, kontakt, zdroj
   a fázi vývoje (_beta_).
10. **Nové stránky:** Poznámky pro lektory (terminologie, časování, na co si dát pozor),
    smyšlené Profily studujících (dospělí začátečníci) a Přehled a slovník (překlad části
    původní stránky Reference a slovník pojmů). Workbench tyhle složky vyžaduje.
11. **Notebooky pro lektory:** z epizod jsem vytvořila Jupyter notebooky (složka `notebooks/`)
    pro lektory, kteří chtějí učit přímo z JupyterLabu. Obrázky jsou v nich vložené, takže
    fungují bez internetu i bez webu lekce.
12. **České rozhraní webu:** Workbench český překlad nemá, tak jsem ho napsala a přidala
    do svého forku balíčku `sandpaper` (<https://github.com/Kharianne/sandpaper>).
    Česky je tak i navigace, popisky boxů (_Cvičení_, _Poznámka_, _Ukázat řešení_…)
    a patička.

## Struktura

```text
config.yaml                      nastavení lekce (název, jazyk, pořadí epizod)
index.md                         úvodní stránka (Summary)
learners/setup.md                pokyny k instalaci (Setup)
learners/reference.md            přehled a slovník pojmů
episodes/01-run-quit.md          1. Spuštění a ukončení
episodes/02-variables.md         2. Proměnné a přiřazení
episodes/03-types-conversion.md  3. Datové typy a převody typů
episodes/fig/                    obrázky a logo lekce
instructors/instructor-notes.md  poznámky pro lektory
profiles/learner-profiles.md     profily studujících
LICENSE.md, CITATION, AUTHORS    licence, citace, autoři původní lekce
.github/workflows/               sestavení a zveřejnění na GitHub Pages
notebooks/                       lekce jako Jupyter notebooky pro lektory
scripts/vytvor_notebooky.py      vytvoří notebooky z epizod
```

## Notebooky pro lektory

Ve složce `notebooks/` je celá lekce jako Jupyter notebooky, které fungují i bez webu
a bez internetu. Jak je použít, popisuje [`notebooks/README.md`](notebooks/README.md).
Po úpravě epizod notebooky vytvoříte znovu příkazem:

```bash
python3 scripts/vytvor_notebooky.py
```

## Rozběhání na vlastním počítači

Lekce je psaná pro [Carpentries Workbench](https://carpentries.github.io/sandpaper-docs/)
(R balíčky `sandpaper`, `varnish` a `pegboard`). Postup níž je pro macOS. Na jiných
systémech je stejný, jen R a pandoc se instalují jinak.

1. Nainstalujte R a pandoc:

   ```bash
   brew install r pandoc
   ```

   (Nebo R z <https://cloud.r-project.org/> a pandoc z <https://pandoc.org/installing.html>.)

2. Nainstalujte balíčky Workbench (stačí jednou):

   ```bash
   Rscript -e 'install.packages(c("sandpaper", "varnish", "pegboard", "tinkr"), repos = c(carpentries = "https://carpentries.r-universe.dev/", CRAN = "https://cloud.r-project.org"))'
   ```

   Aby bylo rozhraní webu česky, nainstalujte pak `sandpaper` z forku s překladem:

   ```bash
   Rscript -e 'install.packages("remotes", repos = "https://cloud.r-project.org"); remotes::install_github("Kharianne/sandpaper")'
   ```

3. Složka s lekcí musí být git repozitář, jinak sestavení spadne s chybou
   `could not find repository`. Pokud repozitář ještě nemáte (viz další kapitola):

   ```bash
   cd ~/personal/python-novice-gapminder-cs
   git init -b main
   ```

4. Sestavte lekci:

   ```bash
   Rscript -e 'sandpaper::build_lesson()'
   ```

   Hotový web najdete ve složce `site/docs/` (otevřete `site/docs/index.html`). Při úpravách
   se hodí živý náhled, který se po každém uložení souboru sám obnoví:

   ```bash
   Rscript -e 'sandpaper::serve()'
   ```

Složka `site/` je v `.gitignore`, takže se do repozitáře nenahrává.

## Zveřejnění na GitHub Pages

Po každém pushi do větve `main` se web na GitHubu sestaví sám. Lokálně ho k tomu sestavovat
nemusíte.

1. **Doplňte údaje označené `FIXME`** v `config.yaml` (`source`, `contact`) a v tomhle README.

2. **Na GitHubu vytvořte nový veřejný repozitář** bez README a bez licence, třeba
   `python-novice-gapminder-cs`. (Pro veřejné repozitáře jsou GitHub Pages zdarma.)

3. **Nahrajte do něj lekci:**

   ```bash
   cd ~/personal/python-novice-gapminder-cs
   git init -b main
   git add .
   git commit -m "Česká verze lekce Plotting and Programming in Python (epizody 1–3)"
   git remote add origin https://github.com/UZIVATEL/python-novice-gapminder-cs.git
   git push -u origin main
   ```

   S GitHub CLI zvládnete kroky 2 a 3 najednou:
   `gh repo create python-novice-gapminder-cs --public --source=. --push`.

4. **Zafixujte verzi Workbench** (doporučuju): _Settings → Secrets and variables → Actions →
   Variables → New repository variable_, název `WORKBENCH_TAG`, hodnota `v0.2.9`
   (stejná jako v souboru `.github/workbench-docker-version.txt`).
   Jinak se po vydání nové verze Workbench sestavení přeskočí a workflow se místo něj pokusí
   otevřít pull request s novou verzí.

5. **Spusťte sestavení:** na kartě _Actions_ by se po pushi mělo samo rozběhnout
   _01 Maintain: Build and Deploy Site_. Pokud ne, vyberte ho vlevo a klikněte na _Run workflow_.
   Trvá to pár minut a na konci vznikne větev `gh-pages`.

6. **Zapněte GitHub Pages:** _Settings → Pages → Build and deployment → Deploy from a branch_,
   větev `gh-pages`, složka `/ (root)`, _Save_. Web pak poběží na adrese
   `https://UZIVATEL.github.io/python-novice-gapminder-cs/`.

7. **Přidejte odkaz na web do popisu repozitáře:** na kartě _Code_ klikněte v části _About_
   na ozubené kolo a zaškrtněte _Use your GitHub Pages website_.

Kdyby sestavení spadlo na oprávněních (chyba 403 při pushi do `gh-pages`), nastavte
_Settings → Actions → General → Workflow permissions_ na _Read and write permissions_.

Další workflow Workbench (náhledy pull requestů, automatické aktualizace) můžete kdykoli
doplnit příkazem `Rscript -e 'sandpaper::update_github_workflows()'`. Ke zveřejnění
potřeba nejsou.

## Známá omezení

- **České rozhraní je z forku.** Workbench sám umí jen en, de, es, fr, it, ja a uk.
  Český překlad je proto v mém forku balíčku `sandpaper` a lekce ho používá díky řádku
  `sandpaper: 'Kharianne/sandpaper'` v `config.yaml`. Když The Carpentries vydají novou
  verzi, je potřeba fork synchronizovat (_Sync fork_ na GitHubu). Kdyby čeština přibyla
  přímo do `sandpaper`, stačí ten řádek z `config.yaml` smazat.
- **Snímky obrazovky** ukazují anglické rozhraní JupyterLabu (to je výchozí).
- **Logo:** Workbench oficiálně zná jen loga The Carpentries a na vlastní logo je potřeba fork
  balíčku `varnish`. Tahle lekce to obchází nastavením `carpentry: '../../fig/kurz'`, takže se
  logo načte ze souborů `episodes/fig/kurz-logo.svg` a `kurz-logo-sm.svg`. Kdyby to nějaká
  budoucí verze Workbench rozbila, zobrazí se v záhlaví jen alternativní text. Čisté řešení
  popisuje [dokumentace Workbench](https://carpentries.github.io/sandpaper-docs/editing.html).
- **Fáze vývoje _beta_** přidává do záhlaví štítek, že je lekce ve vývoji. Až lekci
  vyzkoušíte ve výuce, můžete v `config.yaml` nastavit `life_cycle: 'stable'`.
