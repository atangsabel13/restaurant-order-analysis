# 🍽️ Restaurant Orders — SQL Data Analysis

A MySQL analysis of a restaurant's order history — exploring menu composition, pricing, and order-level sales patterns across three months of point-of-sale data.

![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Overview

This project builds a small relational database from raw restaurant order data and uses SQL to answer practical business questions a restaurant manager might ask: which menu items sell, what a typical order looks like, and which orders are the most valuable.

**Objectives:**
1. Build a two-table relational database (`menu_items`, `order_details`) from raw order data
2. Profile the menu — pricing and composition by category
3. Analyze order-level patterns — items per order, order volume over time, and highest-value orders

---

## 🗂️ Dataset

| | |
|---|---|
| Order line items | 12,097 rows (`order_details`) |
| Distinct orders | 5,343 |
| Menu items | 32 dishes (`menu_items`) |
| Categories | American, Asian, Italian, Mexican |
| Date range | Jan 1 – Mar 31, 2023 |
| Price range | $5.00 – $19.95 |

### Schema

**`order_details`**
| Column | Type | Description |
|---|---|---|
| `order_details_id` | SMALLINT (PK) | Unique line-item ID |
| `order_id` | SMALLINT | Groups line items into a single order |
| `order_date` | DATE | Date the order was placed |
| `order_time` | TIME | Time the order was placed |
| `item_id` | SMALLINT | References `menu_items.menu_item_id` |

**`menu_items`**
| Column | Type | Description |
|---|---|---|
| `menu_item_id` | SMALLINT (PK) | Unique item ID |
| `item_name` | VARCHAR(45) | Dish name |
| `category` | VARCHAR(45) | American, Asian, Italian, or Mexican |
| `price` | DECIMAL(5,2) | Menu price |

---

## 🛠️ Tools & Skills Demonstrated

- MySQL database creation (DDL) and data seeding (DML)
- Aggregate functions — `COUNT`, `MIN`, `MAX`, `AVG`, `SUM`
- `INNER JOIN` / `LEFT JOIN` to combine `menu_items` and `order_details`
- `GROUP BY` / `HAVING` for category- and order-level aggregation
- Filtering and ranking with `WHERE`, `BETWEEN`, `ORDER BY`, `LIMIT`

---

## 🔍 Business Questions Answered

| Question | Answer |
|---|---|
| How many distinct items are on the menu? | 32 |
| Most / least expensive item? | $19.95 / $5.00 |
| Items per category | American 6 · Asian 8 · Italian 9 · Mexican 9 |
| Average price per category | Italian $16.75 · Asian $13.48 · Mexican $11.80 · American $10.07 |
| Number of Italian dishes, and their price range | 9 dishes, $14.50 – $19.95 |
| Order volume between Jan 1 – Mar 31, 2023 | 5,343 orders, 12,097 items ordered |
| Orders with more than 12 items | 20 orders (max order size: 14 items) |
| Highest-value single orders | Top order totals $192.15, $191.05, $190.10, $189.70, $185.10 |

Each of these is a standalone, commented query in the script — see `restaurant.sql` for the full logic behind each answer, plus a joined `menu_items` ⋈ `order_details` view and an order-count-per-item breakdown by category.

---

## 🚀 How to Use

1. Open `restaurant.sql` in MySQL Workbench (or any MySQL client) and run it — it drops/recreates the `restaurant_db` schema and loads both tables.
2. Run the analysis queries at the bottom of the script individually, or adapt them to ask your own questions of the data.

---

## 📬 Contact

**Abel Atangs**
📧 abelatangs7@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/abel-atangs03) · [GitHub](https://github.com/atangsabel13)
