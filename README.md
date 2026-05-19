# buyCar

AI agent pro výběr spolehlivého ojetého auta pro rodinu.

## Co agent dělá

Prohledá inzertní portály, vyhodnotí nalezená auta a vytvoří strukturované reporty s doporučením ke koupi.

## Požadavky na auto

- **Modely:** Škoda Octavia, Škoda Rapid, VW Golf, VW Passat, VW Touran, VW Sharan
- **Palivo:** benzín, manuál, přední pohon
- **Rok:** od 2015, nájezd do 150 000 km, cena do 250 000 Kč
- **Lokalita:** Praha a okolí

## Použití

Otevři `car_agent.md` v Claude Code a spusť jeden z úkolů:

### Úkol A — analýza konkrétního inzerátu
Zadej URL inzerátu. Agent přečte detaily, ověří motor a VIN.

### Úkol B — aktivní hledání
Agent prohledá Sauto, AAA Auto a Auto ESA, vybere nejlepší nabídky a vytvoří reporty.

## Výstupy

| Soubor | Obsah |
|--------|-------|
| `auto_[model]_[rok]_[km].md` | Detailní report každého auta |
| `vysledky.md` | Přehledná tabulka + finální doporučení |

## Závislosti

- Claude Code s Playwright MCP
