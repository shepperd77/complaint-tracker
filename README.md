# Manufacturing Complaint Tracker

A portfolio project reconstructing an Excel-based manufacturing complaint workflow and developing it into a relational database-backed system.

## Project Overview

The project is based on a real-world manufacturing process for handling customer complaints involving individual parts, quality checks, repair decisions, quotations, production, and outbound logistics.

The original workflow was managed in Excel. The objective is to reconstruct the existing process, model its business rules, and gradually transform it into a structured, maintainable application.

The project is developed in stages, with each version building on the previous one.

## Development Roadmap

### V1 — Excel Workflow Reconstruction

**Status: Completed**

Reconstructed and documented the original Excel-based complaint workflow.

The reconstruction covers:
- Workflow checkpoints and departmental responsibilities
- Conditional formatting and visual process indicators
- Identification of the next pending action
- The original process structure and its practical limitations

This version provides the reference for subsequent development.

### V2 — Workflow Analysis and Business Rules

**Status: Requirements established**

Analyzed the underlying manufacturing process to identify its entities, relationships, conditional branches, and operational requirements.

Key areas include:
- Customer and part identification
- Claims containing multiple individual part lines
- Repair eligibility and customer quotation decisions
- Departmental responsibilities
- Workflow deadlines and conditional steps
- Return without repair and claim completion

The objective is to preserve the existing business logic while separating process requirements from the limitations of the original spreadsheet.

### V3 — SQL Schema Design

**Status: Design completed**

Designed the initial relational database structure for the complaint-tracking system.

The design establishes:
- Tables and their responsibilities
- Primary keys and foreign-key relationships
- Data types and field constraints
- Reference tables for controlled values
- Relationships between customers, claims, claim lines, and supporting records
- Conditional workflow requirements for the repair process

#### Key design decision: Claims vs. Claim Lines

A claim represents the overall customer complaint. Each claim line represents an individual part moving through the repair workflow.

This distinction allows a single claim to contain multiple parts while tracking their repair progress independently.

The design also accounts for composite primary keys, allowing line numbers to be unique within their respective claims rather than across the entire database.

### V4 — PostgreSQL Implementation and Validation

**Status: Next phase**

Implement the designed schema in PostgreSQL and validate it using representative test data.

Planned work:
- Create tables and reference data
- Implement primary keys, foreign keys, and constraints
- Test relationships and multi-line claims
- Validate conditional repair workflows
- Test deadline calculations and status handling
- Refine the schema based on concrete test results

### V5 — Application Development

**Status: Planned**

Develop an application interface on top of the database.

The aim is to make the complaint workflow usable without relying on the original spreadsheet, while preserving the underlying manufacturing process and its business rules.

The implementation approach will be determined as the database foundation develops.

## Technology Stack

- **Excel** — original workflow reconstruction and schema planning
- **PostgreSQL** — planned relational database implementation
- **SQL** — schema definition, relationships, queries, and validation
- **Application technologies** — to be determined during the application development phase

## Current Status

The project has progressed from reconstructing the original spreadsheet to completing the initial SQL schema design.

The next milestone is implementing that design in PostgreSQL and testing it against realistic manufacturing complaint scenarios.

This is an iterative project: design decisions will be revisited when testing identifies concrete issues, rather than attempting to anticipate every possible requirement before implementation begins.
