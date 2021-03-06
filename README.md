# Binary.com API for Python

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/mdn522)


## About API

```python
# High Level API, This API is based on "binaryapi.api" for easy usage
from binaryapi.stable_api import Binary

# Low Level API
from binaryapi.api import BinaryAPI
```

## Installing and Updating
For Python 3
```bash
pip3 install -U git+git://github.com/mdn522/binaryapi.git
```

---
## Getting Started
```python
from binaryapi.stable_api import Binary

binary_token = "YOUR-API-TOKEN-GOES-HERE"

binary = Binary(token=binary_token)

symbol = "frxEURUSD"
print("Buy a CALL contract")
print(binary.buy('CALL', amount=1, symbol=symbol, duration=5, duration_unit='t'))
```

---

## Document

### Import 
```python
from binaryapi.stable_api import Binary
```
---
### Enabling Debug Logs

```python
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s %(message)s')
```
---
### Authorize/Login

```python
binary = Binary(token="YOUR-API-TOKEN-GOES-HERE")
```

---
I tried to add every API function available in Binary.com API documentation to this library, which you can call by accessing `api` variable of stable API

Examples:
```python
binary = Binary(token="YOUR-API-TOKEN-GOES-HERE")

# Buy API - https://developers.binary.com/api/#buy
binary.api.buy(buy, price, parameters=None, subscribe=None, passthrough=None, req_id=None)
# You must pass values for buy and price parameters

# Proposal API - https://developers.binary.com/api/#proposal
binary.api.proposal(contract_type, currency, symbol, amount=None, barrier=None, barrier2=None, basis=None, cancellation=None, date_expiry=None, date_start=None, duration=None, duration_unit=None, limit_order=None, multiplier=None, product_type=None, selected_tick=None, subscribe=None, trading_period_start=None, passthrough=None, req_id=None)
# You must pass values for contract_type, currency and symbol parameters

# Subscribe to Ticks API - https://developers.binary.com/api/#ticks
binary.api.ticks(ticks="frxEURUSD", subscribe=None, passthrough=None, req_id=None)

# For More API functions please refer to https://developers.binary.com/api/
```