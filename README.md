# Dialysis Center Operations Suite

Dialysis scheduling, adequacy tracking, vascular access surveillance, compliance, inventory, and care-team coordination.

**Buyer:** Dialysis providers, nephrology groups, renal care operators

## Run

```bash
cd /Users/erolakarsu/external/projects/dialysis-center-operations-suite
./start.sh
```

Open:

```text
http://127.0.0.1:5602
```

## Demo Logins

```text
admin@dialysis-center-operations-suite.local / admin123
manager@dialysis-center-operations-suite.local / manager123
analyst@dialysis-center-operations-suite.local / analyst123
```

## Implemented Features

- Sidebar dashboard and module navigation
- Domain-specific workspaces: Chair Schedule, Treatment Runs, Vascular Access, Renal Labs, Medication Protocols, Dialysis Inventory, CMS Compliance, Care Plans
- Seeded persistent data with 15 records per domain module
- Login, roles, local persistent JSON store
- Create, edit, delete records
- Document metadata upload workflow
- Tasks, notifications, audit logs
- CSV exports for every table
- AI Center with OpenRouter-ready endpoint and local fallback
- Reports and print-ready summaries
- Smoke test for health, login, CRUD, and export

## Test

```bash
npm test
```

For production, replace demo auth with an identity provider, replace local JSON with a database, add durable file storage, and validate AI workflows against your compliance requirements.


## Production-Style Feature Upgrade

Added across the full 20-app batch:

- API-enforced RBAC sessions for Admin, Manager, and Analyst roles
- Authorization checks for write, delete, export, AI, admin, and job endpoints
- Optimistic record versioning with conflict protection
- Server-side validation for required operational fields
- Rules-based risk scoring per record and module-level domain analysis
- Integrations, automations, approvals, tasks, notifications, documents, and audit logs
- Due-notification scheduled job endpoint plus hourly runtime scheduler
- Backup, restore, and reset endpoints
- Readiness endpoint with deployment checks
- Security response headers for API/static responses
- Expanded smoke tests covering RBAC, versioned CRUD, backup, jobs, domain analysis, and export
