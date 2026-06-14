# TallyUp

A simple Streamlit + Supabase Postgres system for stationery and cooking gas businesses owned by the same person.

## What it tracks

- Inventory / stock purchases
- Goods sales / stock out
- Service sales that count fully as profit
- Cooking gas and gas accessory stock
- Cooking gas and gas accessory sales
- Staff clock-in and clock-out
- Credit sales and customer debt tracking
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
STAFF_USERNAME = "staff"
STAFF_PASSWORD = "staff-password"
GAS_STAFF_USERNAME = "gas"
GAS_STAFF_PASSWORD = "gas-password"
ADMIN_USERNAME = "admin"
ADMIN_PASSWORD = "admin-password"
```

Keep this file private because it contains passwords. When deploying, add the same three values as environment variables/secrets on your host.

## First-time setup

1. Go to **Inventory/Stock** when you buy stock.
2. Enter the date, item name, buying price, and quantity.
3. Use **Sales** to record goods sales.
4. Use **Sales > Service** to record services such as printing, typing, or photocopying.
5. Use **Gas Inventory/Stock** and **Gas Sales** for cooking gas and accessories.
6. Stationery staff can use **Inventory/Stock** and **Sales**.
7. Gas staff can use **Gas Inventory/Stock** and **Gas Sales**.
8. Admins can use the full dashboard, expenses, reports, and export tools to monitor both businesses.
9. Staff must clock in with their employee code and name before using their allowed work pages.
10. Use **Credit** as the payment method when a customer buys on debt.
11. Admins can use **Debtors / Daftari** to view balances and record repayments.

## Notes

- Estimated profit uses the buying price saved on the item at the time of sale.
- Service sales count the full sale amount as profit.
- Stock reduces automatically after sales and increases after purchases.
- Inventory, sales, service sales, and expenses can be edited or deleted for 24 hours after they are added.
- Gas records follow the same 24-hour edit/delete rule.
- The shared staff login controls shop access, while clock-in records the individual employee working the shift.
- Customer debt is tracked through a ledger, so every credit sale and repayment has a paper trail.
