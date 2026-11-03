# Database validation plan — SifoBoarding

Status: schema draft only; not applied to any database.

## Required before production
- Apply migrations to a disposable Supabase/PostgreSQL project first.
- Create two companies/users and verify tenant isolation across students, rooms, allocations, and fees.
- Add overlap checks so a student/bed cannot have conflicting active allocations; validate capacity.
- Ensure company_id and branch_id agree across linked records.
- Test fee/payment accounting and status transitions server-side.
- Verify staff roles cannot manage company membership; only owner/admin can.
- Confirm audit events are append-only and capture actor, action, and record identity.
- Review RLS policy recursion, SECURITY DEFINER function ownership/search_path, and privilege grants.
- Add automated SQL migration tests before marking this PR ready.
