---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: warehouse.jpg
# some information about your slides (markdown enabled)
title: Longue vie à la chaîne d'approvisionnement!
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
hideInToc: true
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: none
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# Longue vie à la chaîne d'approvisionnement!

<div class="abs-b">Photo by <a href="https://unsplash.com/@sulyok_imaging?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Adrian Sulyok</a> on <a href="https://unsplash.com/photos/yellow-and-white-plastic-box-lot-sczNLg6rrhQ?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a> / <a href="https://www.sulyokimaging.ro">https://www.sulyokimaging.ro</a>
</div>

---
hideInToc: true
image: gab.jpg
layout: image-left
---

# $ `whoami`

- DevSecOps
  - D'un déploiement hebdo
  - à ~400 deploys/jour / 15 devs
- 3 ans en sécurité temps plein
  - 2 ans automatisation des réponses aux menaces cyber
  - 1 an cryptographie
- Dev (Principalement)
  - TS
  - Python

---
image: sleep.jpg
layout: image-right
level: 2
---

# <3 Supply Chain

- `unattended-upgrades` @ 04:00 HE
- `renovate-bot` (oss) @ 00:00 - 08:00 HE
- `renovate-bot` (interne) @ 08:00 - 00:00 HE


<div class="abs-br">
  Photo by <a href="https://unsplash.com/@davidclode?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">David Clode</a> on <a href="https://unsplash.com/photos/koala-bear-sleeping-on-tree-Yg_sNKOiXvY?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
      
</div>

---
hideInToc: true
---

# ToC

<Toc minDepth="1" maxDepth="1" />

---
layout: image-right
level: 2
image: beer.jpg
---

# Avertissements

- Pardonnez mon _franglais_
- Mes opinions sont les miens
  - Et n'engagent que moi
  - Vive Extreme Programming!
- N'hésitez pas à poser des questions
  - Si on manque de temps, on continuera à la bière!

<div class="abs-br">Photo by <a href="https://unsplash.com/@barncreative?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Fábio  Alves</a> on <a href="https://unsplash.com/photos/beer-dispensers-_fLgxjACz5k?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></div>

---
src: slides/static.md
---

---
src: slides/pourquoi.md
---

---
hideInToc: true
layout: section
---

# Supply Chain Attacks

---
src: slides/solarwinds.md
---

---
src: slides/dependency-confusion.md
---

---
src: slides/quix-.md
---

---
src: slides/git.md
---

---
src: slides/npm.md
---

---
layout: section
level: 0
---

# Défences

---
hideInToc: true
layout: section
---

# Moindre Privilège

## ✅ Je ne peux pas attaquer un _repo_ sans accès en écriture (*)

<div class="abs-b">(*) Nonobstant une élévation de privilèges au cours d'une attaque</div>

---
src: slides/verifications.md
---

---
src: slides/authentication.md
---

---
src: slides/insider.md
---

---
src: slides/conclusion.md
---

---
layout: end
class: text-center
---

# Questions?

# Commentaires?

# Insultes?

<PoweredBySlidev mt-10 />

Slides: https://github.com/carboneater/agiletour-sherbrooke-2026
