---
level: 3
---

# L'éternel jeu du chat et de la souris...

<center>

```mermaid
flowchart LR
D((Devs)) --> C[Code] --> B[Build] --> P[Prod]
C ==>|🔒|R
R@{label: Package<br/>Index, shape: db} --> B
A((Attacker ☠️)) -->|🦠|C

classDef good color:green,stroke:green;
class D good;
classDef pwnt color:red,stroke:red;
class A,B,C,P,R pwnt;
```
</center>

---
layout: section
---

# Les attaques via Git(Hub)

---
level: 2
---

# Initial Vector: Identifiants Compromis

- Fuite Précédente?
- Phishing?

---
level: 2
---

# Initial Vector: Pull Request Malicieux

<ul>
  <li v-click>Forker le projet</li>
  <li v-click>Créer un payload d'exfiltration de secret</li>
  <li v-click>L'injecter dans une config de pipeline</li>
  <li v-click>Créer un PR `upstream`</li>
  <li v-click>Actions Actionnent</li>
  <li v-click>Secrets!</li>
  <li v-click>Supprimer le PR et la branche
    <ul><li>Points bonis si les actions le font</li></ul>
  </li>
</ul>

---
level: 2
---

# Root Cause pt1: Fork Pull Request Approvals

GitHub > Project > Settings > Actions > General

![Fork PR Approvals](/public/fork.png)

---
layout: two-cols-header
level: 2
---

# Root Cause pt2: `on: pull_request_target`

::left::

Le pipeline teste le code de la branche de l'attaquant

::right::

Le pipeline s'exécute comme si le code avait déjà été mergé dans la branche (ex: main)

---
layout: two-cols-header
level: 2
---

# Déjà vu?

::left::

<center>

## PostHog

### (Sha1-Hulud 2.0)

</center>

::right::

<center>

## Trivy

</center>

::bottom::

<center>

Et ce ne sont pas les seuls!

</center>
