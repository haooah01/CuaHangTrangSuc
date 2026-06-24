# Enterprise Test Suite Plan

## Objective

Turn the current jewelry retail business prototype into a customer-verifiable enterprise prototype by making the test strategy visible.

## Test Scope

| Layer | Target |
|---|---|
| Model tests | Validate invoices, products, counters, staff, promotions, loyalty points, buy-back records |
| View tests | Validate route access, form submission, redirect behavior, and error handling |
| Security tests | Validate authentication, CSRF protection, protected admin/staff actions, and invalid input handling |
| Migration tests | Validate committed migrations and clean schema creation in CI |
| Integration tests | Validate complete sales-counter flow from product selection to invoice output |

## Minimal Business Tests

1. Create customer.
2. Create staff.
3. Create product.
4. Assign product to counter.
5. Create invoice.
6. Create invoice detail.
7. Add promotion.
8. Add customer loyalty points.
9. Create buy-back record.
10. Assert model relations stay consistent.

## CI Proof

The workflow `.github/workflows/enterprise-ci.yml` should run:

1. Dependency installation.
2. `python manage.py check`.
3. `python manage.py makemigrations --check --dry-run`.
4. `python manage.py migrate --noinput`.
5. `python manage.py test --noinput`.

## Customer-Facing Evidence

A passing CI badge, screenshots of test results, and a short demo should be added to the README after the first successful pipeline run.
