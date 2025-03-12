---
title: Cobra remake
date: "27-Feb-2025"
description: "Acesta este un articol in care sunt prezentate bazele pentru a scrie o aplicatie CLI"
tags: ["go", "ettih", "semHelper"]
---

Ce trebuie sa fac:

0. Sa verific daca imi mai doresc sa adaug si alte date schema
1. Sa definesc o schema pentru baza de date
2. Sa incerc sa incar cateva din bucatile de cod in aceasta
3. Cum se realizeaza o trecere de pe o schema pe alta
4. Mongo ?

### In cazul unei migratii se pare ca ar trebui sa transfer toate date manual

### Chestii de baza in sql:

- Crearea tabloului

```sql

CREATE TABLE Post IF NOT EXISTS (
    id TEXT PRIMARY KEY,
    title TEXT NOT NULL,
    date TEXT,
    description TEXT,
    is_secret BOOLEAN
    has_ai BOOLEAN
);

```


