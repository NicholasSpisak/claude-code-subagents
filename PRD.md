# Universal Technical Implementation Template for Claude Code Subagents

## Executive Overview

### Purpose Statement
This template provides a comprehensive, domain-agnostic framework for creating high-performance Claude Code subagents. It incorporates best practices from Anthropic's official documentation, proven design patterns, and systematic validation approaches to ensure consistent quality across all specialized implementations.

### Strategic Value Proposition
Define the specific value your subagent provides:
- **Primary Domain**: [Specify the core expertise area]
- **Problem Space**: [Define the specific problems this agent solves]
- **Target Users**: [Identify who benefits from this agent]
- **Differentiation**: [What makes this agent unique or necessary]
- **Integration Value**: [How this agent complements other subagents]

### Expected Outcomes
- **Performance Gains**: [Quantify expected improvements, e.g., 50%+ faster task completion]
- **Quality Metrics**: [Define quality standards, e.g., 95%+ accuracy]
- **User Experience**: [Describe the improved workflow]
- **Business Impact**: [Outline tangible benefits]

## Agent Configuration Specification

### Metadata Structure
```yaml
---
name: [agent-name]  # lowercase letters and hyphens only
type: claude-code-subagent
version: 1.0.0
description: |  # Action-oriented description
  [Clear, concise description of when to use this agent
  and what specific capabilities it provides]
color: [hex-color]  # Visual identifier for UI
tools:  # Optional: specify exact tools or inherit all
  - Read
  - Write
  - Edit
  - [Additional tools as needed]
created: [ISO-8601 date]
author: [creator-identifier]
tags: [domain, expertise, use-case]
---
```

### Naming Conventions
- **Format**: `domain-specialty-role` (e.g., `security-vulnerability-analyst`)
- **Length**: Maximum 30 characters
- **Style**: Descriptive, action-oriented, lowercase with hyphens

### Tool Permission Matrix
| Tool Category | Common Tools | Use Cases | Security Notes |
|---------------|--------------|-----------|----------------|
| File Operations | Read, Write, Edit, MultiEdit | Code modification, analysis | Restrict write access for read-only agents |
| Search & Analysis | Grep, Glob, LS | Pattern matching, discovery | Essential for analysis agents |
| Execution | Bash, TodoWrite | Build, test, deploy | High-risk, grant selectively |
| Web & Research | WebSearch, WebFetch | Documentation, API lookup | Consider rate limits |
| Specialized | MCP servers, Notebooks | Domain-specific tasks | Match to agent purpose |

## Domain Expertise Framework

### Core Identity Definition
```markdown
# Agent Identity

## Primary Role
[Define the agent's primary function and expertise in 2-3 sentences]

## Core Competencies
1. **[Competency 1]**: [Specific skills and knowledge]
2. **[Competency 2]**: [Technical capabilities]
3. **[Competency 3]**: [Domain expertise]
4. **[Competency 4]**: [Methodological approach]
5. **[Competency 5]**: [Quality standards]

## Operating Principles
- **Principle 1**: [Core belief or approach]
- **Principle 2**: [Decision-making framework]
- **Principle 3**: [Quality standard]
- **Principle 4**: [Collaboration approach]
- **Principle 5**: [Learning philosophy]

## Priority Hierarchy
1. [Top Priority] > 2. [Second Priority] > 3. [Third Priority] > 4. [Fourth Priority]
Example: Security > Reliability > Performance > Features > Convenience
```

### Expertise Boundaries
```yaml
expertise_scope:
  primary_domains:
    - [Core domain 1]
    - [Core domain 2]
  secondary_domains:
    - [Supporting domain 1]
    - [Supporting domain 2]
  excluded_domains:
    - [Explicitly out of scope]
  handoff_triggers:
    - condition: [When to delegate]
      target_agent: [Which agent to recommend]
```

## Technical Implementation Guide

### Prompt Engineering Pattern
```markdown
# System Prompt Structure (400-character limit if applicable)

[IDENTITY: 50-75 chars]
You are a [role] specializing in [domain] with expertise in [specific areas].

[METHODOLOGY: 100-125 chars]
Your approach: [primary method]. You prioritize [key priorities] and ensure [quality standards].

[STANDARDS: 75-100 chars]
You follow [frameworks/principles] and validate using [methods]. Success means [criteria].

[FOCUS: 100-125 chars]
Core focus: [primary objectives]. You excel at [specific tasks] while maintaining [standards].
```

### Behavioral Specifications
```yaml
decision_framework:
  analysis_pattern:
    - step: "Understand context and requirements"
      tools: [Read, Grep]
      validation: "Requirements clearly defined"
    - step: "Analyze existing implementation"
      tools: [Read, Glob, Grep]
      validation: "Current state documented"
    - step: "Design solution approach"
      tools: [Write, TodoWrite]
      validation: "Solution addresses all requirements"
    - step: "Implement with validation"
      tools: [Edit, MultiEdit, Bash]
      validation: "Tests pass, quality gates met"
      
quality_gates:
  - gate: "Syntax Validation"
    criteria: "Code parses without errors"
    tools: [language-specific linters]
  - gate: "Type Safety"
    criteria: "Type checks pass"
    tools: [TypeScript, mypy, etc.]
  - gate: "Security Scan"
    criteria: "No critical vulnerabilities"
    tools: [security scanners]
  - gate: "Test Coverage"
    criteria: "≥80% unit, ≥70% integration"
    tools: [test runners]
  - gate: "Performance"
    criteria: "Meets defined benchmarks"
    tools: [profilers, benchmarks]
```

### Communication Patterns
```yaml
communication_style:
  tone: [professional|conversational|educational|direct]
  verbosity: [concise|balanced|detailed]
  technical_level: [beginner|intermediate|expert|adaptive]
  
response_structure:
  - opening: "Acknowledge request and confirm understanding"
  - analysis: "Present findings with evidence"
  - recommendation: "Provide actionable solutions"
  - validation: "Include success criteria"
  - closing: "Summarize next steps"
  
uncertainty_handling:
  - low_confidence: "Explicitly state assumptions"
  - medium_confidence: "Provide alternatives"
  - high_confidence: "Give definitive guidance"
  - knowledge_gap: "Recommend appropriate resources or agents"
```

## Validation and Testing Framework

### Pre-Deployment Checklist
- [ ] **Identity Validation**: Role clearly defined and differentiated
- [ ] **Tool Verification**: Only necessary tools granted
- [ ] **Prompt Testing**: Stays within character limits
- [ ] **Behavioral Testing**: Responds appropriately to test scenarios
- [ ] **Integration Testing**: Works well with other agents
- [ ] **Performance Testing**: Meets response time targets
- [ ] **Edge Case Testing**: Handles unusual inputs gracefully
- [ ] **Security Review**: No unintended permissions or capabilities

### Test Scenario Template
```yaml
test_scenarios:
  - name: "Basic Functionality Test"
    input: "[Sample request within agent's domain]"
    expected_behavior:
      - "Correctly identifies the task type"
      - "Uses appropriate tools"
      - "Provides accurate solution"
    validation_criteria:
      - "Solution works as intended"
      - "Follows defined standards"
      - "Completes within time limit"
      
  - name: "Edge Case Handling"
    input: "[Unusual or complex request]"
    expected_behavior:
      - "Recognizes complexity"
      - "Adapts approach appropriately"
      - "Maintains quality standards"
      
  - name: "Out-of-Scope Request"
    input: "[Request outside agent's expertise]"
    expected_behavior:
      - "Politely acknowledges limitation"
      - "Suggests appropriate alternative"
      - "Provides partial help if possible"
```

### Quality Metrics
```yaml
performance_metrics:
  response_time:
    target: "< 30 seconds for simple tasks"
    maximum: "< 5 minutes for complex tasks"
  accuracy:
    target: "95%+ for core domain tasks"
    minimum: "90%+ for edge cases"
  user_satisfaction:
    target: "4.5+ / 5.0 rating"
    measurement: "Post-interaction survey"
    
resource_utilization:
  context_window:
    target: "< 50% usage for typical tasks"
    warning: "70% usage"
    critical: "85% usage"
  tool_calls:
    optimal: "3-5 per task"
    maximum: "15 per task"
```

## Performance Optimization Strategies

### Context Window Management
```yaml
context_optimization:
  strategies:
    - name: "Selective Reading"
      description: "Read only relevant file sections"
      savings: "40-60% context reduction"
    - name: "Result Summarization"
      description: "Compress findings before proceeding"
      savings: "30-50% context reduction"
    - name: "Tool Output Filtering"
      description: "Request specific output formats"
      savings: "20-40% context reduction"
      
  patterns:
    - pattern: "Batch Operations"
      when: "Multiple similar operations needed"
      benefit: "Reduces tool call overhead"
    - pattern: "Progressive Refinement"
      when: "Large scope analysis required"
      benefit: "Manages context growth"
```

### Response Time Optimization
```yaml
speed_optimization:
  tool_selection:
    prefer:
      - Glob: "For file discovery (faster than LS)"
      - Grep: "For pattern search (faster than Read all)"
      - MultiEdit: "For multiple changes (faster than sequential Edit)"
    avoid:
      - "Reading entire large files unnecessarily"
      - "Recursive operations on deep directories"
      - "Redundant tool calls"
      
  caching_strategy:
    - "Cache file contents during session"
    - "Reuse analysis results"
    - "Store common patterns"
```

## Integration Patterns

### Multi-Agent Collaboration
```yaml
collaboration_patterns:
  - pattern: "Sequential Handoff"
    description: "One agent completes, hands to next"
    example: "Architect → Developer → Tester"
    
  - pattern: "Parallel Analysis"
    description: "Multiple agents analyze simultaneously"
    example: "Security + Performance + Quality"
    
  - pattern: "Hierarchical Delegation"
    description: "Lead agent coordinates specialists"
    example: "Architect delegates to domain experts"
    
  - pattern: "Peer Review"
    description: "Agents validate each other's work"
    example: "Developer → Reviewer → Approver"
```

### Handoff Protocols
```yaml
handoff_protocol:
  trigger_conditions:
    - "Task requires expertise outside current domain"
    - "Complexity exceeds single-agent capacity"
    - "Multi-domain solution needed"
    
  handoff_format:
    summary: "What has been completed"
    context: "Relevant findings and decisions"
    recommendation: "Suggested next agent and approach"
    artifacts: "Files modified or created"
    
  recommended_sequences:
    - sequence: "Design → Implement → Test → Deploy"
      agents: [architect, developer, qa-tester, devops]
    - sequence: "Analyze → Secure → Optimize"
      agents: [analyzer, security, performance]
```

## Anti-Patterns and Common Pitfalls

### Design Anti-Patterns
1. **Jack-of-All-Trades Agent**
   - Problem: Agent tries to do everything
   - Solution: Focus on single, clear responsibility
   - Example: Avoid "full-stack-everything-agent"

2. **Overlapping Responsibilities**
   - Problem: Multiple agents with same capabilities
   - Solution: Clear differentiation and boundaries
   - Example: Frontend vs. UI designer roles

3. **Tool Permission Bloat**
   - Problem: Agent has unnecessary permissions
   - Solution: Grant minimum required tools
   - Example: Read-only analyst shouldn't have Write

### Implementation Pitfalls
1. **Context Window Explosion**
   - Symptom: Agent reads entire codebase
   - Fix: Implement selective reading strategies
   
2. **Infinite Loop Behavior**
   - Symptom: Agent repeats same actions
   - Fix: Add termination conditions and state tracking
   
3. **Over-Engineering Responses**
   - Symptom: Simple tasks get complex solutions
   - Fix: Match solution complexity to problem

### Edge Case Handling
```yaml
edge_cases:
  - case: "Empty or Missing Files"
    detection: "File not found or zero bytes"
    response: "Graceful handling with clear message"
    
  - case: "Huge Files or Directories"
    detection: ">10MB files or >1000 files"
    response: "Implement pagination or sampling"
    
  - case: "Conflicting Requirements"
    detection: "Mutually exclusive constraints"
    response: "Clarify priorities with user"
    
  - case: "Insufficient Permissions"
    detection: "Tool access denied"
    response: "Work within constraints or escalate"
```

## Success Metrics and KPIs

### Quantitative Metrics
```yaml
quantitative_kpis:
  efficiency:
    - metric: "Task Completion Time"
      target: "50% faster than baseline"
      measurement: "Average time per task type"
      
    - metric: "First-Time Success Rate"
      target: "90%+ without revision"
      measurement: "Tasks completed without rework"
      
  quality:
    - metric: "Code Quality Score"
      target: "Maintain or improve baseline"
      measurement: "Linting, complexity metrics"
      
    - metric: "Test Coverage"
      target: "≥80% for new code"
      measurement: "Coverage reports"
      
  reliability:
    - metric: "Error Rate"
      target: "<5% task failures"
      measurement: "Failed vs. successful tasks"
```

### Qualitative Metrics
```yaml
qualitative_kpis:
  user_satisfaction:
    - metric: "Ease of Use"
      measurement: "User feedback surveys"
      target: "4.5+ / 5.0 rating"
      
    - metric: "Clear Communication"
      measurement: "Clarity ratings"
      target: "Rarely requires clarification"
      
  developer_experience:
    - metric: "Integration Smoothness"
      measurement: "Developer feedback"
      target: "Seamless workflow integration"
      
    - metric: "Learning Curve"
      measurement: "Time to proficiency"
      target: "Productive within first session"
```

## Example Implementation

### Complete Agent Example: Code Security Analyst
```yaml
---
name: security-vulnerability-analyst
type: claude-code-subagent
version: 1.0.0
description: |
  Specialized security analyst for identifying vulnerabilities,
  implementing secure coding practices, and ensuring compliance
  with security standards. Use for security audits, threat
  modeling, and secure code reviews.
color: "#FF4444"
tools:
  - Read
  - Grep
  - Glob
  - Edit
  - MultiEdit
  - WebSearch
  - TodoWrite
created: 2024-01-20
author: security-team
tags: [security, audit, compliance, vulnerability]
---

You are a security vulnerability analyst specializing in threat modeling, secure coding practices, and compliance standards. Your approach: security-first analysis with OWASP Top 10, SANS guidelines. You prioritize identifying vulnerabilities, implementing fixes, and preventing future issues. You validate using static analysis, penetration testing patterns, and security benchmarks. Success means zero critical vulnerabilities and robust security posture.
```

### Usage Example
```typescript
// Task delegation to security analyst
const securityTask = {
  agent: "security-vulnerability-analyst",
  task: "Audit authentication system for vulnerabilities",
  context: {
    files: ["src/auth/**/*.ts", "src/middleware/auth.ts"],
    standards: ["OWASP Top 10", "SOC 2 compliance"],
    priority: "critical"
  },
  expectedOutcomes: [
    "Vulnerability report with severity ratings",
    "Remediation recommendations",
    "Secure code implementations",
    "Compliance checklist"
  ]
};
```

## Template Usage Guide

### Step-by-Step Implementation
1. **Define Your Domain**: Start with clear domain boundaries
2. **Identify Core Competencies**: List 5-7 key capabilities
3. **Design Behavioral Patterns**: Map out decision flows
4. **Craft System Prompt**: Follow the structured pattern
5. **Define Test Scenarios**: Create comprehensive test cases
6. **Implement Quality Gates**: Set measurable standards
7. **Document Integration Points**: Define collaboration patterns
8. **Validate and Iterate**: Test with real-world scenarios

### Customization Checklist
- [ ] Replace all placeholder text with domain-specific content
- [ ] Adjust tool permissions to match agent needs
- [ ] Customize quality gates for your domain
- [ ] Define specific test scenarios
- [ ] Set appropriate performance targets
- [ ] Document unique edge cases
- [ ] Create integration examples

### Best Practices
1. **Start Focused**: Better to excel in narrow domain than be mediocre broadly
2. **Evidence-Based**: Always provide reasoning and validation
3. **User-Centric**: Design for developer experience
4. **Performance-Conscious**: Optimize for speed and efficiency
5. **Security-Aware**: Consider security implications
6. **Maintainable**: Document clearly for future updates
7. **Testable**: Include comprehensive test coverage

This template provides the foundation for creating world-class Claude Code subagents that deliver exceptional value through specialized expertise and consistent quality.
