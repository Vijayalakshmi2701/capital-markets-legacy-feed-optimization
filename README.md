# capital-markets-legacy-feed-optimization
Business Analysis case study focused on legacy middleware modernization and data integrity automation for OTC derivative collateral settlements.
# Case Study: Legacy Feed Optimization & STP Automation Engine

## 📌 Project Overview
* **Domain:** Capital Markets, OTC Derivatives, Collateral Management (Margin & Cleared Space)
* **Target Objective:** Modernise a legacy IT middleware data feed to eliminate broken downstream security settlement instructions.
* **Core Metrics Achieved:** **80% reduction** in manual security settlement failures; **100% data integrity** for Straight-Through Processing (STP).
* **BA Competencies Demonstrated:** Root Cause Analysis (RCA), Requirements Elicitation, Business Rules Definitions, User Acceptance Testing (UAT).

---

## 🔍 The Business Problem
The internal Collateral Booking System processes daily high-value transactions: **Initial Margin (IM), Variation Margin (VM), Substitutions, and Interest Bookings**. These were sent via an automated feed to a Third-Party Settlement System. 

Due to structural data flaws within the legacy middleware, corrupt data payloads were regularly transmitted downstream, creating:
1. **Duplicate booking instructions** inflating market exposure.
2. **Incorrect settlement directions** (swapping delivery and receipt instructions).
3. **Missing or unmatched instructions** failing clearinghouse validation.

The Settlements Team had to manually investigate and re-key broken transactions daily, generating severe operational overhead and settlement risk.

---

## 🛠️ My Business Analysis Approach

### 1. Root Cause Analysis (Data Discovery)
I cross-verified daily Settlement Failure Reports against operational datasets. I isolated the structural cause: the **Legacy IT System relied on outdated, hardcoded collateral exchange rules** and was unable to parse modern structural data fields required by modern clearinghouses.

### 2. Functional Requirements Engineering
I acted as the bridge translator between operations and technology. I extracted modern market parameters (ISDA/CSA standards) and translated them into actionable functional specifications for the development team to update the core application code.

### 3. Validation & Quality Assurance (UAT)
I defined comprehensive testing scenarios to replicate complex settlement profiles (e.g., negative interest rates and multi-leg asset substitutions) to ensure zero failures occurred post-deployment.

---

## 📂 Project Deliverables & Artifacts
To review the underlying technical documentation produced for this project, browse the following files:
* 📑 **[Business Requirements Document (BRD)](docs/business-requirements-document.md)** - Explains the legacy vs. modern business rules and system context diagram.
* 📋 **[Agile User Stories & Backlog](docs/user-stories-backlog.md)** - Shows how requirements were structured for technical developer implementation.
* 🧪 **[User Acceptance Testing (UAT) Scripts](docs/user-acceptance-testing.md)** - Details the validation matrix and test data variations.
