---
title: Proměnné a přiřazení
teaching: 10
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Psát programy, které ukládají jednoduché hodnoty do proměnných a počítají s nimi.
- Umět sledovat, jak se hodnoty proměnných v programu mění.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- Jak si program zapamatuje data?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Hodnoty ukládejte do proměnných

- **Proměnná** (_variable_) je název pro nějakou hodnotu.

- Pro názvy proměnných platí několik pravidel:

  - smí obsahovat **jen** písmena, číslice a podtržítko `_` (to se hodí k oddělení slov v delších názvech),
  - nesmí začínat číslicí,
  - **záleží v nich na velikosti písmen**, takže `vek`, `Vek` a `VEK` jsou tři různé proměnné.

- Python 3 sice v názvech povolí i česká písmena s diakritikou (třeba `věk`), ale v praxi
  se skoro vždy píšou bez ní. Budeme to tak dělat i my.

- Název by měl dávat smysl, aby vy i ostatní věděli, co v proměnné je.

- Názvy, které začínají podtržítky (třeba `__skutecny_vek_alistaira`), mají v Pythonu
  zvláštní význam. Dokud nebudete vědět jaký, raději se jim vyhněte.

- Znaménko `=` uloží hodnotu napravo pod název nalevo. Říká se tomu přiřazení.

- Proměnná vznikne ve chvíli, kdy do ní poprvé něco přiřadíte.

- Tady Python uloží věk do proměnné `vek`
  a jméno v uvozovkách do proměnné `jmeno`:

  ```python
  vek = 42
  jmeno = 'Ahmed'
  ```

## Hodnoty vypisujte pomocí `print`

- K vypisování slouží funkce `print`. Je to built-in function (vestavěná funkce),
  takže ji máte v Pythonu k dispozici vždycky, nic nemusíte instalovat ani importovat.
- Funkci zavoláte (řeknete Pythonu, aby ji spustil) jejím názvem.
- Do kulatých závorek za název napíšete, co má funkce dostat – tady to, co se má vypsat.
- Text, kterému se v Pythonu říká string (textový řetězec), dejte do jednoduchých nebo dvojitých uvozovek.
- Hodnotám, které funkci předáváte, se říká **argumenty** (_arguments_).

```python
print(jmeno, 'má', vek, 'let')
```

```output
Ahmed má 42 let
```

- `print` sám vloží mezi jednotlivé hodnoty mezeru.
- A na konci odřádkuje.

## Proměnná musí existovat dřív, než ji použijete

- Pokud proměnná ještě neexistuje nebo máte v jejím názvu překlep, Python ohlásí chybu.
  (Některé jiné jazyky si v takové situaci výchozí hodnotu „domyslí“, Python ne.)

```python
print(prijmeni)
```

```error
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-c1fbb4e96102> in <module>()
----> 1 print(prijmeni)

NameError: name 'prijmeni' is not defined
```

- Nejvíc vám obvykle řekne poslední řádek chybové hlášky. Tady se v něm píše, že název
  `prijmeni` není definovaný (_is not defined_).
- Chybovým hláškám se podrobně věnuje [epizoda o rozsahu platnosti proměnných v původní anglické lekci](https://swcarpentry.github.io/python-novice-gapminder/17-scope.html#reading-error-messages).

::::::::::::::::::::::::::::::::::::::::: callout

## Proměnné přežívají mezi buňkami

Pozor: v Jupyter notebooku záleží na tom, _v jakém pořadí buňky spouštíte_, ne na tom,
jak jsou v notebooku seřazené. Python si pamatuje všechno, co jste dosud spustili, včetně
proměnných. Pokud tedy nadefinujete proměnnou v buňce níž a pak (znovu) spustíte buňku
nad ní, proměnná už tam bude existovat. Zkuste si to: vytvořte dvě buňky v tomhle pořadí.

```python
print(moje_hodnota)
```

```python
moje_hodnota = 1
```

Když je spustíte popořadě, první buňka skončí chybou. Když ale první buňku spustíte až
_po_ té druhé, vypíše `1`. Abyste se do toho nezamotali, používejte volbu
`Kernel` -> `Restart Kernel and Run All Cells...`. Ta Python „vynuluje“ a spustí všechny
buňky načisto odshora dolů.

::::::::::::::::::::::::::::::::::::::::::::::::::

## Proměnné můžete používat ve výpočtech

- S proměnnou se počítá stejně jako s hodnotou, která je v ní uložená.
  - Do proměnné `vek` jsme před chvílí uložili `42`.

```python
vek = vek + 3
print('Věk za tři roky:', vek)
```

```output
Věk za tři roky: 45
```

## Jednotlivý znak ze stringu získáte pomocí indexu

- Znaky ve stringu (písmena, číslice a další) mají své pořadí. `'AB'` tedy není totéž co `'BA'`.
  Díky tomu se stringem můžete zacházet jako se seznamem znaků.
- Každá pozice ve stringu (první, druhá…) má své číslo. Tomu se říká **index**
  (někdy taky _subscript_).
- Indexy se počítají od nuly.
- Znak na určité pozici získáte tak, že index napíšete do hranatých závorek.

![Řádek kódu v Pythonu print(nazev_atomu[0]) ukazuje, že s indexem nula dostaneme jen první písmeno, v tomto případě 'h' ze slova helium.](fig/2_indexing.svg){alt="Řádek kódu v Pythonu print(nazev_atomu[0]) nad písmeny slova helium s indexy 0 až 5; zvýrazněné je písmeno h s indexem 0."}

```python
nazev_atomu = 'helium'
print(nazev_atomu[0])
```

```output
h
```

## Část stringu vyříznete pomocí slice

- Části stringu se říká **substring** (podřetězec). Může mít i jen jeden znak.
- Položce v listu (seznamu) se říká prvek (_element_). Když se stringem zacházíte jako
  se seznamem, jeho prvky jsou jednotlivé znaky.
- **Slice** (výřez) je kus stringu, nebo obecně kus čehokoli, co se chová jako seznam.
- Slice se píše jako `[start:stop]`. `start` je index prvního znaku, který chcete,
  a `stop` je index znaku _hned za_ tím posledním, který chcete. Oba indexy jsou
  typu integer (celé číslo).
- Rozdíl `stop - start` je délka slice.
- Původní string se tím nezmění. Slice vám vrátí kopii jeho části.

```python
nazev_atomu = 'sodík'
print(nazev_atomu[0:3])
```

```output
sod
```

## Délku stringu zjistíte funkcí `len`

```python
print(len('helium'))
```

```output
6
```

- Vnořené funkce se vyhodnocují zevnitř ven, stejně jako v matematice.

## Python rozlišuje velká a malá písmena

- Pro Python jsou velká a malá písmena různé znaky, takže `Jmeno` a `jmeno` jsou dvě různé proměnné.
- Pro velká písmena na začátku názvů platí určité zvyklosti. Zatím proto pište názvy
  proměnných malými písmeny.

## Pojmenovávejte proměnné srozumitelně

- Pythonu je jedno, jak proměnné pojmenujete, pokud dodržíte pravidla
  (písmena, číslice a podtržítko):

```python
flabadab = 42
ewr_422_yY = 'Ahmed'
print(ewr_422_yY, 'má', flabadab, 'let')
```

- Lidem, kteří budou váš kód číst, to ale jedno není. Volte názvy, ze kterých je jasné, co program dělá.
- Nejčastěji ten kód budete číst vy sami. Za půl roku.

::::::::::::::::::::::::::::::::::::::: challenge

## Prohození hodnot

Doplňte do tabulky, jaké hodnoty mají proměnné
_po_ provedení každého řádku.

```python
# Příkaz      # Hodnota x   # Hodnota y   # Hodnota pomocna #
x = 1.0       #             #             #                 #
y = 3.0       #             #             #                 #
pomocna = x   #             #             #                 #
x = y         #             #             #                 #
y = pomocna   #             #             #                 #
```

::::::::::::::: solution

## Řešení

```output
# Příkaz      # Hodnota x   # Hodnota y   # Hodnota pomocna #
x = 1.0       # 1.0         # neexistuje  # neexistuje      #
y = 3.0       # 1.0         # 3.0         # neexistuje      #
pomocna = x   # 1.0         # 3.0         # 1.0             #
x = y         # 3.0         # 3.0         # 1.0             #
y = pomocna   # 3.0         # 1.0         # 1.0             #
```

Tyhle tři řádky prohodí hodnoty proměnných `x` a `y`. Proměnná `pomocna` přitom slouží
jako odkladiště. Tenhle obrat se v programování používá docela často.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Odhadněte hodnotu

Jakou hodnotu bude mít proměnná `pozice` na konci tohoto programu?
(Zkuste to nejdřív odhadnout bez spuštění a pak si odhad ověřte.)

```python
pocatecni = 'vlevo'
pozice = pocatecni
pocatecni = 'vpravo'
```

::::::::::::::: solution

## Řešení

```python
print(pozice)
```

```output
vlevo
```

Do proměnné `pocatecni` se nejdřív uloží `'vlevo'`.
Na druhém řádku dostane stejnou hodnotu i proměnná `pozice`.
Na třetím řádku se do `pocatecni` uloží `'vpravo'`,
ale `pozice` si nechá svou původní hodnotu `'vlevo'`.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Číslice čísla

Když přiřadíte `a = 123`,
co se stane, pokud se pokusíte získat druhou číslici pomocí `a[1]`?

::::::::::::::: solution

## Řešení

Číslo není string ani jiná sekvence, takže ho indexovat nejde a Python ohlásí chybu.
O typech a o tom, jak mezi nimi převádět, je [další epizoda](03-types-conversion.md).
Pokud chcete N-tou číslici čísla, převeďte ho funkcí `str` na string a ten pak indexujte.

```python
a = 123
print(a[1])
```

```error
TypeError: 'int' object is not subscriptable
```

```python
a = str(123)
print(a[1])
```

```output
2
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Jaký název zvolit?

Který název proměnné je lepší: `m`, `min`, nebo `minuty`?
Proč?
Nápověda: představte si, že kód přebíráte po kolegovi, který odchází z týmu.
Který z těchto řádků byste chtěli dostat?

1. `ts = m * 60 + s`
2. `cel_sek = min * 60 + sek`
3. `celkem_sekund = minuty * 60 + sekundy`

::::::::::::::: solution

## Řešení

Nejlepší je `minuty`. U `min` není jasné, jestli nejde třeba o „minimum“,
a navíc se tak v Pythonu jmenuje existující built-in funkce.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Procvičte si slice

Co vypíše tento program?

```python
nazev_atomu = 'uhlík'
print('nazev_atomu[1:3] je:', nazev_atomu[1:3])
```

::::::::::::::: solution

## Řešení

```output
nazev_atomu[1:3] je: hl
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Jak funguje slice

Máte tento string:

```python
nazev_druhu = "Acacia buxifolia"
```

Co vrátí tyto výrazy?

1. `nazev_druhu[2:8]`
2. `nazev_druhu[11:]` (za dvojtečkou nic není)
3. `nazev_druhu[:4]` (před dvojtečkou nic není)
4. `nazev_druhu[:]` (jen dvojtečka)
5. `nazev_druhu[11:-3]`
6. `nazev_druhu[-5:-3]`
7. Co se stane, když jako `stop` zadáte číslo mimo rozsah stringu? (Zkuste třeba `nazev_druhu[0:20]` nebo `nazev_druhu[:103]`.)

::::::::::::::: solution

## Řešení

1. `nazev_druhu[2:8]` vrátí `'acia b'`.
2. `nazev_druhu[11:]` vrátí `'folia'`, tedy všechno od pozice 11 do konce.
3. `nazev_druhu[:4]` vrátí `'Acac'`, tedy všechno od začátku po pozici 4 (tu už ne).
4. `nazev_druhu[:]` vrátí celý string `'Acacia buxifolia'`.
5. `nazev_druhu[11:-3]` vrátí `'fo'`, tedy znaky od pozice 11 po třetí pozici od konce (tu už ne).
6. `nazev_druhu[-5:-3]` vrátí taky `'fo'`, tedy znaky od páté pozice od konce po třetí od konce (tu už ne).
7. Nic zlého. Když slice sahá mimo string, Python prostě vrátí, co tam je: `nazev_druhu[0:20]` dá totéž co `nazev_druhu[0:]` a `nazev_druhu[:103]` totéž co `nazev_druhu[:]`.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- Hodnoty ukládejte do proměnných.
- Hodnoty vypisujte pomocí `print`.
- Proměnné přežívají mezi buňkami.
- Proměnná musí existovat dřív, než ji použijete.
- Proměnné můžete používat ve výpočtech.
- Jednotlivý znak ze stringu získáte pomocí indexu.
- Část stringu (substring) vyříznete pomocí slice.
- Délku stringu zjistíte funkcí `len`.
- Python rozlišuje velká a malá písmena.
- Pojmenovávejte proměnné srozumitelně.

::::::::::::::::::::::::::::::::::::::::::::::::::
