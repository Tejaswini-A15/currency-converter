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

# Example usage
from_currency = input("From currency (USD, INR, EUR): ").upper()
to_currency = input("To currency (USD, INR, EUR): ").upper()
try:
    amount = float(input("Amount: "))
    converted = convert_currency(from_currency, to_currency, amount)
    if converted is not None:
        print(f"{amount} {from_currency} = {converted:.2f} {to_currency}")
    else:
        print("Conversion rate not available.")
except ValueError:
    print("Invalid amount.")
