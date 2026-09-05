# pizzahut-sql-sales-analysis

Analysis of 21,350+ orders and $817K+ in revenue for a fictional PizzaHut outlet, using pure SQL to answer real business questions about sales, menu performance, and customer ordering patterns — and to turn those answers into concrete recommendations for growing revenue.

**[📊 View the full presentation](./PizzaHut_Sales_Analysis.pptx)** &nbsp;

---

##  Project Overview:

Pizza sales data is only useful if it answers questions a business actually cares about: *What's selling? When are we busiest? What should we push harder?* 
This project uses MySQL to explore a relational pizza-sales dataset end to end — from basic counts to window functions — and translates the results into insights a sales or ops team could act on immediately.

**Tools:** MySQL / MySQL Workbench
**Techniques:** Joins, aggregations, subqueries, `GROUP BY` / `ORDER BY` / `LIMIT`, window functions (`SUM() OVER`)

---

##  Dataset:

Four related tables:

| Table | Description |
|---|---|
| `orders1` | Order ID, order date, order time — one row per order |
| `order_detail` | Line items linking orders to pizzas and quantities |
| `pizzas` | Pizza ID, size, price, and its pizza type |
| `pizza_types` | Pizza name, category (Classic / Chicken / Supreme / Veggie), ingredients |

---

## Business Questions Answered:

| # | Question |
|---|---|
| 1 | What is the total number of orders placed? |
| 2 | What is the total revenue generated from pizza sales? |
| 3 | Which is the highest-priced pizza on the menu? |
| 4 | What is the most commonly ordered pizza size? |
| 5 | Which are the top 5 most ordered pizza types by quantity? |
| 6 | What is the total quantity ordered for each pizza category? |
| 7 | How are orders distributed across different hours of the day? |
| 8 | How are pizzas distributed across categories on the menu? |
| 9 | What is the average number of pizzas ordered per day? |
| 10 | Which are the top 3 pizza types by revenue? |
| 11 | Which pizza types generate the top revenue within their category? |
| 12 | What percentage does each category contribute to total revenue? |
| 13 | How does cumulative revenue grow over time? |

Full query text, screenshots, and results for each are in [`queries.sql`](./queries.sql) and the [presentation](./PizzaHut_Sales_Analysis.pptx).

---

##  Key Insights:

- **21,350 orders → $817,860.05 in revenue** — an average order value of ~$38.
- **Large is the dominant size**, with 18,526 orders — far ahead of any other size.
- **Classic wins on volume, Chicken wins on value**: Classic leads unit sales (14,888), but the Thai, Barbecue, and California Chicken pizzas are the top 3 revenue earners overall.
- **Clear daily rush windows**: orders peak at 12–1 PM and again at 6 PM, then drop sharply after 9 PM.
- **Revenue is well balanced across categories** (23.7%–26.9% each) — no single category the business is over-reliant on.
- **Predictable daily demand**: ~138 pizzas sold per day on average, with steady, consistent cumulative revenue growth over time.

##  Recommendations:

1. **Upsell around Large pizzas** — bundle Large-size combos; prompt Medium buyers to size up.
2. **Feature chicken specialties** — Thai, Barbecue & California Chicken earn the most revenue per pizza sold.
3. **Target the lunch & dinner rush** — time-boxed offers and staffing around 12–1 PM and 6 PM.
4. **Revive slow hours** — discounts in the 9–11 AM and post-9 PM windows to smooth demand.
5. **Plan inventory around ~138 pizzas/day** as a forecasting baseline to cut waste.
6. **Refresh the Veggie line-up** — it trails other categories slightly; test new recipes or limited-time offers.

---

##  How to Reproduce:

1. Import the dataset into MySQL (`orders1`, `order_detail`, `pizzas`, `pizza_types`).
2. Run the queries in [`queries.sql`](./queries.sql) in MySQL Workbench (or any MySQL client).
3. Cross-reference results with the [presentation](./PizzaHut_Sales_Analysis.pptx) for narrative and takeaways.

---

##  Files in This Repo:

```
├── queries.sql                      # All 13 SQL queries, commented
├── PizzaHut_Sales_Analysis.pptx     # Full slide deck with insights & recommendations
└── README.md
```
