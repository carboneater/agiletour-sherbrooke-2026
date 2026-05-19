---
hideInToc: true
layout: section
---

# Dance Like Nobody's Watching

# Encrypt Like Everyobdy Is

- Dr Werner Vogels, Amazon CTO

---
layout: section
---

# Code Like Nobody's Watching

# Authenticate Like Everybody Is

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

![Carney's Signature](/100-front.jpg)

Source: [Bank of Canada](https://www.bankofcanada.ca/banknotes/bank-note-series/frontiers/100-polymer-note/)

<!--
Authenticité: The Author is who they claim to be
Intégrité: The document wasn't altered
Non-Répudiation: There is exactly one author and we can positively identify them. If they want to claim there was fraud, they have the duty to prove how someone could compromise the algorithms to be considered as them.
-->


---

# Validation

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

# ToC ⚖️ ToU

- La clé privée est encryptée avec un mot/phrase de passe
- GPG-Agent décrypte la clé pour une période de 10 minutes (par défaut)

---
layout: section
level: 3
---

# [Sequoia-Git](https://gitlab.com/sequoia-pgp/sequoia-git)

`sudo apt install sequoia-git`  
`sq-git init`
