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

```{python}
K = 1
r = 2
x = 0.5
rychlost = r*x*(1-x/K)
```

## Nastavení hodnot pro postupné opakované provádění operací v cyklu

```{python}
stromy = ["topol","javor","buk","akát","jírovec"]
for strom in stromy:
    print (f"zpracovavam {strom}")
```

Pokud potřebujeme sledovat informaci, kolikátá otočka cyklu se provádí, použijeme příkaz `enumerate`.

```{python}
stromy = ["topol","javor","buk","akát","jírovec"]
for i,strom in enumerate(stromy):
    print (f"zpracovavam {strom}, v seznamu položa s indexem {i}")
```


## Nastavení definičního oboru pro funkce
 
Nejčastěji proměnnou tohoto typu tvoříme pomocí příkazu `linspace` knihovny `numpy`. K tomu, aby byl tento příkaz přístupný, si musíme knihovnu numpy naimportovat. Parametry příkazu jsou počáteční a koncový bod intervalu. Třetí nepovinný parametr značí počet bodů uvažovaných z tohoto intervalu. 

Následující ukázka do proměnné `t` uloží 300 hodnot rovnoměrně rozdělených na intervalu $[0,10]$. Jak ukázka použití je vykrelsení grafu funkce sinus. Tato funkce je součástí balíčku `numpy` a graf vykreslujeme pomocí knihovny `matplotlib`.

```{python}
import numpy as np
import matplotlib.pyplot as plt
t = np.linspace(0,10,300)
plt.plot(t,np.sin(t))
```

## Vytvoření pole s vypočtenými daty

```
import numpy as np
import matplotlib.pyplot as plt

N = 300
seznam_k = list(range(1,6))
t = np.linspace(0,3.14,N)

X = np.zeros((N,len(seznam_k)))

for i,k in enumerate(seznam_k):
    X[:,i] = np.sin(k*t)

plt.plot(t,X)
plt.legend(seznam_k)
plt.show()


```
 