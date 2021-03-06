---
title: Payment requests overview
---

# Payment requests

You can generate a payment request URI that will be interpretted by a Bitcoin wallet to execute a payment.

## Generate request

Generating a payment request using oogway only takes one line of code:

```python
>>> from oogway import request_payment
>>> request_payment("1FHXDkRLhoCziRjftaPB3fELUYrZomFanx", 20000, exp=60, message="from oogway with love")

'bitcoin:1FHXDkRLhoCziRjftaPB3fELUYrZomFanx?amount=0.00020000&time=1598321506&exp=3600&message=from%20oogway%20with%20love'
```

## Parse request

Parsing payment requests is also possible with oogway:

```python
>>> from oogway import parse_request
>>> parse_request("bitcoin:1FHXDkRLhoCziRjftaPB3fELUYrZomFanx?amount=0.00020000&time=1598321506&exp=3600&message=from%20oogway%20with%20love")

{
    'address': '1FHXDkRLhoCziRjftaPB3fELUYrZomFanx',
    'amount': '20000',
    'created': '2020-08-25 04:11:46',
    'status': 'expired',
    'exp': '3600',
    'message': 'from oogway with love'
}
```

## CLI

You can also generate payment requests using the CLI:

```console
$ oogway request-payment 1FHXDkRLhoCziRjftaPB3fELUYrZomFanx 2000 --expire 60 --message "from oogway with love"

> bitcoin:1FHXDkRLhoCziRjftaPB3fELUYrZomFanx?amount=0.00020000&time=1598321506&exp=3600&message=from%20oogway%20with%20love
```