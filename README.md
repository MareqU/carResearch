# carResearch — AI agent pro výběr ojetého auta

AI agent postavený na Claude Code a Playwright MCP, který prohledává české inzertní portály, vyhodnocuje nalezená auta podle předem definovaných kritérií a generuje strukturované reporty s verdiktem **koupit / zvážit / vyhnout se**.

---

## Jak to funguje

Agent má přístup k prohlížeči přes Playwright MCP — otevírá reálné weby, čte inzeráty, vyhledává informace o spolehlivosti motorů a zapisuje výsledky do Markdown souborů.

Pracuje ve dvou režimech:

- **Úkol A** — zadáš URL konkrétního inzerátu, agent ho analyzuje a vytvoří report
- **Úkol B** — agent sám prohledá všechny portály, vybere nejzajímavější nabídky a vytvoří přehled

---

## Požadavky na auto

| Parametr | Hodnota |
|----------|---------|
| Značky | Škoda Octavia, Škoda Rapid, VW Golf, VW Passat, VW Touran, VW Sharan |
| Palivo | Benzín |
| Převodovka | Manuál |
| Pohon | Přední |
| Rok výroby | Od 2015 |
| Nájezd | Max 150 000 km |
| Cena | Max 250 000 Kč |
| Lokalita | Praha a okolí (do 1 hodiny jízdy) |
| Priority | 1. Spolehlivost  2. Servisní historie |

---

## Použití

### Předpoklady

- [Claude Code](https://claude.ai/code) s aktivním Playwright MCP serverem

### Spuštění

1. Otevři tento repozitář v Claude Code
2. Otevři soubor `car_agent.md` — ten slouží jako instrukce pro agenta
3. Zvol úkol:

**Úkol A — analýza konkrétního inzerátu:**
```
Proveď Úkol A pro tento inzerát: [URL inzerátu]
```

**Úkol B — aktivní hledání:**
```
Proveď Úkol B — prohledej Sauto, AAA Auto a Auto ESA a vytvoř přehled.
```

---

## Prohledávané portály

| Portál | Poznámka |
|--------|----------|
| [Sauto.cz](https://www.sauto.cz) | Největší inzerce v ČR — soukromníci i bazary |
| [AAA Auto](https://www.aaaauto.cz) | Největší síť bazarů v ČR |
| [Auto ESA](https://www.autoesa.cz) | ⚠️ Filtr ceny funguje podle **akční ceny na úvěr** — hotovostní cena je o 40–100 000 Kč vyšší. Vždy ověřit „Cena v hotovosti" na detailu inzerátu. |

---

## Hodnocení motorů

| Motor | Hodnocení | Poznámka |
|-------|-----------|----------|
| 1.6 MPI | ✅ Velmi spolehlivý | Starší, bez turba, jednoduchý na servis — slabší výkon (81 kW) |
| 1.5 TSI (2019+) | ✅ Výborná volba | Nástupce 1.4 TSI, 110 kW, EA211 Evo — vyladěná verze |
| 1.2 TSI (Rapid 2012+) | ✅ Dobrá volba | Opravené řetězové rozvody |
| 1.0 TSI | ✅ Spolehlivý | Moderní, EURO6, 85 kW |
| 1.2 TSI (starší Octavia/Golf) | ⚠️ Pozor | Řetězové rozvody, spotřeba oleje |
| 1.5 TSI (2017–2018) | ⚠️ Ověřit | Raná verze — drobné problémy s ACT |
| 1.4 TSI | ⚠️ Pozor | Výkonný, nákladnější na servis |
| 1.4 TSI + DSG (do 2015) | ❌ Vyhnout se | Suché spojky DSG — nevhodné pro město |

---

## Výstupy

Agent ukládá výsledky do složky pojmenované podle aktuálního data (např. `25052026/`).

| Soubor | Obsah |
|--------|-------|
| `auto_[Model]_[Rok]_[km].md` | Detailní report jednoho auta |
| `vysledky.md` | Srovnávací tabulka všech aut + finální doporučení |

### Struktura reportu každého auta

- **Základní info** — model, rok, motor, nájezd, cena, odkaz na inzerát
- **Servisní historie** — dostupnost záznamů, pravidelnost, autorizovaný vs. nezávislý servis
- **Spolehlivost modelu** — typické závady, hodnocení konkrétního motoru
- **Rodinná vhodnost** — ISOFIX, velikost kufru, NCAP bezpečnost, místo pro dětskou sedačku
- **Kontrolní seznam** — co ověřit při prohlídce, VIN přes cebia.cz
- **Červené vlajky** — podezřelé nesrovnalosti v inzerátu
- **Verdikt** — ✅ Koupit / ⚠️ Zvážit / ❌ Vyhnout se

---

## Struktura projektu

```
carResearch/
├── car_agent.md        # Instrukce pro agenta (prompt)
├── README.md
├── 17052026/           # Výsledky ze dne 17.5.2026
│   ├── auto_Octavia_2018_109014km.md
│   └── vysledky.md
├── 25052026/           # Výsledky ze dne 25.5.2026
│   └── ...
└── .claude/
    └── settings.local.json   # Povolené nástroje pro Claude Code
```

---

## Závislosti

- [Claude Code](https://claude.ai/code)
- Playwright MCP server (nakonfigurován v Claude Code)
