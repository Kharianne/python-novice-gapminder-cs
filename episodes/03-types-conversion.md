---
title: Datové typy a převody typů
teaching: 10
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Vysvětlit, čím se liší typ integer (celé číslo) od typu float (desetinné číslo).
- Vysvětlit, čím se liší čísla od stringů (textových řetězců).
- Převádět hodnoty mezi typy integer, float a string pomocí built-in funkcí (vestavěných funkcí).

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- Jaké druhy dat program ukládá?
- Jak převedu hodnotu jednoho typu na jiný?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Každá hodnota má svůj typ

- Každá hodnota v programu má nějaký typ (_type_).
- **Integer** (`int`; celé číslo): kladná i záporná celá čísla, třeba 3 nebo -512.
- **Floating point number** (`float`; desetinné číslo, přesněji číslo s plovoucí řádovou čárkou): čísla s desetinnou částí, třeba 3.14159 nebo -2.5.
- **Character string** (`str`; textový řetězec, většinou se mu říká jen „string“): text.
  - Píše se do jednoduchých nebo dvojitých uvozovek. Hlavně aby byly na začátku i na konci stejné.
  - Když string vypíšete, uvozovky se nezobrazí.

::::::::::::::::::::::::::::::::::::::::: callout

## Desetinná tečka, ne čárka

V češtině píšeme desetinnou čárku (3,14), Python ale používá vždycky **tečku**: `3.14`.

Když napíšete `3,14`, Python to za chybu nepovažuje. Vezme to jako dvě samostatná čísla,
`3` a `14`, a udělá z nich tuple (n-tici), tedy skupinu hodnot:

```python
cislo = 3,14
print(cislo)
print(type(cislo))
```

```output
(3, 14)
<class 'tuple'>
```

::::::::::::::::::::::::::::::::::::::::::::::::::

## Typ hodnoty zjistíte funkcí `type`

- Built-in funkce (vestavěná funkce) `type` vám řekne, jakého typu je hodnota.
- Funguje i na proměnné.
  - Pozor ale: typ má _hodnota_, _proměnná_ je jen její štítek.

```python
print(type(52))
```

```output
<class 'int'>
```

```python
kondice = 'průměrná'
print(type(kondice))
```

```output
<class 'str'>
```

## Typ určuje, co s hodnotou můžete dělat

- Na typu záleží, jaké operace (nebo metody) na hodnotu půjdou použít.

```python
print(5 - 3)
```

```output
2
```

```python
print('ahoj' - 'a')
```

```error
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-2-67f5626a1e07> in <module>()
----> 1 print('ahoj' - 'a')

TypeError: unsupported operand type(s) for -: 'str' and 'str'
```

## Stringy můžete sčítat a násobit

- Když stringy „sečtete“, spojí se za sebe (_concatenation_).

```python
cele_jmeno = 'Ahmed' + ' ' + 'Walsh'
print(cele_jmeno)
```

```output
Ahmed Walsh
```

- Když string vynásobíte celým číslem (typu integer) _N_, dostanete nový string, ve kterém se ten původní _N_-krát opakuje.
  - Násobení je přece opakované sčítání.

```python
oddelovac = '=' * 10
print(oddelovac)
```

```output
==========
```

## Stringy mají délku (čísla ne)

- Built-in funkce `len` spočítá, kolik znaků string má.

```python
print(len(cele_jmeno))
```

```output
11
```

- Čísla délku nemají, ani nulovou.

```python
print(len(52))
```

```error
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-3-f769e8e8097d> in <module>()
----> 1 print(len(52))

TypeError: object of type 'int' has no len()
```

## Čísla a stringy musíte před počítáním převést {#convert-numbers-and-strings}

- Číslo a string sečíst nejde.

```python
print(1 + '2')
```

```error
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-4-fe4f54a023c6> in <module>()
----> 1 print(1 + '2')

TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

- Python neví, co byste chtěli: má být `1 + '2'` rovno `3`, nebo `'12'`?
- Hodnotu převedete na jiný typ tak, že název typu použijete jako funkci.

```python
print(1 + int('2'))
print(str(1) + '2')
```

```output
3
12
```

## Integer a float se dají volně kombinovat

- V aritmetice můžete hodnoty typu integer a float klidně míchat.
  - Python 3 si integer podle potřeby sám převede na float.

```python
print('polovina je', 1 / 2.0)
print('tři na druhou je', 3.0 ** 2)
```

```output
polovina je 0.5
tři na druhou je 9.0
```

## Proměnná se změní, jen když do ní něco přiřadíte

- V tabulkovém procesoru (třeba v Excelu) můžete nastavit, aby jedna buňka počítala
  s hodnotou z jiné. Když tu druhou změníte, první se sama přepočítá.
- V programovacích jazycích to tak **nefunguje**.

```python
prvni_promenna = 1
druha_promenna = 5 * prvni_promenna
prvni_promenna = 2
print('první je', prvni_promenna, 'a druhá je', druha_promenna)
```

```output
první je 2 a druhá je 5
```

- Při násobení si počítač přečte hodnotu `prvni_promenna`, spočítá výsledek a uloží ho
  do `druha_promenna`.
- Tím to končí. `druha_promenna` už na `prvni_promenna` _nijak nezávisí_, takže se
  nezmění, ani když později změníte `prvni_promenna`.

::::::::::::::::::::::::::::::::::::::: challenge

## Desetinná čísla

Jakého typu je hodnota 3.4?
Jak to zjistíte?

::::::::::::::: solution

## Řešení

Je to floating point number (desetinné číslo), zkráceně „float“.
Zjistíte to pomocí built-in funkce `type()`.

```python
print(type(3.4))
```

```output
<class 'float'>
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Automatický převod typů

Jakého typu je hodnota 3.25 + 4?

::::::::::::::: solution

## Řešení

Je to float.
Python integer podle potřeby sám převede na float.

```python
vysledek = 3.25 + 4
print(vysledek, 'je', type(vysledek))
```

```output
7.25 je <class 'float'>
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Jaký typ zvolit?

Jaký typ (integer, float, nebo string) byste použili pro tyhle údaje? Zkuste u každého
najít víc než jednu rozumnou odpověď. Kdy by třeba v bodě 1 dávalo smysl počítat dny
jako float, a ne jako integer?

1. Počet dní od začátku roku.
2. Kolik dní uplynulo od začátku roku do teď.
3. Výrobní číslo laboratorního přístroje.
4. Stáří vzorku v laboratoři.
5. Současný počet obyvatel města.
6. Průměrný počet obyvatel města za nějaké období.

::::::::::::::: solution

## Řešení

1. Integer, protože počet dní bude mezi 1 a 366.
2. Float, protože potřebujete i části dní.
3. String, pokud výrobní číslo obsahuje písmena i číslice. Pokud má jen číslice, stačí integer.
4. Záleží na tom, jak stáří vzorku chápete. Celé dny od odběru (integer)? Datum a čas odběru (string)?
5. Float, pokud chcete počet obyvatel uvádět třeba v milionech, nebo integer, pokud počítáte jednotlivé lidi.
6. Float, protože průměr bude nejspíš mít desetinnou část.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Druhy dělení

V Pythonu 3 dělá operátor `//` floor division (celočíselné dělení, výsledek se zaokrouhlí dolů),
operátor `/` obyčejné dělení s výsledkem typu float a operátor `%` (_modulo_) vrátí zbytek
po celočíselném dělení:

```python
print('5 // 3:', 5 // 3)
print('5 / 3:', 5 / 3)
print('5 % 3:', 5 % 3)
```

```output
5 // 3: 1
5 / 3: 1.6666666666666667
5 % 3: 2
```

Řekněme, že `pocet_ucastniku` je počet účastníků studie
a `pocet_na_pruzkum` je počet lidí, kteří se vejdou do jednoho průzkumu.
Napište výraz, který spočítá, kolik průzkumů potřebujete,
aby se každý účastník zúčastnil právě jednou.

::::::::::::::: solution

## Řešení

Hledáte nejmenší počet průzkumů, při kterém se dostane na všechny, tedy
`pocet_ucastniku / pocet_na_pruzkum` zaokrouhlené nahoru. To je totéž jako floor division
pomocí `//` plus 1. Před dělením ale musíte od počtu účastníků odečíst 1, jinak by výsledek
nevyšel v případě, kdy jde `pocet_ucastniku` vydělit číslem `pocet_na_pruzkum` beze zbytku.

```python
pocet_ucastniku = 600
pocet_na_pruzkum = 42
pocet_pruzkumu = (pocet_ucastniku - 1) // pocet_na_pruzkum + 1

print(pocet_ucastniku, 'účastníků,', pocet_na_pruzkum, 'na průzkum:', pocet_pruzkumu)
```

```output
600 účastníků, 42 na průzkum: 15
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Ze stringů na čísla

Pokud to dává smysl, `float()` převede string na číslo typu float
a `int()` převede float na integer:

```python
print("string na float:", float("3.4"))
print("float na int:", int(3.4))
```

```output
string na float: 3.4
float na int: 3
```

Když ale převod smysl nedává, dostanete chybovou hlášku.

```python
print("string na float:", float("Ahoj světe!"))
```

```error
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-5-df3b790bf0a2> in <module>
----> 1 print("string na float:", float("Ahoj světe!"))

ValueError: could not convert string to float: 'Ahoj světe!'
```

Co podle vás udělá tenhle program?

Co doopravdy udělá?

Proč asi?

```python
print("desetinný string na int:", int("3.4"))
```

::::::::::::::: solution

## Řešení

Co jste čekali? Nebylo by divné, kdyby funkce `int` převedla string "3.4" nejdřív na 3.4
a pak na 3. Python přece umí spoustu jiných kouzel – není to snad součást jeho kouzla?

```python
int("3.4")
```

```output
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-2-ec6729dfccdc> in <module>
----> 1 int("3.4")
ValueError: invalid literal for int() with base 10: '3.4'
```

Python 3 ale ohlásí chybu. Proč? Nejspíš kvůli důslednosti. Když chcete dva převody typů
po sobě, musíte je v kódu napsat výslovně:

```python
int(float("3.4"))
```

```output
3
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Počítání s různými typy

Které z těchto výrazů vrátí číslo typu float `2.0`?
Správných odpovědí může být víc.

```python
prvni = 1.0
druhy = "1"
treti = "1.1"
```

1. `prvni + float(druhy)`
2. `float(druhy) + float(treti)`
3. `prvni + int(treti)`
4. `prvni + int(float(treti))`
5. `int(prvni) + int(float(treti))`
6. `2.0 * druhy`

::::::::::::::: solution

## Řešení

Odpověď: 1 a 4

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

## Komplexní čísla

Python umí i komplexní čísla.
Píšou se jako `1.0+2.0j`.
Když je `hodnota` komplexní číslo,
k jeho reálné a imaginární části se dostanete přes _dot notation_ (tečkovou notaci):
`hodnota.real` a `hodnota.imag`.

```python
komplexni_cislo = 6 + 2j
print(komplexni_cislo.real)
print(komplexni_cislo.imag)
```

```output
6.0
2.0
```

1. Proč podle vás Python píše imaginární část s `j`, a ne s `i`?
2. Co podle vás vrátí `1 + 2j + 3`?
3. Co bude `4j`? A co `4 j` nebo `4 + j`?

::::::::::::::: solution

## Řešení

1. V matematice se imaginární jednotka obvykle značí `i`. Python ale převzal zvyklost
   z elektrotechniky, kde písmeno `i` znamená elektrický proud, a imaginární jednotka se
   proto značí `j`.
   [Víc se o tom píše na Stack Overflow (anglicky).](https://stackoverflow.com/questions/24812444/why-are-complex-numbers-in-python-denoted-with-j-instead-of-i)
2. `(4+2j)`
3. `4j` je komplexní číslo s imaginární částí 4. Zápis `4 j` skončí chybou `SyntaxError: invalid syntax`.
   Ve výrazu `4 + j` Python bere `j` jako proměnnou, takže výsledek závisí na tom, jestli
   `j` existuje a co v ní je. Když neexistuje, skončí výraz chybou `NameError`.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- Každá hodnota má svůj typ.
- Typ hodnoty zjistíte funkcí `type`.
- Typ určuje, co s hodnotou můžete dělat.
- Stringy můžete sčítat a násobit.
- Stringy mají délku (čísla ne).
- Čísla a stringy musíte před počítáním převést.
- Integer a float se dají volně kombinovat.
- Proměnná se změní, jen když do ní něco přiřadíte.

::::::::::::::::::::::::::::::::::::::::::::::::::
