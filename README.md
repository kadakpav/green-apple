# Escarpment Market

Front-end prototype of a same-day grocery delivery site for Hamilton, Ontario.

## Features
- Product catalogue (32 items, 7 categories) with search and category filters
- Hamilton postal-code check (L8, L9, L0R)
- Same-day delivery: live countdown to the 4:00 pm cutoff, 2-hour windows 10 am – 10 pm, today plus 2 days
- Cart drawer with quantities, $75 free-delivery threshold, $25 minimum order, $4.99 delivery fee, 13% HST
- Checkout: address, delivery window, payment by card, PayPal, Apple Pay or Samsung Pay
- Card form formatting and validation (Luhn check, expiry, CVC)
- Light and dark themes, responsive down to phone width

## Run it
No build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Important: payments are mocked
No payment is processed and no card data leaves the browser. Before going live:
- **Cards / Apple Pay / Google Pay:** Stripe or Moneris, using their hosted fields so card data never touches your server (PCI DSS)
- **PayPal:** PayPal JS SDK
- **Samsung Pay:** confirm support with your processor
- **Backend:** inventory, orders, delivery-slot capacity, driver dispatch, receipt emails and SMS
