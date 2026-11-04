# Exercise 01 – CSRF Vulnerability

## Overview
Cross-Site Request Forgery (CSRF) is a web security vulnerability that allows an attacker to trick an authenticated user into performing unwanted actions without their knowledge.

## Vulnerability Description
The application contains a CSRF vulnerability in the `/transfer` endpoint.

The endpoint accepts POST requests to transfer funds without:
- CSRF token validation.
- Origin or Referer validation.
- Proper cross-origin request protection.

As a result, an attacker may exploit the victim's authenticated session to perform unauthorized transactions.

## Exploitation Scenario
1. The victim logs into the vulnerable application.
2. The victim visits a malicious webpage.
3. The webpage automatically submits a POST request to `/transfer`.
4. The browser may include the victim's session cookies.
5. The application processes the unauthorized transaction.

## Impact
- Unauthorized financial transactions.
- Unauthorized actions using authenticated sessions.
- Potential financial loss.

## Proof of Concept
See [PAYLOAD.md](PAYLOAD.md) for the HTML CSRF payload.

## Mitigation
See [FIX.md](FIX.md) for recommended security solutions.

## Disclaimer
This project is for educational purposes and authorized security testing only.
