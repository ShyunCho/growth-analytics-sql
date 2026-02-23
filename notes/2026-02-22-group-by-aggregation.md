# 2026-02-22 – GROUP BY & HAVING

## 🧠 What I Learned

### GROUP BY
Groups rows with the same value.

Example:
a
a
b

Becomes:
a → 2
b → 1

### COUNT(*)
Counts how many rows exist in each group.

### HAVING
Filters after grouping.

WHERE → filters rows
HAVING → filters grouped results

---

## 🧩 Problem Practiced

LeetCode 182 – Duplicate Emails

SELECT email AS Email
FROM Person
GROUP BY email
HAVING COUNT(*) > 1;

---

## 🔍 Key Insight

- GROUP BY creates groups.
- COUNT calculates group size.
- HAVING filters groups.
- JOIN direction matters (LEFT JOIN keeps left table).
