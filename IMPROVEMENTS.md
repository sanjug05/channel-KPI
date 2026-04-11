# test-dashboard: Improvement Backlog (Environment + End-user Utility)

## Critical (Do first)
1. **Move authentication to Firebase Auth or a backend**
   - Remove hardcoded credentials from frontend code.
   - Enforce role checks via backend/Firestore rules, not only UI visibility.
2. **Harden Firestore security rules**
   - Restrict write/delete to admin role claims.
   - Allow viewer accounts as read-only.
3. **Improve session security**
   - Replace role-only sessionStorage auth with signed ID token validation.

## Reliability
1. Add global error boundary/toast fallback for failed Firestore reads/writes.
2. Queue offline changes and sync when network restores.
3. Add schema versioning for showroom/dealer records.

## Performance
1. Add pagination/virtualized rendering for dealers and showrooms.
2. Debounce search/filter handlers.
3. Load heavy libraries (XLSX/jsPDF/html2canvas) on demand.

## UX / End-user Utility
1. Add saved filters and personalized dashboard presets.
2. Add SLA alerts (e.g., "7+ day delay", "missing docs > 3 days").
3. Add RM-wise weekly digest export and email scheduling.
4. Add timeline view (Gantt-like) for showroom phase slippage.
5. Add in-app onboarding tooltips and glossary for stage terms.

## Data quality / governance
1. Validate dealer fields (city, rm, date) with stricter rules.
2. Add duplicate detection (name+city similarity check).
3. Add audit drill-down screen with diff (before/after values).

## Engineering maintainability
1. Split single-file app into modules (auth, firestore, rendering, analytics).
2. Replace inline `onclick` handlers with delegated listeners.
3. Add linting/formatting + CI checks.
4. Add unit tests for timeline/delay calculations.
