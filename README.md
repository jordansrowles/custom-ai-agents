# Custom AI Agents

A collection of specialized AI agents for GitHub Copilot, each designed to handle specific software development tasks with domain expertise.

## Agent Capabilities

| Agent | Production Code | Test Code | Analysis Reports | Code Reviews | Documentation |
|-------|----------------|-----------|------------------|--------------|---------------|
| **Performance Optimiser** | ✅ Edits | ✅ Edits | ✅ Creates | ✅ Reviews | ✅ Updates |
| **Refactoring Specialist** | ✅ Edits | ✅ Edits | ❌ | ✅ Reviews | ✅ Updates |
| **Security Reviewer** | ❌ Read-only | ❌ Read-only | ✅ Creates | ✅ Reviews | ❌ |
| **Senior Software Architect** | ❌ Read-only | ❌ Read-only | ✅ Creates | ✅ Reviews | ❌ |
| **Test Data Curator** | ❌ Read-only | ✅ Edits | ❌ | ✅ Reviews | ✅ Updates |
| **Test Specialist** | ❌ Read-only | ✅ Edits | ❌ | ✅ Reviews | ✅ Updates |

## Agents

### Performance Optimiser
Focuses on runtime performance, memory usage, and scalability. Prioritizes measurement and evidence over guesswork. Can edit both production and test code to improve performance metrics.

### Refactoring Specialist
Improves code structure, readability, and maintainability without changing observable behavior. Identifies code smells and applies targeted refactorings while preserving functionality.

### Security Reviewer
Analyzes security posture, threat surfaces, and secure coding practices. Performs read-only reviews and produces structured security reports with prioritized recommendations.

### Senior Software Architect
Evaluates software architecture against established patterns (Clean Architecture, Hexagonal, DDD, etc.). Produces comprehensive analysis reports identifying violations, anti-patterns, and improvement opportunities.

### Test Data Curator
Manages test data creation, organization, and cleanup. Focuses on making tests reliable and realistic through proper data management patterns and factory methods.

### Test Specialist
Enhances test coverage and quality across unit, integration, and end-to-end tests. Works exclusively in test code to identify gaps and improve test reliability and maintainability.

## Usage

Each agent is defined in its own markdown file with structured frontmatter and detailed instructions. To use an agent, reference the appropriate file in your GitHub Copilot agent configuration.

The agents are designed to work independently or in combination to handle different aspects of software development workflows.
