# Kit a Chen #

## Členové týmu ##

| **Jméno** | **Role** |
| --- | --- |
| David Hořák | Leader, návrh SW architektury, senior SW |
| Tomáš Bušek | Tvorba diagramů, junior SW |
| Nikol Šimová | Správa dat, junior SW |
| Barbara Žáčková | Junior SW |
| Milan Stehík | GUI developer, UXD, junior SW |

## Zadání úlohy ##

**Vedení kuchyně (3-4 řešitelé)**

Aplikace bude sloužit pro správu receptů, potřebných surovin, skladových zásob, plánování jídel a nákupů surovin.

**Rozšíření aplikace (5 řešitelů)** Aplikace umožní dále export denního menu a stavu skladových zásob, popř. seznamu surovin nutných k dokoupení.



## Seznam úkolů ##

| **Úkol** | **Řešitel(é)** |
| --- | --- |
| Návrh SW architektury aplikace | David Hořák |
| Návrh třídy, obsluhující skladové zásoby | Tomáš Bušek |
| Dodělat třídu pro vytvoření denního menu | Nikol Šímová, David Hořák |
| Třída a metody pro export menu a sklad. Zásob do PDF | Barbara Žáčková |
| Funkce kontroly skladových zásob oproti plánovanému menu | Tomáš Bušek |
| Návrh uživatelského rozhraní | Milan Stehlík |
| Testování použitelnosti | Milan Stehlík |
| Implementace SW architektury | David Hořák |
| Naplnění daty (obrázky, data...) | Nikol Šímová |
| Bug testing | Tomáš Bušek |
| Funkčnost nástrojové lišty | Barbara Žáčková |



## Use Case Diagram - obrázek z CASE nástroje ##

![Use Case Diagram - obrázek z CASE nástroje](https://github.com/simn00/Kuchyn-/blob/master/pasted%20image%200.png?raw=true)

## Slovní popis pro Use Case ##

**Správa menu:**

*Summary* - Dochází k vytváření, úpravě a mazání menu související s jednotlivými dny

*Actor* - Šéfkuchař, manažer

*Precondition* - Uživatel, nacházející se v aplikaci, zvolí zda chce vytvořit, upravit či smazat menu, které se skládá z jednotlivých receptů

*Postcondition* - Denní menu je připravené k použití

*Základní scénář*

1) User zvolí zobrazit menu (viz Zobrazení menu)

2) User vybere konkrétní menu

3) Systém zobrazí konkrétní menu

4) User provede změny v menu

5) Systém zkontroluje správnost vložených hodnot

6) Systém uloží změny

*Alternativní scénář A* - tvorba nového menu

2A. User zvolí vytvoření nového menu

3A. Systém zobrazí formulář pro nové menu

4A. USr vytvoří nové menu

5A. Systém zkontroluje správnost vložených hodnot

6A. Systém uloží změny

*Alternativní scénář B*

6B. Systém odhalí chybu vstupních údajů

7B. User opraví vstupní údaje

8B. Systém uloží vstupní údaje



**Zobrazení menu:**

*Summary* - Dochází k zobrazení menu

*Actor* - Manažer, šéfkuchař, nákupčí

*Precondition* - Je vytvořeno menu, které se skládá z receptů a z počtu jejich variant. Menu je označeno vždy datumem

*Postcondition* - Uživateli se zobrazí menu přesně dle jeho potřeb

*Základní scénář*

1. 1)User zažádá o zobrazení menu
2. 2)Pokud jsou k dispozici, systém vypíše dostupná menu

*Alternativní scénář*

2b) Pokud uživatel nemá práva, nebude mu povolen přístup do menu

*Alternativní scénář*

3b) Pokud menu není vytvořeno, zkontroluje se, zda má uživatel přístup ke správě menu
        4a) Pokud má přístup -&gt; přestup na Správu skladu

4b) Pokud nemá přístup -&gt; Chybová hláška



**Správa receptů:**

*Summary* - Dochází k vytváření, úpravě a mazání receptů.

*Actor* - Manažer, šéfkuchař

*Precondition* - Uživatel je přihlášen v aplikaci, zvolí zda chce vyvořit, upravit či smazat recept.

*Postcondition* - V databázi je zapsán recept, který lze dále používat, například přidat do poledního menu.

*Základní scénář A* - Tvorba nového receptu:

1) User vejde do složky seznam receptů

2) User klikne a tlačítko &quot;Nový recept&quot;

3) User vyplní název receptu

4) Zvolí o jaký se jedná chod

5) Vloží suroviny a jejich množství, které jsou pro recept potřeba.

6) Vloží případnou poznámku.

7) Uloží recept kliknutím na tlačítko &quot;Vytvořit&quot;

*Základní scénář B* - Úprava receptů

1) User vejde do složky seznam receptů

2) Klikne na recept, který chce upravit

3) Upraví položky, které chce upravit

4) Vše uloží kliknutím na tlačítko &quot;vytvořit&quot;

Základní scénář C - Vymazání receptu

1) User vejde do složky seznam receptů

2) Klikne na recept, který chce vymazat

3) Vymaže recept kliknutím na tlačítko smazat



**Export surovin k nákupu:**

*Summary* - Dochází k vyexportování informací do souboru, jaké suroviny a v jakém množství je potřeba nakoupit.

*Actor* - Manažer, nákupčí

*Precondition* - Uživatel zvolí možnosti &#39;&#39;výpis potřebných suroviny&#39;&#39;

*Postcondition* - Uživatel má kompletní seznam surovin, které jsou potřeba nakoupit.

*Základní scénář*

1. 1)User v hlavním menu klikne na tlačítko sklad
2. 2)Dále klikne na tlačítko Export potřebných surovin
3. 3)Soubor ve formátu doc se uživateli automaticky stáhne do počítače



**Zobrazení skladu:**

*Summary* - Zobrazení skladu se surovinami

*Actor* - šéfkuchař, nákupčí, manažer

*Precondition* - Je vytvořen sklad, ve kterém jsou uchovávány suroviny, které šéfkuchař potřebuje k vaření
*PostCondition* - Zobrazí obsah skladu, tedy suroviny a jejich dostupné mnoštví

*Základní scénář*

1) Zkontroluje zda má uživatel práva na zobrazení skladu

        2) Pokud má uživatel práva, zkontroluje zda je sklad vytvořen

        3) Pokud je sklad vytvořen, zobrazí se obsah skladu se surovinami

*Alternativní scénář*

 2b) Pokud uživatel nemá práva, nebude mu povolen přístup do systému

*Alternativní scénář*

3b) Pokud sklad není vytvořen, zkontroluje se, zda má uživatel přístup ke správě menu
        4a) Pokud má přístup -&gt; přestup na Správu skladu

 4b) Pokud nemá přístup -&gt; Chybová hláška



**Správa skladu:**

*Summary* - Provádí se zde utváření, úprava a mazání skladu

*Actor* - nákupčí, manažer

*Precondition* - Uživatel si zvolí zda chce vytvořit, upravit či smazat sklad

*Postcondition* - Vytvoří se sklad, který obsahuje suroviny. Dále je možné tyto suroviny upravovat, mazat a vytvářet nové

*Základní scénář*

1) User dá Zobrazit sklad (viz. Zobrazení skladu)

2) User vybere sklad

3) Systém zkontroluje, jestli je sklad vytvořen

4) Pokud ano, systém zobrazí sklad

5) User provede změny ve skladu

6) Systém zkontroluje správnost vložených hodnot

7) Pokud jsou správné, systém uloží změny

*Základní scénář*

1) User dá Zobrazit sklad (viz. Zobrazení skladu)

2) User vybere sklad

3) Systém zkontroluje, jestli je sklad vytvořen

4) Pokud ano, systém zobrazí sklad

5) User vymaže sklad

*Alternativní scénář*

4b) Pokud ne, systém nabídne vytvoření nového skladu

5) Systém zobrazí formulář pro nový sklad

6) User vytvoří nový sklad

7) Systém zkontroluje správnost vložených hodnot

8) Systém uloží změny

*Alternativní scénář*

6b) Pokud nejsou správné, systém nahlásí chybu

7) User chybu opraví

8) Systém uloží změny



## Class diagram ##

![Class diagram](https://github.com/simn00/Kuchyn-/blob/master/class.PNG?raw=true)

## Popis struktury file systému ##

Jako databáze pro menu, recepty, sklad a suroviny bude použit formát csv, který bude zapisovat data a číst, oddělovat je pomocí je hlavně &quot;;&quot;. Tyto databáze budou uloženy separátně v hlavní složce aplikace. Pro data o restauraci používáme textový soubor, do kterého při prvním spuštění manažer vloží informace o restauraci.



## Návrh GUI ##

**Prototyp**

*Hlavní okno*

![](https://github.com/simn00/Kuchyn-/blob/master/sem2_1.PNG?raw=true)

*Menu Overview*

![](https://github.com/simn00/Kuchyn-/blob/master/sem2_2.PNG?raw=true)

*Recepty Overview*

![](https://github.com/simn00/Kuchyn-/blob/master/sem2_3.PNG?raw=true)

*Nový recept*

![](https://github.com/simn00/Kuchyn-/blob/master/sem2_4.PNG?raw=true)

*Recept detail*

![](https://github.com/simn00/Kuchyn-/blob/master/sem2_5.PNG?raw=true)

## Konvence, které si tým definoval pro svou práci ##

**1. Pojmenovávání tříd, proměnných, metod, ...**

1.1 Pro identifikátory (tříd, metod, proměnných, ...) používejte jména popisující jejich význam. Vyhýbejte se zkratkám. Jména by neměla být krátká (minimálně 3 znaky) ani příliš dlouhá (do 16 znaků).

1.2 Jména tříd začínají velkým písmenem. Pokud se použije více slov, všechna začínají velkým písmenem. Pro označení třídy se obvykle používá podstatné jména v jednotném čísle, které bývá doplněno o přívlastky (např. třídy Student, SeznamStudentu).

1.3 Jména metod, proměnných, formálních parametrů metod začínají malým písmenem. Pokud jméno obsahuje více slov, druhé a další začínají velkým písmenem.

1.4 Názvy konstant se píší celé velkými písmeny, v případě více slov se jednotlivá slova oddělují znakem podtržení, např. MAXIMALNI\_POCET.

**2. Formátování**
2.1 Na jednom řádku by měl být jeden příkaz, deklarace jedné proměnné.

2.2 Obsah bloku odsaďte vždy o 3 či 4 mezery. V rámci jednoho bloku by měly být všechny příkazy odsazeny stejně.

2.2 Otevírací závorka bloku je obvykle na konci řádku, uzavírací samostatná na řádku. Např.

     public static void main(String[] args) {
         int scitanec1 = 5;
         int scitanec2 = 2;
         System.out.println(&quot;Soucet je: &quot; + (scitanec1 + scitanec2));
     }

     while (&#39;&#39;podmínka&#39;&#39;) {
 &#39;&#39;příkazy&#39;&#39;
     }

     if (&#39;&#39;podmínka&#39;&#39;) {
 &#39;&#39;příkazy&#39;&#39;
     }
     else {
 &#39;&#39;příkazy&#39;&#39;
     }
2.3 V řídících strukturách vždy používejte složené závorky pro bloky a to i v případě, že v bloku je pouze jeden příkaz.

2.4 Používejte mezeru před otevírací závorkou a okolo operátorů.

**3. Dokumentace, komentáře**
3.1 Na začátku každé třídy uveďte:

- stručný popis třídy,
- autora či autory,
- označení verze (pořadové číslo či datum poslední změny).

Příklad:

 /\*\*
 \*  Třída SeznamAkci - obsahuje seznam přípustných příkazů adventury.
 \*  Používá se pro rozpoznávání jednotlivých příkazů.
 \*
 \*  Tato třída je součástí jednoduché textové hry.
 \*
 \*@author     Michael Kolling, Lubos Pavlicek, Jarmila Pavlickova
 \*@version    4.0
 \*@created    září 2006
 \*/
3.2 Před každou metodou by měl být její popis doplněný o popis významu jednotlivých parametrů a návratových hodnot. Příklad:

 /\*\*
 \* Metoda hledá nejvyšší hodnotu (maximum) v poli celých čísel.
 \*
 \*@param pole Pole celých čísel, které se bude prohledávat
 \*@return Vrací celé číslo s nejvyšší hodnotou
 \*/
3.3 Popisy tříd a metod by měly být ve formátu vhodném pro javadoc.

3.4 Vlastní kód doplňte o komentář pouze v nezbytných případech. Předpokládejte, že čtenář zdrojového textu zná Javu.

Konvence byly převzány z   [htt](https://java.vse.cz/4it101/Konvence) [ps://java.vse.cz/4it101/Konvence](https://java.vse.cz/4it101/Konvence)
