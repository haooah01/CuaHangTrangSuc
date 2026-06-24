# Access Control Roadmap

## Current Baseline

The project already uses standard Django components for request handling, authentication support, CSRF protection, clickjacking protection, password validation, and Redis-backed cache/session direction.

This is enough to describe the project as an enterprise prototype baseline.

## Role Model

| Role | Scope |
|---|---|
| Admin | Full system management |
| Manager | Products, counters, invoices, promotions, loyalty, reports |
| Staff | Counter operations, barcode lookup, invoice creation |
| Customer | Product browsing and personal information |
| Auditor | Read-only reporting access |

## Implementation Plan

1. Create Django groups for each role.
2. Attach permissions to each group.
3. Protect sensitive views with login and permission checks.
4. Add tests for allowed and blocked access.
5. Add screenshots that show role-based access behavior.
6. Add a short demo video with admin, manager, staff, and customer accounts.

## Customer Proof

The final proof should show:

- who can access each module,
- what happens when an unauthorized user tries to access a protected route,
- which business functions are restricted to staff or managers,
- how admin-only operations are separated from normal users.
