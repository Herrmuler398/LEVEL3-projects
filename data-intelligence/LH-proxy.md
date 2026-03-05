# Lufthansa API Proxy

If you are unable to register for a Lufthansa OpenAPI account or generate your own `client_id` and `client_secret`, you can use this proxy instead.

The proxy handles OAuth authentication for you — no credentials are required. You only need a **password** to access it. Ask your instructor if you don't have one.

---

## Base URL

```
https://lh-proxy.onrender.com
```

---

## Authentication

Every request must include the password in the request header:

```python
headers = {"password": "your-password-here"}
```


## Example Endpoints

| Category       | Endpoint                                                    |
|----------------|-------------------------------------------------------------|
| Airports       | `/v1/references/airports/FRA`                               |
| Flight status  | `/v1/operations/flightstatus/route/MUC/FRA/2026-03-05`      |
| Schedules      | `/v1/operations/schedules/LH400`                            |
