# omrekenen

Webpagina met rekenmachines om stroom (A) en vermogen (kW / kVA) in elkaar om te rekenen, bedoeld voor laag- en middenspanning bij netbeheer.

Alles zit in één bestand, [`index.html`](index.html). Er is geen installatie, build of server nodig: open het bestand in een browser.

## Functies

- **A → kW**: rekent stroom om naar werkelijk vermogen (P), schijnbaar vermogen (S) en blindvermogen (Q).
- **kW → A**: rekent vermogen om naar stroom per fase. De invoer kan in kW of in kVA.
- **Systemen**: DC, 1-fase AC en 3-fase AC. Bij 3-fase kun je de spanning als lijnspanning of als fasespanning opgeven.
- **Snelknoppen** voor gangbare waarden:
  - stroom: 25–80 A
  - spanning: 230 V, 400 V, 10 kV en 20 kV
  - cos φ: 1–0,85
- **Stap-voor-stap berekening** met de ingevulde waarden.
- **Uitleg en formules**, uitklapbaar.
- **Tabel met gangbare aansluitingen** (1×25 A t/m 3×80 A) in kVA en kW, uitklapbaar. Klik op een rij om hem in de rekenmachine te laden.
- **Licht en donker thema** via een schuifschakelaar. Standaard volgt de pagina de systeeminstelling; je eigen keuze wordt onthouden.
- Je kunt getallen met een Nederlandse komma invoeren (bijv. `0,95`).

## Formules

| Systeem | Vermogen | Stroom |
|---|---|---|
| DC | P = U · I | I = P / U |
| 1-fase AC | P = U · I · cos φ | I = P / (U · cos φ) |
| 3-fase AC | P = √3 · U<sub>L</sub> · I · cos φ | I = P / (√3 · U<sub>L</sub> · cos φ) |

Verder geldt S = P / cos φ en Q = S · sin φ.

## Gebruik

Live op Vercel: https://omrekenen.van--bokhoven.com (elke push naar `main` wordt automatisch gedeployed).

Lokaal: open `index.html` in je browser.

## Footer en favicon

De footer en favicon zijn gedeeld met de andere subsites en komen van de hoofdwebsite:
[`shared/footer.js`](https://van--bokhoven.com/shared/footer.js) en `peter_avatar.png` op https://van--bokhoven.com.
Wijzigingen daaraan doe je in de repo `website_peter`, niet hier.
