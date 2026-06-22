# Agile Backlog & Requirements Layout

## User Story: Outbound Middleware Validation & Duplicate Prevention Engine

**As an** Outbound Integration Middleware Developer,  
**I want** the legacy transaction feed system to validate transaction payload attributes against updated market rules before transmission,  
**So that** duplicate, missing, or inverse-direction settlement instructions are caught and stopped before reaching the third-party application.

### Acceptance Criteria (Given-When-Then Framework)

#### Scenario 1: Prevention of Duplicate Booking Instructions
* **Given** the internal collateral booking system generates a transaction payload (IM, VM, Substitution, or Interest),
* **When** the legacy middleware processes the record,
* **Then** the system must cross-verify the Unique Transaction Identifier (UTI) against a rolling 24-hour log table of sent payloads.
* **And** if a duplicate UTI matches, the system must drop the duplicate record and flag an exception alert.

#### Scenario 2: Validation of Transaction Direction Mapping
* **Given** a security substitution or margin call is requested,
* **When** the transaction direction is processed by the legacy feed layer,
* **Then** the middleware must explicitly map the field `Direction_ID` based on parameters: `01` for Deliver and `02` for Receive.
* **And** reject any message payload where the direction field contains blank, null, or inverted values.

