---
layout: section
---

# Signatures Cryptographiques

---
layout: two-cols-header
level: 2
---

# Signatures Cryptographiques

::left::

## Triples Garanties

- Intégrité
- Authenticité
- Non-Répudiation

::right::

<img alt="100CAD Bill" src="/public/100-front.jpg" style="object-fit: contain;min-height:50vh;" />

<div class="abs-bl">

Image Source: [Bank of Canada](https://www.bankofcanada.ca/banknotes/bank-note-series/frontiers/100-polymer-note/)

</div>

<!--
Authenticité: The Author is who they claim to be
Intégrité: The document wasn't altered
Non-Répudiation: There is exactly one author and we can positively identify them. If they want to claim there was fraud, they have the duty to prove how someone could compromise the algorithms to be considered as them.
-->


---
level: 2
---

# Git Commit Signing: Validation

```mermaid
flowchart LR

subgraph Dev
    C@{label: Code, shape: doc}
    subgraph Paire
        PrK[🔐 Privée]
        PuK[🔏 Publique]
    end
    PrK & C --> S[Signature]
    S & C --> DG@{label: Commit, shape: docs}
end

subgraph Origin
    KS[KeyStore]
    OG@{label: Commit, shape: docs}

    KS & OG --> VS{Validate<br/>Signature}

    VS -->|❌ Reject| OG
    VS -->|✅| CI
end

Dev ~~~ Origin
PuK -->|Publish| KS
DG -->|Push| OG
```

---
level: 2
---

# ToC ⚖️ ToU

- La clé privée est encryptée avec un mot/phrase de passe
- GPG-Agent décrypte la clé pour une période (par défaut: 10 minutes)

---
layout: section
level: 3
---

# [Sequoia-Git](https://gitlab.com/sequoia-pgp/sequoia-git)

`sudo apt install sequoia-git`  
`sq-git init`

➕ Le code contient les clés publiques

➖ Difficile à gérer en large déploiement

---
level: 2
---

> Tu m'a convaincu! À partir de maintenant, je signe tout!

```mermaid
flowchart LR
S@{label: Sigstore, shape: docs}
C((Code)) --> B[Build] --> D[Container] -->H[Host] --> Prod
N@{label: packages, shape: db} --> B
S -.->|✅| C & N & D

DK@{label: Distro Keys, shape: docs} -.->|✅| DP@{label: Distro Packages, shape: db} --> H & D

classDef signed stroke:#4C4;
class S,C,B,N,D signed;
classDef distro stroke:#44C;
class DK,DP,H distro;
```

<v-click><p>Ils vécurent heureux et n'eurent pas beaucoup d'incidents...</p></v-click>

<v-click><p>N'est-ce pas?</p></v-click>

---
level: 2
---

# On est juste à la moitié du chemin!

Les mécanismes de validation à la consommation des packages sont encore manquants!

![SSL EV SCAM](/public/ssl-2019.png)

(Sauf pour les packages des OS)
