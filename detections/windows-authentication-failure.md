# Detection: Windows Authentication Failure

## Alert

- Windows Event ID: 4625

## Description

Wazuh detected multiple failed Windows authentication attempts.

## Severity

Medium

## Investigation

- Verified alert in Wazuh Dashboard.
- Confirmed failed login attempts.
- Reviewed Windows Security Logs.

## Recommendation

Investigate repeated failed logins to identify possible brute-force attacks.
