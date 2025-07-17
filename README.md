# currency-converter
a python code for currency converter
# Static exchange rates (example only — rates may be outdated!)
exchange_rates = {
    "USD": {"INR": 83.0, "EUR": 0.91},
    "INR": {"USD": 0.012, "EUR": 0.011},
    "EUR": {"USD": 1.10, "INR": 91.0},
}

def convert_currency(from_currency, to_currency, amount):
    try:
        rate = exchange_rates[from_currency][to_currency]
        return amount * rate
    except KeyError:
        return None


