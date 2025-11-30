# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Claude Code agents repository containing specialized agent definitions for software development tasks. Each agent is defined in a markdown file with YAML frontmatter specifying its capabilities, model, and tools.

## Agent Architecture

The repository contains seven specialized agents that work together in a comprehensive development workflow:

### Core Agent Types

1. **code-analyzer** (`code-analyzer.md`) - Purple agent using Read, Grep, Glob, Bash tools
   - Analyzes code quality, performance, and adherence to project standards
   - Focuses on Go development patterns, security vulnerabilities, and maintainability
   - Reviews architecture compliance with event-driven patterns and clean code principles

2. **problem-analyzer-planner** (`problem-analyzer-planner.md`) - Cyan agent with full tool access
   - Breaks down complex problems into implementation plans
   - Performs technical architecture analysis and solution design
   - Identifies dependencies, risks, and creates detailed task breakdowns

3. **task-planner-implementer** (`task-planner-implementer.md`) - Blue agent with full tool access
   - Combines planning with hands-on implementation
   - Follows Agentic Coding Development Guidelines
   - Specializes in Go development with event-driven orchestrator architecture

4. **code-reviewer** (`code-reviewer.md`) - Orange agent with full tool access  
   - Provides comprehensive code reviews for quality, security, and maintainability
   - Conducts post-implementation reviews with structured analysis
   - Covers both Go backend and React frontend review patterns

5. **task-executor** (`task-executor.md`) - Green agent with full tool access
   - Coordinates sequential execution of multiple tasks
   - Delegates individual tasks to task-planner-implementer
   - Maintains completion tracking and progress reporting

### Git Operations Agents

6. **pr-generator** (`pr-generator.md`) - Green agent with full tool access
   - Creates properly formatted GitHub pull requests with Japanese conventions
   - Analyzes commit history to generate appropriate PR titles and descriptions
   - Follows structured formatting with draft status and review checkboxes

7. **commit-message-generator** (`commit-message-generator.md`) - Blue agent with full tool access
   - Generates structured commit messages following Japanese conventions
   - Analyzes git diff and status to create contextual commit messages
   - Ensures proper type categorization and detailed body content

### Agent Workflow Patterns

The agents are designed to work in complementary workflows:
- **Analysis Phase**: problem-analyzer-planner → task-planner-implementer
- **Implementation Phase**: task-planner-implementer → code-reviewer
- **Multi-task Coordination**: task-executor → task-planner-implementer (repeated)
- **Quality Assurance**: code-analyzer (ongoing)
- **Git Operations**: commit-message-generator → pr-generator

## Project Context Awareness

All agents are configured with awareness of:
- **Go Development Standards**: Using github.com/cockroachdb/errors for error handling, testify for testing
- **Architecture Patterns**: Event-driven orchestrator patterns, dependency injection, interface usage  
- **Database Patterns**: PostgreSQL with SQLC, proper naming conventions (snake_case, plural tables)
- **Code Quality**: English-only code and comments, minimal but necessary documentation
- **Testing Strategy**: Unit, integration, and E2E test coverage with proper mocking patterns

## Usage Guidelines

- Each agent specializes in specific development phases - use the appropriate agent for the task type
- Agents reference project-specific patterns from CLAUDE.md files when available
- All agents follow structured output formats for consistency
- Quality gates and review processes are built into the agent workflow
- Task tracking and dependency management are handled systematically

## Development Workflow

The agents support a complete development lifecycle:
1. Problem analysis and planning (problem-analyzer-planner)
2. Task breakdown and implementation (task-planner-implementer)  
3. Quality review and feedback (code-reviewer)
4. Ongoing code analysis (code-analyzer)
5. Multi-task coordination (task-executor)
6. Commit message generation (commit-message-generator)
7. Pull request creation (pr-generator)

This agent ecosystem enables systematic, high-quality software development with built-in quality assurance and architectural consistency.