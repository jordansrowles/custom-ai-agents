Write SYSTEM_AUTOPSY_{YYYY-M-D-HH-MM}.md as a uncompromising technical teardown of the codebase.

OBJECTIVE
Perform a rigorous, adversarial analysis intended to surface defects, risks, and false assumptions, not to explain or justify the implementation. Identify and explain all defects, incorrect logic, architectural failures, broken or leaky abstractions, performance and scalability bottlenecks, concurrency and lifecycle risks, security or reliability hazards, consistency violations, unnecessary complexity, dead code, misused patterns, missing or over-engineered features, and all forms of technical debt

ANALYSIS DIMENSIONS
For each applicable dimension below, identify all findings — even if they overlap:

A. Architecture & Design
- Intended architecture inference
- Boundary and abstraction integrity
- Dependency direction and coupling
- Pattern correctness and misuse
- Domain model alignment
- Change amplification and blast radius

B. Code Quality & Correctness
- Logical defects and invalid assumptions
- Dead code and unreachable paths
- Naming and semantic drift
- Invariant enforcement
- Error handling correctness

C. Performance & Scalability
- Hot paths and algorithmic complexity
- Allocation and resource waste
- Blocking and sync-over-async
- Scaling behavior (10×, 100×)
- Latency amplification

D. Concurrency & Lifecycle
- Thread safety and shared state
- Async misuse and races
- Object and resource lifetimes
- Startup and shutdown paths
- Partial initialization risks

E. Security & Reliability
- Trust boundaries and attack surfaces
- Input validation and injection risks
- Secret handling and logging leaks
- Failure modes and recovery safety
- Data corruption paths

F. Testing & Observability- Test coverage quality vs quantity
- Over-mocking and false confidence
- Missing boundary tests
- Logging signal vs noise
- Metrics and diagnosability gaps

G. Operability & Evolution
- Configuration and environment drift
- Deployment and migration risk
- Dependency rot and upgrade traps
- Maintainability and cognitive load
- Long-term evolution blockers

FOR EACH FINDING, PROVIDE
- Category (e.g., defect, anti-pattern, risk, debt, violation)
- Severity (Critical / High / Medium / Low)
- Evidence (explicit code references, behaviors, or concrete examples)
- Root cause (design, architectural, process, or conceptual)
- Real-world impact (failure modes, scalability, security, operability, change risk)
- Corrective action (delete, refactor, redesign, isolate, guard, or accept)
- Cost and risk of the fix
- What breaks if this is not fixed

CONSTRAINTS
- No politeness, no hedging, no generic advice
- Name anti-patterns and smells explicitly
- Infer intended design and call out contradictions
- Prefer deletion and simplification over abstraction
- State uncertainty explicitly when evidence is insufficient

OUTPUT REQUIREMENTS
- Use concrete language
- No filler, no praise
- Prioritise clarity over completeness
- End with a ranked remediation plan separating:
  - Immediate fixes
  - Structural/high-risk fixes
  - Acceptable debt
  - Code that should be removed entirely