---
layout: two-cols-header
level: 2
---

# Pourquoi utiliser la chaîne d'approvisionnement?

::left::

- Native à chaque écosystème
- Simple!
- Permet de ne pas réinventer la roue!

::right::

```mermaid
xychart

title "Nombres approximatif de packages dans NPM selon l'année"
x-axis [2014,2017,2019,2022,2023,2026]
y-axis "Milliers de Packages"
line [115,  600,  1000,  2100,  2500, 3100]
```

Source: Gemini. Prenez ça avec un peu de 🧂

---
layout: two-cols-header
level: 2
---

# Mais, j'ai entendu qu'on peut m'attaquer par là?!?

::left::

## Oui...

- SolarWinds (2020)
- CodeCov (2021)
- Comm100 (2022)
- MOVEit (2023)
- Crowdstrike (2024)
- Shai-Hulud (2025)
- PostHog/LiteLLM (2026)
- Mini Shai-Hulud/Miasma (2026)


(Liste Très  Non Exhaustive!)

::right::

<v-click>

## Stagner est pire...

```mermaid
xychart

title "CVEs publiées / année"
x-axis [99,00,01,02,03,04,05,06,07,08,09,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25]
y-axis "CVEs"
line [321,  1438,  1323,  1691,  1223,1612,  6708,  6885,  7322,  5673,   5732,  4639,  4150,  5288,  5142,   7948,  6494,  6457, 14645, 16512,  17308, 18375, 20161, 25059, 28961,  40077, 48244]
```

</v-click>

---
level: 2
---

# Pause Lexicale

| Acronyme | Définition                          | Échelle    | ex: Log4J                  |
|----------|-------------------------------------|------------|----------------------------|
| CVE      | Common Vulnerabilities & Exposures  |            | CVE-2021-44228 (Log4Shell) |
| CVSS     | Common Vulnerability Scoring System | 0 - 10     | 10.0                       |
| EPSS     | Exploit Prediction Scoring System   | 0 - 100%   | 100 % (À Posteriori)       |
| KEV      | Known Exploited Vulnerability       |            | Oui. 0-Day                 |
