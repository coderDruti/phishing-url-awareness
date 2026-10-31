# Test Results

Python version used: 3.13.9 | Operating system: Windows | Date: 29.10.2026

| # | Input | Expected result | Actual result | Pass/Fail |
| --- | ------- | ----------------- | --------------- | ----------- |
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety | Pass |
| 2 | http://192.0.2.10/account | IP address + HTTP | 1. Uses an IP address instead of a familiar domain. 2. Uses HTTP. HTTPS alone does not prove trust. | Pass |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | 1. Contains an @ symbol; inspect carefully. 2. Uses HTTP. HTTPS alone does not prove trust. | Pass |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains | Pass |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | Contains a punycode-style hostname | Pass |

## Notes

- Simply pressing enter produces the following output:
    No URL entered
- Entering the url "www.example.com" with a missing scheme produces the following result:
    Uses HTTP. HTTPS alone does not prove trust
  - Missing scheme is treated as http://
- Entering the url "https://secure-login.example.invalid" with a tricky name produces the following output:
    No listed warning signs found. This does NOT prove safety.
  - A tricky name slips through
