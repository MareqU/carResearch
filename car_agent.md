Agent pro výběr spolehlivého auta
Hlavní cíl
Najít co nejspolehlivější auto do 250 000 Kč od spolehlivého prodejce.
Auto musí být praktické pro rodinu s manželkou a 1 dítětem.
Požadavky

Lokalita: Praha a okolí (preferováno)
Rozpočet: max 250 000 Kč
Značky a modely: Škoda Octavia, Škoda Rapid, VW Golf, VW Passat, Vw Touran, Vw Sharan
Palivo: benzín
Převodovka: manuál
Pohon: přední
Nájezd: max 150 000 km
Rok vyroby: od 2015
Posádka: řidič + manželka + 1 dítě
Priorita č.1: spolehlivost auta
Priorita č.2: spolehlivý prodejce
Priorita č.3: doložená servisní historie (výhoda, ne podmínka)


Nástroje
Vždy používej Playwright MCP pro veškeré procházení webů.
Nepoužívej Bash ani jiné nástroje pro přístup na internet.
Úkol B — Aktivní hledání napříč portály
Prohledej všechny tyto portály a na každém nastav stejné filtry:
PortálURLPoznámkaSautohttps://www.sauto.cz největší inzerce, soukromníci i bazaryAAA Autohttps://www.aaaauto.cznejvětší síť bazarů v ČR, https://www.autoesa.cz/
Na každém portálu nastav filtry:

Značka: Škoda (model: Octavia, Rapid) / Volkswagen (model: Golf, Passat, Trouran, Sharan)
Palivo: benzín
Převodovka: manuál
Pohon: přední
Cena: do 250 000 Kč
Nájezd: do 150 000 km
Rok vyroby: od 2015
Lokalita: Praha a okolí

Pro každý portál:

Projdi výsledky a vyber maximálně 3 nejzajímavější inzeráty — přednostně vyber inzeráty kde je zmíněna servisní historie nebo servisní knížka
Z každého inzerátu přečti: model, rok, motor, km, cena, prodejce, kontakt, popis, zmínka o servisní historii
Klikni na profil prodejce a přečti jeho hodnocení a počet recenzí
Zaznamenej z jakého portálu inzerát pochází

Úkol A — Analýza konkrétního inzerátu

Otevři zadanou URL pomocí Playwright MCP
Přečti všechny detaily přímo ze stránky inzerátu
Zjisti na jakém portálu inzerát je a klikni na profil prodejce — přečti jeho hodnocení
Otevři novou záložku a vyhledej recenze prodejce na google.com (název firmy + "recenze")
Pokud je prodejce na více portálech (sauto, aaaauto, tipcars...), zkontroluj hodnocení i tam
Otevři další záložku a vyhledej spolehlivost konkrétního motoru na auto.cz nebo autorevue.cz

Zvláštní pozornost věnuj: 1.2 TSI (rozvody, spotřeba oleje), 1.4 TSI (DSG problémy), 1.6 MPI (spolehlivý ale slabší)


Prověř VIN na cebia.cz pokud je v inzerátu uveden

Zásady pro práci s prohlížečem

Vždy počkej na plné načtení stránky před čtením obsahu
Pokud je stránka blokovaná nebo pomalá, zkus ji znovu načíst
Ukládej si URL každého navštíveného inzerátu pro závěrečný přehled


Rodinné požadavky — ověř u každého auta

Dostatek místa na zadních sedadlech pro dětskou sedačku
Velikost a přístupnost kufru (vejde se kočárek?)
Hodnocení NCAP bezpečnosti (min. 4 hvězdy)
ISO FIX pro dětskou sedačku (výhoda)
Dobrý výhled z auta při parkování


Poznámky k motorům
Při hodnocení spolehlivosti motoru zohledni:

✅ 1.6 MPI — starší, jednoduchý, velmi spolehlivý, bez turba, ale slabší
✅ 1.2 TSI (v Rapidu od 2012) — má již opravené řetězové rozvody, dobrá volba
✅ 1.6 TDI od roku 2015 — spolehlivější generace s lepšími vstřikovači
⚠️ 1.2 TSI (starší generace v Octavii/Golfu) — pozor na řetězové rozvody a spotřebu oleje
⚠️ 1.4 TSI — výkonný, ale nákladnější na servis, pozor na starší kusy
❌ 1.4 TDI 66 kW — vyhnout se, riziko prasknutí bloku motoru
❌ 1.4 TSI + DSG do roku 2015 — suché spojky DSG, nevhodné pro město a kolony


Struktura výstupního souboru pro každé auto
Pro každé nalezené auto vytvoř soubor auto_[model]_[rok]_[km].md:
Základní info

Model, rok výroby, motor (ccm, kW), převodovka, nájezd, cena
Odkaz na inzerát

Servisní historie

Je servisní historie zmíněna v inzerátu? ✅/❌
Servisováno v autorizovaném servisu nebo nezávislém?
Jsou doloženy faktury nebo servisní knížka?
Zkontroluj v inzerátu fotky servisní knížky — jsou záznamy pravidelné?
Velká servisní intervaly (výpadky) jsou červená vlajka ⚠️
Hodnocení servisní historie: ⭐⭐⭐⭐⭐

Spolehlivost modelu

Zdroje: auto.cz, autorevue.cz, TÜV Report
Typické závady tohoto modelu a generace
Jak na tom je tento konkrétní motor?
Hodnocení spolehlivosti modelu: ⭐⭐⭐⭐⭐

Hodnocení prodejce

Zdroje: profil na portálu inzerátu, ostatní portály (sauto, aaaauto, tipcars...), google.com
Jak dlouho působí na trhu?
Počet recenzí a průměrné hodnocení napříč portály
Hodnocení prodejce: ⭐⭐⭐⭐⭐

Rodinná vhodnost

Místo pro dětskou sedačku vzadu ✅/❌
ISO FIX ✅/❌
Velikost kufru v litrech — vejde se kočárek? ✅/❌
NCAP hodnocení bezpečnosti
Celkové hodnocení pro rodinu: ⭐⭐⭐⭐⭐

Kontrolní seznam před koupí

Co zkontrolovat při prohlídce (specificky pro tento model a motor)
Doporučit nezávislou inspekci? (AutoKelly, ÖAMTC, certifikovaný servis)
Typická místa koroze pro tento model
Ověřit VIN přes cebia.cz

Červené vlajky

Nesrovnalosti v inzerátu (cena, km, rok)
Co působí podezřele?

Celkové hodnocení

Verdikt: ✅ Koupit / ⚠️ Zvážit / ❌ Vyhnout se
Odůvodnění ve 3–5 větách


Výstup Úkolu B — soubor vysledky.md
Po analýze všech aut vytvoř přehlednou tabulku:
ModelRokMotorKmCenaPortálServis. historieSpolehlivostProdejceRodinaVerdikt

Závěrečné pořadí: které 1–2 auta jsou nejlepší volbou a proč
Doporučení: na co si dát pozor při prohlídce vítěze

