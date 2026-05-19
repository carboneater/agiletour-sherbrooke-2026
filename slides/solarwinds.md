---
layout: section
---

# SolarWinds SUNBURST (2020)

## CI/CD Compromis

---
level: 2
---

# Initial Vector

- ⁉️ Incertain ⁉️
    - Authentifiants Compromis
    - _Password Spraying_
    - _Social Engineering_

---
level: 2
---

# L'attaque


```mermaid
flowchart LR

subgraph TeamCity
    S([☠️]) --> D@{label: Dependencies, shape: db} --> B
    C([code]) --> B[Build] --> T[Tests]
end

T --> P@{label: Public Mirror, shape: cyl}
classDef pwnt color:red,stroke:red;
class S,D,B,T,P pwnt;
```

---
level: 2
---

# M'auront pas \[deux fois\], ces ...

```mermaid
flowchart LR

C([Code]) --> TCA & TCB

subgraph TCA[TeamCity A]
direction LR
    CA@{label: Code, shape: doc} & DA@{label: Dependencies, shape: db} --> BA[Build] --> TA[Tests] -.->|✅| MA@{label: Mirror, shape: cyl}
    CA --> CCA
    BA -->|📦| MA --> CCA{Code Matches}
end

subgraph TCB[TeamCity B]
direction LR
    CB@{label: Code, shape: doc} & DB@{label: Dependencies, shape: db} --> BB[Build] --> TB[Tests] -.->|✅| MB@{label: Mirror, shape: cyl}
    CB --> CCB
    BB -->|📦| MB --> CCB{Code Matches}
end

CCA & CCB -.->|✅|DC

MA & MB -.-> DC{"H(📦A)🟰H(📦B)"} -->P@{label: Public, shape: cyl}
```

---

# Bon, mais pas parfait

```mermaid
flowchart LR

C([Code]) -.-> TCA & TCB

subgraph TCA[TeamCity A]
direction LR
    CA@{label: Code, shape: doc} & DA@{label: Dependencies, shape: db} --> BA[Build] --> TA[Tests] -.->|✅| MA@{label: Mirror, shape: cyl}
    CA --> CCA
    BA -->|📦| MA --> CCA{Code Matches}
end

subgraph TCB[TeamCity B]
direction LR
    CB@{label: Code, shape: doc} & DB@{label: Dependencies, shape: db} --> BB[Build] --> TB[Tests] -.->|✅| MB@{label: Mirror, shape: cyl}
    CB --> CCB
    BB -->|📦| MB --> CCB{Code Matches}
end

US@{label: Upstream<br/>Dependencies, shape: db} --> DA & DB

CCA & CCB -.->|✅|DC

MA & MB -.-> DC{"H(📦A)🟰H(📦B)"} -->P@{label: Public, shape: cyl}
```
