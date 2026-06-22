# User Acceptance Testing (UAT) Script Matrix

This document outlines the operational system validations completed in the UAT environment prior to production sign-off.

| Test ID | Scenario Description | Input Test Data | Expected Functional Result | Status |
| :--- | :--- | :--- | :--- | :--- |
| **UAT-001** | Single processing of high-volume VM call. | `TXN_ID: 98765`, `Collateral: Cash`, `Amt: $5,000,000`, Duplicate files pushed twice. | Middleware processes the first message; drops the duplicate message. Zero duplicates downstream. | **Passed** |
| **UAT-002** | Security Substitution multi-directional flow execution. | `TXN_ID: 43210`, `Return Security: ISIN-A (Deliver)`, `Receive Security: ISIN-B (Receive)`. | Middleware generates two distinct payloads with precise direction fields (`01` and `02`) without drops. | **Passed** |
| **UAT-003** | Boundary validation of Interest Booking under negative rates. | `TXN_ID: 11223`, `Interest Rate: -0.25%`, Direction inverted via legacy code. | System detects negative value, maintains standard direction field mapping, and signs off amount logic without crashing. | **Passed** |

