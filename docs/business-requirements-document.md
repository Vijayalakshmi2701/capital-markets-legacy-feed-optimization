# Functional Business Requirements Document (BRD)

## 1. Functional Scope & Context Diagram
The middleware update must serve as a programmatic gatekeeper that structural validation rules pass through before moving data downstream.

[Collateral System] ---> [Legacy Middleware (Rule Validation Layer)] ---> [Third-Party App]
## 2. Legacy vs. Modern Business Rules Matrix

| System Module | Outdated Legacy Business Rule (Old System) | New Modernized Business Rule (To-Be System) |
| :--- | :--- | :--- |
| **Duplicate Checking** | Accepted any payload sent by the source system blindly. | Must validate the Unique Transaction Identifier (UTI) against a rolling 24-hour log table. Duplicate UTIs must be dropped and logged as exceptions. |
| **Direction Mapping** | Hardcoded based on ancient transaction categories, causing inversion errors. | Enforce explicit mapping fields based on legal execution: `01` for Deliver (Outbound) and `02` for Receive (Inbound). |
| **Substitution Logic** | Processed return and receipt legs of asset swaps as independent, detached trades. | Require a hard relational link connecting the old collateral release message to the new security intake event to prevent mismatched data drops. |
