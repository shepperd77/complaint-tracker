# Complaint Tracker

Manufacturing complaint workflow tracker – V1 reconstruction and V2 data model.

## Project

This project reconstructs a real-world manufacturing complaint workflow originally implemented in Excel.

The original tracker has been used in a production environment for approximately one year. The project documents the original workflow, reverse-engineers its business logic, and uses that knowledge as the foundation for a database-backed V2.

The project uses anonymized data and contains no real customer, complaint, part-number or serial-number data.

## V1 – Original Workflow

The original tracker uses:

* one row per complaint
* process checkpoints represented by columns
* responsible department assigned to each checkpoint
* automatic workflow status using `IFS`
* conditional formatting to visualize progress
* `AKCE u` to identify the current responsible department
* filtering by `AKCE u` to create working queues for each department

### Workflow visualization

* **White** – complaint has not been started
* **Green** – completed checkpoint
* **Red** – current checkpoint / next required action
* **Completed** – all checkpoints finished

The V1 reconstruction focuses on reproducing the original process before redesigning it.

## V2 – Data Model & Workflow Logic

V2 moves from spreadsheet-based workflow tracking toward a structured relational data model.

The V2 specification defines:

* data types and field constraints
* controlled lists and reference tables
* mandatory and conditionally mandatory fields
* nullable fields for skipped workflow branches
* derived values and deadlines
* workflow branching and applicability rules
* separation of stored facts from derived workflow state

A key change from V1 is the workflow logic:

> **V1:** the first empty checkpoint is the current action.

> **V2:** the first applicable checkpoint that has not been completed is the current action.

This allows the workflow to handle conditional branches without treating intentionally skipped fields as incomplete work.

## Planned Architecture

**V1**
Excel workflow → reconstruction and documentation

**V2**
PostgreSQL → structured data model and workflow logic

**V3**
Application / user interface → interaction with the database

The database schema will be implemented only after the V2 process and data model have been fully specified.

## Project Status

### Completed

* V1 workflow reverse engineering
* V1 workflow reconstruction
* Workflow checkpoints and department ownership mapped
* V1 status logic documented
* V2 data dictionary created
* V2 mandatory, conditional and derived field rules defined
* V2 workflow branching logic defined

### Next

* PostgreSQL schema design
* Reference tables
* Workflow definition
* Sample anonymized data
* Database implementation

## Repository Structure

```text
complaint-tracker/
├── README.md
├── complaint-tracker-v1-template.xlsx
└── ...
```
