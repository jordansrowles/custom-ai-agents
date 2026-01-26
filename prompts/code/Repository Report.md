Write REPOSITORY_AUTOPSY_{YYYY-MM-DD_HH-mm}.md as a full-spectrum, uncompromising technical autopsy of the provided repository.

This report is intended to be read by the projects maintainers. Do not explain concepts. Do not soften language. Do not praise effort. The goal is accuracy, risk exposure, and decision support.

ASSUME
- The repository is production-critical or will become so.
- The code will be modified under time pressure by engineers unfamiliar with its internals.
- The environment is hostile: partial failures, bad inputs, scale, concurrency, and misuse are expected.
- Missing context is a failure of the codebase, not an excuse.

GLOBAL OUTPUT RULES
- Use Markdown.
- Use clear, stable headers (##, ###, ####).
- Every major section MUST have an anchorable header.
- Add a Table of Contents at the top that links to every H2 and H3 header.
- Under EVERY H2 and H3 header, add a small “↑ Back to Top” link that points to the Table of Contents anchor.
- Do not include filler text.
- Do not repeat yourself—cross-reference sections instead.
- When uncertain, state uncertainty explicitly and explain what evidence is missing.

STRUCTURE REQUIREMENTS

1. TITLE AND METADATA
- Repository name
- Commit / branch analyzed
- Analysis date
- Assumed runtime environments
- Assumed usage profile (interactive, batch, service, library, etc.)

2. TABLE OF CONTENTS
- Auto-generated
- Links to all sections and subsections
- Anchor target at the very top named `#top`

---

## 3. EXECUTIVE SUMMARY (NO EXCUSES)
↑ Back to Top

Summarize in plain, brutal terms:
- What is fundamentally wrong
- What is solid (if anything)
- What will break first
- What will cost the most to fix later if ignored
- Whether this codebase should be:
  - Stabilized
  - Incrementally refactored
  - Partially rewritten
  - Fully replaced

No technical euphemisms. This section should stand alone.

---

## 4. REPOSITORY OVERVIEW AND INTENT INFERENCE
↑ Back to Top

Infer and document:
- The apparent purpose of the system
- The intended users and workflows
- The implied architectural style
- The mental model the original authors likely had

Explicitly call out where the implementation contradicts these inferred intentions.

---

## 5. ARCHITECTURE AND SYSTEM DESIGN
↑ Back to Top

### 5.1 High-Level Architecture
↑ Back to Top
- Actual component layout (not aspirational)
- Dependency direction and coupling
- Layering violations
- Circular dependencies

### 5.2 Boundary and Abstraction Integrity
↑ Back to Top
- Leaky abstractions
- Boundary breaches between layers
- Knowledge bleeding across modules

### 5.3 Pattern Usage and Misuse
↑ Back to Top
- Correctly applied patterns
- Cargo-cult patterns
- Anti-patterns (by name, with evidence)
- Places where patterns increased complexity with no payoff

---

## 6. CODE QUALITY AND CORRECTNESS
↑ Back to Top

### 6.1 Logical Defects and Incorrect Assumptions
↑ Back to Top
- Explicit bugs
- Implicit assumptions that can be violated
- Undefined or unstable behavior

### 6.2 Naming, Semantics, and Drift
↑ Back to Top
- Misleading names
- Concepts that changed meaning over time
- Inconsistent terminology

### 6.3 Invariants and Preconditions
↑ Back to Top
- Critical invariants
- Where they are enforced
- Where they are silently violated

---

## 7. PERFORMANCE AND SCALABILITY
↑ Back to Top

### 7.1 Hot Paths and Complexity
↑ Back to Top
- Algorithmic complexity
- Accidental quadratic behavior
- Inefficient data structures

### 7.2 Resource Management
↑ Back to Top
- Memory allocation patterns
- I/O behavior
- Blocking calls

### 7.3 Scaling Failure Forecast
↑ Back to Top
- Behavior at 10× and 100× load
- First bottleneck
- Cascading failure risks

---

## 8. CONCURRENCY, ASYNC, AND LIFECYCLE
↑ Back to Top

### 8.1 Thread Safety and Shared State
↑ Back to Top
- Race conditions
- Unsafe mutation
- False assumptions about execution order

### 8.2 Async Usage
↑ Back to Top
- Fake async
- Sync-over-async
- Latency amplification

### 8.3 Startup and Shutdown
↑ Back to Top
- Partial initialization
- Order dependencies
- Resource leaks

---

## 9. ERROR HANDLING AND FAILURE MODES
↑ Back to Top

### 9.1 Exception and Error Propagation
↑ Back to Top
- Swallowed errors
- Misleading recovery
- Silent corruption

### 9.2 Failure Mode Analysis
↑ Back to Top
- How the system fails
- Whether failure is safe
- Recovery realism

---

## 10. SECURITY AND RELIABILITY
↑ Back to Top

### 10.1 Threat Model
↑ Back to Top
- Trust boundaries
- Attack surfaces
- Privilege escalation paths

### 10.2 Data and Secret Handling
↑ Back to Top
- Input validation
- Injection risks
- Secret storage and exposure

---

## 11. TESTING AND CONFIDENCE ANALYSIS
↑ Back to Top

### 11.1 Test Coverage Reality Check
↑ Back to Top
- What is tested vs what matters
- Missing boundaries
- Dead tests

### 11.2 False Confidence Sources
↑ Back to Top
- Over-mocking
- Brittle assertions
- Tests that lie

---

## 12. OBSERVABILITY AND OPERABILITY
↑ Back to Top

### 12.1 Logging and Diagnostics
↑ Back to Top
- Signal vs noise
- Missing visibility
- Misleading success logs

### 12.2 Configuration and Environments
↑ Back to Top
- Config drift
- Unsafe defaults
- Environment-specific behavior

---

## 13. DEPENDENCIES AND EXTERNAL RISK
↑ Back to Top

- Unused dependencies
- Overpowered libraries
- Upgrade and supply-chain risk
- Dependencies masking simple code

---

## 14. TECHNICAL DEBT INVENTORY
↑ Back to Top

For each debt item:
- Description
- Origin
- Interest rate
- Compounding risk
- Recommended action (pay, isolate, delete, ignore)

---

## 15. CHANGE RISK AND MAINTAINABILITY
↑ Back to Top

- High-blast-radius modules
- Cognitive load hotspots
- Areas hostile to modification

---

## 16. PRIORITIZED REMEDIATION PLAN
↑ Back to Top

### 16.1 Fix Immediately
↑ Back to Top
Issues that will cause outages, data loss, or security incidents.

### 16.2 Structural Fixes
↑ Back to Top
High-cost, high-payoff changes.

### 16.3 Acceptable Debt
↑ Back to Top
Debt that can be lived with short-term.

### 16.4 Code to Remove
↑ Back to Top
What should be deleted entirely and why.

---

## 17. FINAL VERDICT
↑ Back to Top

State clearly:
- Is this codebase viable long-term?
- Under what constraints?
- What happens if no action is taken?

No hedging. No “it depends.”