# TallyUp

A simple Streamlit + Supabase Postgres system for a small stationery business.

## What it tracks

- Inventory / stock purchases
- Goods sales / stock out
- Service sales that count fully as profit
- Expenses
- Low stock alerts
- Sales, profit, purchase, expense and service reports
- Excel export

## How to run

1. Install Python 3.10 or newer.
2. Open Command Prompt or Terminal inside this folder.
3. Install requirements:

```bash
pip install -r requirements.txt
```

4. Run the app:

```bash
streamlit run app.py
```

Create a Streamlit secrets file:

```text
.streamlit/secrets.toml
```

Add your Supabase Postgres connection string and login passwords:

```toml
DATABASE_URL = "postgresql://..."
STAFF_PASSWORD = "staff-password"
ADMIN_PASSWORD = "admin-password"
```

Keep this file private because it contains passwords. When deploying, add the same three values as environment variables/secrets on your host.

## First-time setup

1. Go to **Inventory/Stock** when you buy stock.
2. Enter the date, item name, buying price, and quantity.
3. Use **Sales** to record goods sales.
4. Use **Sales > Service** to record services such as printing, typing, or photocopying.
5. Staff can use **Inventory/Stock** and **Sales**.
6. Admins can use **Dashboard**, **Expenses**, **Reports**, and **Export Data** to monitor the business.

## Notes

- Estimated profit uses the buying price saved on the item at the time of sale.
- Service sales count the full sale amount as profit.
- Stock reduces automatically after sales and increases after purchases.
- Inventory, sales, service sales, and expenses can be edited or deleted for 24 hours after they are added.
