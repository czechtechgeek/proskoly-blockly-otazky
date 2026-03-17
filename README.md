# Přehled otázek — Blockly želví grafika

Každá otázka je v samostatném adresáři jako `otazka.json`.
Viz [kurikulum](../kurikulum/kurikulum.md) pro celkovou osnovu.

---

## Typy otázek

### ✏️ nakresli/
Student dostane **prázdný workspace** s omezeným toolboxem.
Musí sestavit program od nuly.

**Kdy použít:**
- Testování pochopení nového konceptu
- Student musí sám vybrat správné bloky a hodnoty

**Workspace:** prázdný
**Toolbox:** minimální sada potřebných bloků
**Hodnocení:** délky čar, úhly, max počet bloků

---

### 🔲 doplň/
Workspace má **předpřipravené bloky s mezerou** — chybí 1–2 bloky.
Student musí chybějící blok najít v toolboxu a správně ho zapojit.

**Kdy použít:**
- Nácvik práce s existujícím kódem
- Testování rozpoznání chybějícího kroku
- Vhodné pro první setkání s novým blokem

**Workspace:** sekvence s mezerou (`start_blocks_xml`)
**Toolbox:** chybějící blok + distraktory
**Hodnocení:** stejné jako nakresli

---

### 🔧 oprav/
Workspace má **kompletní, ale chybný kód** — špatná hodnota, špatný počet, špatný typ.
Student musí identifikovat a opravit chybu.

**Kdy použít:**
- Ladění a debugging
- Testování pochopení hodnot (úhel, počet opakování)
- Typická chyba: `opakuj(4)` místo `opakuj(3)` pro trojúhelník

**Workspace:** funkční ale chybný kód (`start_blocks_xml`)
**Toolbox:** bloky k případné náhradě
**Hodnocení:** stejné jako nakresli

---

### 🔀 seřaď/
Workspace má **rozhozené bloky** — správné bloky jsou tam, ale nejsou propojeny.
Student musí sestavit správnou sekvenci.

**Kdy použít:**
- Testování algoritmického myšlení (správné pořadí)
- Obtížnější varianta nakresli — všechny části dány
- Vhodné pro opakování

**Workspace:** rozhozené bloky bez propojení (`start_blocks_xml`)
**Toolbox:** prázdný nebo žádný
**Hodnocení:** stejné jako nakresli

---

## Struktura otazka.json

```
meta.id            — unikátní ID (např. "2-1-001")
meta.typ           — nakresli / doplň / oprav / seřaď
meta.difficulty    — 1–5
meta.stav          — draft / review / ready / published
meta.koncepty      — seznam použitých konceptů

cms.task_text      — zadání česky, klíčové části v [hlp]...[/hlp]
cms.sketch_code    — JS kód pro referenční kresbu na pozadí
cms.toolbox_json   — dostupné bloky (flyoutToolbox nebo categoryToolbox)
cms.start_blocks_xml — předpřipravené bloky (pro doplň/oprav/seřaď)
cms.validace.*     — délky čar, úhly, tolerance, typy bloků, max počet
cms.spravna_odpoved_xml — vzorové řešení jako Blockly XML
```

---

## Konvence pojmenování adresářů

```
<kapitola>-<číslo>-<slug>/
Příklady:
  2-1-001-ctverec-se-smyckou/    ← základní otázka 2.1 #1
  2-1-001b-ctverec-bod-b/        ← mutace základní otázky
  65308-nakresli-ctverec/        ← importovaná z CMS (existující)
```

## Mutace

Každá základní otázka má 4–5 mutací lišící se:
- **Výchozí pozicí** — body A[125,75], B[225,75], C[125,175], D[225,175], E[125,275], F[225,275]
- **Délkou stran** — 45 / 65 / 80 / 100 / 125 / 150 px
- **Směrem otáčení** — right / left
- **Výchozím úhlem** — 0° / 90° / 180° / 270°

---

## Statistiky

| Adresář | Počet otázek |
|---|---|
| nakresli/ | viz `python3 nastroje/generate_index.py` |
| doplň/ | |
| oprav/ | |
| seřaď/ | |
