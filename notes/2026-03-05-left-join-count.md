# SQL Notes : LEFT JOIN and COUNT

## 1. LEFT JOIN

LEFT JOIN keeps all rows from the left table.

Example:

Users LEFT JOIN Orders

Result:
- All users remain in the result
- If there is no matching order, the order columns become NULL

Example result:

| user_id | order_id |
|--------|--------|
| 1 | 10 |
| 2 | 11 |
| 3 | NULL |

User 3 has no order but still appears.

---

## 2. COUNT and NULL

COUNT(column) does NOT count NULL values.

Example:

| order_id |
|---------|
| 10 |
| 11 |
| NULL |

COUNT(order_id) = 2

So when we use:

COUNT(o.order_id)

Users without orders return **0**.

---

## 3. JOIN Condition (ON)

The ON clause defines how two tables are connected.

Example:

Users.user_id = Orders.buyer_id

SQL:

LEFT JOIN Orders o
ON u.user_id = o.buyer_id

This connects each user with their orders.

---

## 4. Filtering Orders in 2019

We only want orders made in 2019.

Condition:

o.order_date >= '2019-01-01'
AND o.order_date < '2020-01-01'

This filters orders within the year 2019.

---

## 5. Key SQL Thinking Pattern

When solving SQL problems:

1. Identify the base table  
2. Decide if LEFT JOIN is needed  
3. Define the join condition  
4. Apply filters  
5. Use aggregation if needed

---

## Key Insight

If a problem says **"for each user"**, the base table must be `Users`.

Use LEFT JOIN so users with no activity still appear in the result.
