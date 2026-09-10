# Operating Model

## 1. Purpose

This document defines how the AI-Powered Enterprise Knowledge Assistant will be operated and supported after production launch.

The objective is to establish clear ownership for:

- Day-to-day operations
- Monitoring
- Incident management
- User support
- Data freshness
- Security and access
- AI quality
- Cost management
- Model changes
- Knowledge transfer
- Business As Usual (BAU)

The operating model ensures the system remains reliable, secure, useful, and maintainable after the initial project is completed.

---

# 2. Operating Principles

## Principle 1: Clear Ownership

Every operational responsibility must have an identified owner.

The TPM coordinates during the project and transition but does not become the permanent owner of every operational function.

---

## Principle 2: Operations Own BAU

Once the system is formally transitioned to BAU, Operations/SRE and the appropriate functional teams own ongoing operational responsibilities.

The project team remains available during the defined hypercare period.

---

## Principle 3: AI Requires Ongoing Monitoring

AI systems require more than traditional infrastructure monitoring.

The team must monitor:

- System health
- Retrieval quality
- Answer quality
- Grounding
- Data freshness
- Security
- Cost
- Model behavior
- User feedback

---

## Principle 4: Changes Require Appropriate Validation

Changes to the LLM, embedding model, retrieval logic, chunking strategy, data sources, or security model should follow an appropriate change-management process.

The level of validation should match the risk and impact of the change.

---

# 3. Operating Model Overview

The operating model consists of the following areas:

1. Platform Operations
2. AI Operations
3. Data Operations
4. Security and Privacy
5. Product Management
6. User Support
7. Incident Management
8. Change Management
9. Continuous Improvement

---

# 4. Roles and Responsibilities

| Area | Primary Owner | Supporting Teams |
|---|---|---|
| Product roadmap | Product | Business, TPM |
| Technical platform | Engineering / SRE | AI/ML |
| AI quality | AI/ML | Product, Data |
| Data ingestion | Data / Engineering | Business |
| Data freshness | Data / Business | Product, Engineering |
| Authorization | Security / Engineering | IT |
| Privacy | Privacy / Legal | Security, Product |
| Monitoring | SRE / Operations | Engineering |
| Incident response | SRE / Operations | Engineering, Security, Product |
| User support | Support / Operations | Product |
| Cost management | Product / Engineering | Finance |
| Model changes | AI/Engineering | Product, Security |
| Business communications | Product / TPM | Business |
| Program coordination | TPM | All teams |

---

# 5. Platform Operations

Engineering/SRE is responsible for the technical health of the production system.

### Responsibilities

- Infrastructure health
- Service availability
- Performance
- Capacity
- Scaling
- Database health
- Vector database health
- Dependency monitoring
- Backup and recovery
- Deployment infrastructure
- Operational alerts
- Technical incident response

### Key Metrics

- Availability
- Latency
- Error rate
- Throughput
- Resource utilization
- Dependency failures
- Recovery performance

---

# 6. AI Operations

AI/ML Engineering owns the ongoing health of the AI behavior.

### Responsibilities

- LLM performance
- Retrieval quality
- Reranking
- Prompt/configuration management
- Grounding
- Citation behavior
- AI evaluation
- Model monitoring
- Model lifecycle
- Regression testing

### AI Quality Monitoring

Monitor for:

- Incorrect answers
- Unsupported answers
- Missing citations
- Poor retrieval
- Increased no-answer rate
- Model behavior changes
- User-reported quality issues

---

# 7. Data Operations

Data/Engineering owns the enterprise knowledge pipeline.

### Responsibilities

- Document ingestion
- Document processing
- Chunking
- Embedding generation
- Vector index updates
- Metadata
- Version management
- Duplicate detection
- Stale content handling
- Document deletion
- Refresh failures

### Critical Data Updates

For critical business or policy documents:

1. Source document is updated
2. Change is detected
3. Urgent ingestion/refresh is triggered
4. New content is processed
5. Embeddings/index are updated
6. Validation is performed
7. Previous version is deactivated when appropriate
8. AI begins using the new authoritative version

The end-to-end update process should have a defined business SLA for critical content.

---

# 8. Security and Privacy Operations

Security and Privacy teams remain responsible for their respective controls after launch.

### Security Responsibilities

- Authorization
- Authentication
- Security monitoring
- Security incidents
- Access reviews
- Vulnerability management
- Security testing

### Privacy Responsibilities

- Data handling
- Retention
- Privacy requirements
- Regulatory considerations
- Privacy reviews for significant changes

### Security Principle

Unauthorized information must never be provided to the LLM or exposed to the user.

---

# 9. User Support

Users should have a clear way to report:

- Incorrect answers
- Missing information
- Outdated information
- Access problems
- Technical errors
- Poor search results
- Other concerns

Support should classify issues and route them to the appropriate team.

### Example Routing

**Incorrect answer**

→ AI/ML Engineering

**Outdated document**

→ Data / Document Owner

**Unauthorized access concern**

→ Security

**Application failure**

→ Engineering / SRE

**Business policy question**

→ Appropriate Business Owner

**General product feedback**

→ Product

---

# 10. Incident Management

Production incidents should follow the organization's standard incident-management process.

### Incident Lifecycle

1. Detect
2. Alert
3. Triage
4. Assign severity
5. Assign owner
6. Mitigate
7. Communicate
8. Recover
9. Validate recovery
10. Document
11. Review when appropriate

### AI-Specific Incidents

Examples include:

- Unauthorized information exposure
- Significant hallucination/grounding issue
- Retrieval failure
- Incorrect policy answer
- Large increase in no-answer responses
- Model regression
- Data freshness failure
- Unexpected cost increase

Security-related incidents should follow the organization's security incident process.

---

# 11. Change Management

Changes should be evaluated according to risk.

### Examples of Changes

- LLM replacement
- Embedding model replacement
- Prompt changes
- Retrieval changes
- Reranking changes
- Chunking changes
- Vector database changes
- New document source
- Permission model changes
- Infrastructure changes

### Change Evaluation

Depending on the change, evaluate:

- AI quality
- Retrieval quality
- Security
- Privacy
- Performance
- Reliability
- Cost
- Data migration
- Rollback

### Embedding Model Changes

Changing the embedding model may require:

- Re-embedding the document corpus
- Creating a new vector index
- Comparing retrieval quality
- Running regression tests
- Validating security metadata
- Comparing cost and performance
- Planning rollback

Major changes should not be introduced directly into production without appropriate validation.

---

# 12. AI Evaluation in BAU

Evaluation does not end at launch.

The team should periodically evaluate the system using:

- Representative user questions
- Known critical questions
- Newly identified failure cases
- Security test cases
- Freshness test cases
- Negative test cases

Evaluation should be repeated after significant model, retrieval, data, or architecture changes.

---

# 13. Cost Management

Product and Engineering should monitor ongoing operating cost.

### Monitor

- Cost per query
- LLM usage
- Embedding usage
- Vector database cost
- Compute
- Storage
- Monitoring
- Data processing

### Cost Review

If costs exceed agreed expectations, the team should investigate:

- Model selection
- Retrieval configuration
- Context size
- Caching opportunities
- Query patterns
- Infrastructure utilization
- Data-processing efficiency

Cost optimization must not compromise required quality or security.

---

# 14. Monitoring and Reporting

Operational dashboards should provide visibility into:

### System Health

- Availability
- Latency
- Errors
- Capacity

### AI Health

- Retrieval quality
- Answer quality
- Grounding
- No-answer rate
- User feedback

### Data Health

- Freshness
- Ingestion success
- Index health
- Stale content

### Security

- Authorization failures
- Security events
- Access anomalies

### Cost

- Query volume
- Cost/query
- Total operating cost

---

# 15. Knowledge Transfer

Before the project transitions to BAU, the project team must transfer operational knowledge to the permanent owners.

### Knowledge Transfer Package

- Architecture
- Data flow
- Retrieval flow
- Security model
- Permission model
- Monitoring dashboards
- Alerts
- Incident runbooks
- Escalation paths
- Data refresh procedures
- Model-change procedures
- Backup/recovery procedures
- Known issues
- Dependencies
- Vendor information
- Cost model

---

# 16. Operational Readiness Validation

Knowledge transfer is not complete simply because documentation has been delivered.

Operations should demonstrate that they can:

- Monitor the system
- Interpret alerts
- Triage common incidents
- Escalate appropriately
- Execute recovery procedures
- Understand data refresh processes
- Understand the security model
- Support users
- Identify when Engineering, Security, or Product involvement is required

The TPM should track operational-readiness gaps to closure or formally accepted risk.

---

# 17. Hypercare to BAU Transition

The transition should occur in stages.

### Stage 1 — Launch

Project team and Operations jointly monitor the system.

### Stage 2 — Hypercare

Project team remains highly engaged while Operations increasingly handles normal operational activities.

### Stage 3 — BAU Readiness

Operations demonstrates readiness through monitoring, incident response, and support procedures.

### Stage 4 — Formal Handoff

Operational ownership is formally accepted.

### Stage 5 — BAU

Operations and functional teams manage the system as a normal production service.

---

# 18. BAU Ownership

After formal handoff:

### Product

Owns:

- Product roadmap
- Business value
- User needs
- Prioritization
- Product changes

### Engineering / SRE

Owns:

- Platform
- Reliability
- Performance
- Infrastructure
- Technical incidents

### AI/ML

Owns:

- AI quality
- Model lifecycle
- Evaluation
- Retrieval behavior

### Data

Owns:

- Data pipeline
- Data freshness
- Document lifecycle
- Indexing

### Security

Owns:

- Security controls
- Authorization
- Security incidents

### Privacy / Legal

Owns:

- Privacy and legal requirements

### Operations / Support

Owns:

- Monitoring
- User support
- Incident coordination
- Operational reporting

---

# 19. Continuous Improvement

The product should continuously improve based on:

- User feedback
- Production incidents
- AI evaluation results
- New business requirements
- Data-quality findings
- Cost trends
- Performance trends
- Security findings

Potential improvements may include:

- Better retrieval
- Better chunking
- Better reranking
- Improved source quality
- Improved user experience
- New supported use cases
- Cost optimization
- Model upgrades

Each significant improvement should follow the appropriate product and change-management process.

---

# 20. Escalation Model

Escalation should occur when:

- A production issue exceeds the team's ability to resolve it
- Security or privacy risk is identified
- Business impact is significant
- SLA may be missed
- A major architectural decision is required
- A significant model change is proposed
- Cost exceeds approved expectations
- AI quality falls below agreed standards

The person discovering the issue does not need to solve every problem alone.

The operating model should make it clear:

**Who owns it → Who needs to know → Who decides → Who executes → Who communicates**

---

# 21. BAU Success Criteria

The transition to BAU is complete when:

- Operational ownership is accepted
- Monitoring is active
- Alerts are validated
- Incident procedures are understood
- Runbooks are available
- Support ownership is established
- Data refresh process is operational
- Security responsibilities are established
- AI evaluation process is established
- Model-change process is established
- Backup/recovery procedures are understood
- Known issues are documented
- Open risks have owners
- Required stakeholders accept the handoff

---

# 22. TPM Role After Handoff

The TPM's role changes after BAU transition.

During the project, the TPM focuses on:

- Planning
- Coordination
- Risk management
- Dependencies
- Execution
- Readiness
- Launch
- Communication

After BAU transition, the TPM may become involved when:

- A major new capability is introduced
- A significant architecture change occurs
- A major migration is required
- Cross-functional risks require program coordination
- A new strategic initiative is launched

The TPM should not become the permanent operational owner simply because they managed the original project.

---

# 23. Document Ownership

**Primary Owner:** Technical Program Manager during project and transition

**BAU Owners:**

- Product
- Engineering / SRE
- AI/ML
- Data
- Security
- Privacy/Legal
- Operations / Support

**Project Phase:** Prototype / Pre-Production

**BAU Transition Date:** TBD

**Hypercare Duration:** TBD

**Production Support Model:** TBD
