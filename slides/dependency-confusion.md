---
layout: section
level: 1
---

# Dependency Confusion

---
level: 2
---

# Dependency Confusion

```mermaid
flowchart LR


U@{label: Upstream, shape: db}
subgraph Interne
    R@{label: Repo<br/>@Company, shape: db}
    M@{label: Mirroir, shape: db}
end
U-.->M

P@{label: "@Company/package@1.0.1", shape: docs} --->R

Interne --> O@{label: "@Company/package@1.0.1", shape: docs}
R -.->O
SI@{label: "@slidev/cli@52", shape: docs} --> U
Interne --> SO@{label: "@slidev/cli@52", shape: docs}
M -.-> SO
```

---
level: 2
---

# Dependency Confusion

```mermaid
flowchart LR


U@{label: Upstream, shape: db}
subgraph Interne
    R@{label: Repo<br/>@Company, shape: db}
    M@{label: Mirroir, shape: db}
end
U-.->|🦠|M

P@{label: "@Company/package@1.0.1", shape: docs} --->R
Ma@{label: "@Company/package@1.0.2", shape: docs} -->|🦠| U

M -.->|🦠| O@{label: "@Company/package@1.0.2", shape: docs}

classDef pwnt color:red,stroke:red;
class M,Ma,O,U pwnt;
```

---
layout: two-cols-header
level: 2
---

# Mitigations

::left::

-  Réserver le `@scope` publiquement
    + Restreint qui peut publier
    - Fuite de l'information interne
    - Pas une garantie dans le temps
        - Fiasco NPM/Kix/Left-Pad

::right::

<v-click>

- Déconnecter les packages privés des sources publiques

```diff
packages:
  '@my-company/*':
    access: $all
    publish: $authenticated
    unpublish: $authenticated
-   proxy: npmjs
  '@*/*':
    access: $all
    proxy: npmjs
  '**':
    access: $all
    proxy: npmjs
```

Référence:  [Verdaccio Docs](https://www.verdaccio.org/docs/best/#remove-proxy-to-increase-security-at-private-packages)

</v-click>
