# Typy proměnných

Nejčastější použití proměnných zahrnuje následující:

* nastavení parametrů pro výpočet, například parametry prostředí při modelování růstu populace nebo počáteční podmínky pro simulaci;
* uložení vypočtených hodnot;
* nastavení hodnot pro postupné opakované provádění operací v cyklu, například můžeme simulovat růst populace pro různé hodnoty nosné kapacity prostředí;
* nastavení definičního oboru pro funkce, například můžeme nastavit, že nás zajímá simulace po jednotlivých dnech pro celkem deset let;
* vytvoření pole s vypočtenými daty, což umožní oddělit fázi výpočtu dat od jejich zpracování a vizualizace;
* vytvoření tabulky s vypočtenými daty, což odpovídá předchozímu bodu, ale s použitím jiného typu proměnných;
* načtení dat z externí tabulky, například v Excelu, pro další zpracování.

Poslední dva body (tabulky) necháme na jindy a nejprve se budeme věnovat ostatním.

## Nastavení parametrů a uložení vypočtených hodnot

```
K = 1
r = 2
x = 0.5
rychlost = r*x*(1-x/K)
```
