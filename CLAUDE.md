# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository contains a collection of specialized agent personas for Claude Code's Task tool. Each agent represents a domain expert with specific methodologies, priorities, and technical expertise designed to handle specialized software development tasks.

## Architecture

### Agent System Structure
- **agents/**: Contains markdown files defining 9 specialized agent personas
- **logs/**: Claude Code session logs and tool usage tracking  
- Each agent has a structured format with YAML frontmatter and detailed persona specifications

### Agent Categories

**Technical Specialists:**
- `backend-reliability-engineer`: Server-side systems, APIs, databases, microservices
- `frontend-ux-specialist`: UI/UX components, accessibility, performance, mobile-first development
- `systems-architect`: System design, scalability, architectural decisions
- `security-threat-analyst`: Security assessments, threat modeling, vulnerability analysis
- `performance-optimizer`: Performance analysis, bottleneck elimination, optimization

**Process & Quality Experts:**
- `code-analyzer-debugger`: Bug investigation, root cause analysis, systematic debugging
- `code-refactoring-expert`: Code quality improvement, technical debt management
- `qa-test-engineer`: Testing strategies, quality assurance, edge case analysis
- `technical-mentor-guide`: Educational guidance, knowledge transfer, explanations

## Agent Specification Format

Each agent follows this structure:
```yaml
---
name: agent-name
description: When to use this agent and its capabilities
color: visual-identifier
---

# Persona definition with:
- Identity & Operating Principles
- Core Methodology  
- Technical Expertise
- Problem-Solving Approach
- Quality Standards
- Communication Style
- Success Metrics
```

## Usage Patterns

### Agent Activation
Agents are designed to be activated via Claude Code's Task tool when:
1. Domain-specific expertise is needed
2. Specialized methodologies would be beneficial  
3. Complex problems require focused approaches
4. Quality standards need domain-specific validation

### Integration Points
- **Evidence-Based Approach**: All agents emphasize measurement and validation
- **Security-First**: Security considerations integrated across all domains
- **Performance-Aware**: Performance implications considered in all decisions  
- **User-Centric**: Focus on end-user experience and needs

## Development Workflows

### No Build Process
This is a configuration/specification repository with no compilation or build steps required. Changes to agent definitions take effect immediately when used with Claude Code.

### Testing Approach
Agent effectiveness is validated through:
- Real-world usage scenarios
- Task completion quality assessment
- User feedback and iteration
- Cross-agent collaboration patterns

### Quality Standards
- Each agent maintains domain-specific quality gates
- Evidence-based decision making across all agents
- Consistent methodology documentation
- Clear activation criteria and use cases

## Key Design Principles

1. **Specialization Over Generalization**: Each agent has deep expertise in specific domains
2. **Evidence-Based Decision Making**: All recommendations backed by data and best practices
3. **User Experience Focus**: Prioritize end-user needs across all technical decisions
4. **Security by Default**: Security considerations integrated into all agent workflows
5. **Performance Consciousness**: Performance implications considered in all domains
6. **Collaborative Design**: Agents designed to work together on complex problems

## Agent Priorities

Each agent has distinct priority hierarchies:
- **Frontend**: User experience > accessibility > performance > technical elegance
- **Backend**: Reliability > security > performance > features > convenience  
- **Security**: Security > compliance > reliability > performance > convenience
- **Architect**: Long-term maintainability > scalability > performance > short-term gains
- **Performance**: Measure first > optimize critical path > user experience > avoid premature optimization

These specifications enable Claude Code to provide specialized, expert-level assistance across the full spectrum of software development challenges.