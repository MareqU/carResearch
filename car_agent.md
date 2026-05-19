# Agent pro výběr spolehlivého auta

## Hlavní cíl
Najít co nejspolehlivější auto do 250 000 Kč.
Auto musí být praktické pro rodinu s manželkou a 1 dítětem.

## Požadavky

| Parametr | Hodnota |
|----------|---------|
| Lokalita | Praha a okolí (preferováno) |
| Rozpočet | max 250 000 Kč |
| Značky | Škoda Octavia, Škoda Rapid, VW Golf, VW Passat, VW Touran, VW Sharan |
| Palivo | benzín |
| Převodovka | manuál |
| Pohon | přední |
| Nájezd | max 150 000 km |
| Rok výroby | od 2015 |
| Posádka | řidič + manželka + 1 dítě |

**Priority:**
1. Spolehlivost auta
2. Doložená servisní historie (výhoda, ne podmínka)

## Nástroje
- Vždy používej **Playwright MCP** pro veškeré procházení webů
- Nepoužívej Bash ani jiné nástroje pro přístup na internet

## Zásady pro práci s prohlížečem
- Vždy počkej na plné načtení stránky před čtením obsahu
- Pokud se zobrazí cookie banner nebo popup, zavři ho před dalšími akcemi
- Pokud je stránka blokovaná nebo pomalá, zkus ji znovu načíst
- Ukládej si URL každého navštíveného inzerátu pro závěrečný přehled

---

## Úkol A — Analýza konkrétního inzerátu

1. Otevři zadanou URL pomocí Playwright MCP
2. Přečti všechny detaily přímo ze stránky inzerátu
3. Otevři novou záložku a vyhledej spolehlivost konkrétního motoru na auto.cz nebo autorevue.cz
4. Prověř VIN na cebia.cz pokud je v inzerátu uveden

> Zvláštní pozornost věnuj: 1.2 TSI (rozvody, spotřeba oleje), 1.4 TSI (nákladný servis)

---

## Úkol B — Aktivní hledání napříč portály

### Portály

| Portál | URL | Poznámka |
|--------|-----|----------|
| Sauto | https://www.sauto.cz | Největší inzerce, soukromníci i bazary |
| AAA Auto | https://www.aaaauto.cz | Největší síť bazarů v ČR |
| Auto ESA | https://www.autoesa.cz | Síť bazarů |

### Filtry na každém portálu

| Parametr | Hodnota |
|----------|---------|
| Značka / Model | Škoda (Octavia, Rapid) / VW (Golf, Passat, Touran, Sharan) |
| Palivo | benzín |
| Převodovka | manuál |
| Pohon | přední |
| Cena | do 250 000 Kč |
| Nájezd | do 150 000 km |
| Rok výroby | od 2015 |
| Lokalita | Praha a okolí |

### Postup na každém portálu

1. Nastav filtry dle tabulky výše
2. Projdi výsledky a vyber maximálně 3 nejzajímavější inzeráty — přednostně vyber inzeráty kde je zmíněna servisní historie nebo servisní knížka
3. Z každého inzerátu přečti: model, rok, motor, km, cena, kontakt, popis, zmínka o servisní historii
4. Zaznamenej z jakého portálu inzerát pochází

---

## Poznámky k motorům (benzín)

| Motor | Hodnocení | Poznámka |
|-------|-----------|----------|
| 1.6 MPI | ✅ Velmi spolehlivý | Starší, jednoduchý, bez turba — slabší výkon |
| 1.2 TSI (Rapid od 2012+) | ✅ Dobrá volba | Opravené řetězové rozvody |
| 1.2 TSI (starší Octavia/Golf) | ⚠️ Pozor | Řetězové rozvody, spotřeba oleje |
| 1.4 TSI | ⚠️ Pozor | Výkonný, nákladnější na servis — pozor na starší kusy |
| 1.4 TSI + DSG do 2015 | ❌ Vyhnout se | Suché spojky DSG — nevhodné pro město a kolony |

---

## Rodinné požadavky — ověř u každého auta

- Dostatek místa na zadních sedadlech pro dětskou sedačku
- Velikost a přístupnost kufru (vejde se kočárek?)
- Hodnocení NCAP bezpečnosti (min. 4 hvězdy)
- ISO FIX pro dětskou sedačku (výhoda)
- Dobrý výhled z auta při parkování

---

## Struktura výstupního souboru pro každé auto

Vytvoř soubor `auto_[model]_[rok]_[km].md`:

### Základní info
- Model, rok výroby, motor (ccm, kW), převodovka, nájezd, cena
- Odkaz na inzerát

### Servisní historie
- Je servisní historie zmíněna v inzerátu? ✅/❌
- Servisováno v autorizovaném nebo nezávislém servisu?
- Jsou doloženy faktury nebo servisní knížka?
- Jsou záznamy v servisní knížce pravidelné? (velké výpadky = ⚠️)
- **Hodnocení servisní historie: ⭐⭐⭐⭐⭐**

### Spolehlivost modelu
- Zdroje: auto.cz, autorevue.cz, TÜV Report
- Typické závady tohoto modelu a generace
- Jak na tom je tento konkrétní motor?
- **Hodnocení spolehlivosti modelu: ⭐⭐⭐⭐⭐**

### Rodinná vhodnost
- Místo pro dětskou sedačku vzadu ✅/❌
- ISO FIX ✅/❌
- Velikost kufru v litrech — vejde se kočárek? ✅/❌
- NCAP hodnocení bezpečnosti
- **Celkové hodnocení pro rodinu: ⭐⭐⭐⭐⭐**

### Kontrolní seznam před koupí
- Co zkontrolovat při prohlídce (specificky pro tento model a motor)
- Doporučit nezávislou inspekci? (AutoKelly, ÖAMTC, certifikovaný servis)
- Typická místa koroze pro tento model
- Ověřit VIN přes cebia.cz

### Červené vlajky
- Nesrovnalosti v inzerátu (cena, km, rok)
- Co působí podezřele?

### Celkové hodnocení
- **Verdikt: ✅ Koupit / ⚠️ Zvážit / ❌ Vyhnout se**
- Odůvodnění ve 3–5 větách

---

## Výstup Úkolu B — soubor vysledky.md

Po analýze všech aut vytvoř přehlednou tabulku:

| Model | Rok | Motor | Km | Cena | Portál | Servis. historie | Spolehlivost | Rodina | Verdikt |
|-------|-----|-------|----|------|--------|-----------------|--------------|--------|---------|

**Závěrečné pořadí:** která 1–2 auta jsou nejlepší volbou a proč

**Doporučení:** na co si dát pozor při prohlídce vítěze
