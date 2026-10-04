# EnergyPulse Engineering Decisions

## ADR-001: Medallion Architecture

### Decision

EnergyPulse will use Bronze, Silver, and Gold data layers.

### Reason

The architecture separates raw source data from processed and business-ready datasets.

Benefits:

- Easier debugging
- Reprocessing capability
- Clear data ownership
- Better lineage
- Separation of concerns

---

## ADR-002: AWS S3 for Data Lake

### Decision

AWS S3 will be used as the primary data lake storage layer.

### Reason

S3 provides scalable and durable object storage and integrates well with the AWS data ecosystem.

---

## ADR-003: Apache Airflow for Orchestration

### Decision

Apache Airflow will orchestrate the EnergyPulse pipelines.

### Reason

Airflow provides:

- DAG-based workflows
- Scheduling
- Retry handling
- Dependency management
- Backfills
- Operational visibility

---

## ADR-004: PySpark for Data Processing

### Decision

PySpark will be used for large-scale data processing.

### Reason

PySpark demonstrates distributed processing capabilities and provides a scalable processing framework.

---

## ADR-005: dbt for Analytical Transformation

### Decision

dbt will be used for SQL-based transformation and analytical modeling.

### Reason

dbt provides:

- Modular SQL transformations
- Testing
- Documentation
- Lineage
- Version-controlled analytics engineering