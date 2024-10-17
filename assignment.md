# Posloupnost čísel

- **Hodnocení:** 5.0 bodů (s bonusy až 6.6 bodů)
- **Termín odevzdání:** 14.11.2022 11:59:59

## Zadání

Úkolem je vytvořit program, který analyzuje zadanou číselnou posloupnost.

### Vstup
Předpokládáme posloupnost celých čísel. Z této posloupnosti vybíráme souvislé intervaly, například můžeme vybrat interval mezi 5. a 10. zadaným číslem. Interval musí obsahovat alespoň dvě čísla ze vstupní posloupnosti. Pro každý vybraný interval určíme součet čísel, která jej tvoří. Ze vstupní posloupnosti vybereme všechny možné intervaly a pro každý interval určíme jeho součet. Zajímá nás, kolik dvojic různých intervalů má stejný součet.

### Výstup
Výstupem programu je počet nalezených dvojic intervalů se stejným součtem.

#### Ukázka:

Pro vstupní posloupnost:

```
1 5 2 4 2 2 2
```

Existuje celkem 21 možných intervalů délky alespoň 2:

```
0..1:  1 5               suma=6
0..2:  1 5 2             suma=8
0..3:  1 5 2 4           suma=12
0..4:  1 5 2 4 2         suma=14
0..5:  1 5 2 4 2 2       suma=16
0..6:  1 5 2 4 2 2 2     suma=18
1..2:  5 2               suma=7
1..3:  5 2 4             suma=11
1..4:  5 2 4 2           suma=13
1..5:  5 2 4 2 2         suma=15
1..6:  5 2 4 2 2 2       suma=17
2..3:  2 4               suma=6
2..4:  2 4 2             suma=8
2..5:  2 4 2 2           suma=10
2..6:  2 4 2 2 2         suma=12
3..4:  4 2               suma=6
3..5:  4 2 2             suma=8
3..6:  4 2 2 2           suma=10
4..5:  2 2               suma=4
4..6:  2 2 2             suma=6
5..6:  2 2               suma=4
```

Z těchto 21 intervalů lze vybrat 12 dvojic různých intervalů se stejným součtem:

```
0..1 ~ 2..3             suma=6  
0..1 ~ 3..4             suma=6  
0..1 ~ 4..6             suma=6  
0..2 ~ 2..4             suma=8  
0..2 ~ 3..5             suma=8  
0..3 ~ 2..6             suma=12 
2..3 ~ 3..4             suma=6  
2..3 ~ 4..6             suma=6  
2..4 ~ 3..5             suma=8  
2..5 ~ 3..6             suma=10 
3..4 ~ 4..6             suma=6  
4..5 ~ 5..6             suma=4  
```

### Vstupní podmínky
Vstupem programu je posloupnost celých čísel (kladných, nulových i záporných). Zadávání vstupní posloupnosti končí po dosažení konce vstupu (EOF). Čísel ve vstupní posloupnosti může být nejvýše 2000.

### Detekce chyb
Program musí detekovat nesprávný vstup. Za chybu považujte:
- vstupní posloupnost je prázdná (obsahuje 0 čísel),
- vstupní posloupnost je příliš dlouhá (více než 2000 čísel),
- hodnota na vstupu není platné celé číslo.

### Hodnocení
Úloha je hodnocena v bonusovém režimu. Efektivita řešení může ovlivnit konečné hodnocení:
- neefektivní program může mít snížené body,
- efektivní program může získat bonusové body za rychlé zpracování delších posloupností.

## Ukázka práce programu

```
Posloupnost:
1 5 2 4
Pocet dvojic: 1

Posloupnost:
1 5 2 4 2 2 2
Pocet dvojic: 12

Posloupnost:
1 5 6
20 -20
Pocet dvojic: 3

Posloupnost:
2 2 1 7 7
Pocet dvojic: 0

Posloupnost:
1 1 2 3 5 8
Pocet dvojic: 0

Posloupnost:
abcd
Nespravny vstup.
```

## Nápověda

- Ukázkové běhy zachycují očekávané výpisy programu a vstupy zadané uživatelem. Zvýraznění tučným písmem je použité pouze zde pro lepší čitelnost. Program zobrazí text bez HTML markupu.
- Každý výstup musí končit znakem odřádkování (`\n`), včetně chybových hlášení.
- Naivní řešení se složitostí **O(n⁶)** projde všechny testy kromě testů rychlosti. Vylepšený algoritmus se složitostí **O(n⁴)** projde první test rychlosti. Druhý test rychlosti vyžaduje ještě efektivnější řešení.
- K dispozici je dostatek volné paměti (několik stovek MiB).
