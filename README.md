# Complaint Tracker

Manufacturing complaint workflow tracker – V1 reconstruction.

## Project

This project reconstructs a real-world manufacturing complaint workflow originally implemented in Excel.

The original system has been used in a production environment for approximately one year. The goal of this project is to rebuild its functionality in Google Sheets as V1, document the workflow, and later use the experience as the foundation for a database-backed V2.

## V1 – Original Workflow

The original tracker uses:

- one row per complaint
- process checkpoints represented by columns
- responsible department assigned to each checkpoint
- automatic workflow status using `IFS`
- conditional formatting to visualize progress
- `AKCE u` to identify the current responsible department
- filtering by `AKCE u` to create a working queue for each department

### Workflow visualization

- **White** – complaint has not been started
- **Green** – completed checkpoint
- **Red** – current checkpoint / next required action
- **Completed** – all checkpoints finished

## Departments

| Short | Department |
|---|---|
| CS1 | Customer Service – initial step |
| CS | Customer Service |
| PROD | Production |
| QA | Quality |
| ENG | Engineering |
| PM | Project Management |
| LOG | Logistics |

## V1 Reconstruction

The first version of this project will recreate the original workflow in Google Sheets.

The objective is not to redesign the process immediately, but to reproduce the working logic first.

## Future Development

Potential future direction:

**V1**
→ Google Sheets reconstruction

**V2**
→ PostgreSQL database

**V3**
→ Application / user interface

The database and application architecture will be designed after the original workflow has been fully reconstructed and understood.

## Project Status

**Day 1 – Workflow reverse engineering completed**

The original workflow, responsible departments, status logic, conditional formatting and filtering principle have been mapped.
