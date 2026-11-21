# Sanitized Defect Reports

Representative defects identified during testing using **Charles Proxy** network inspection to separate client rendering/caching issues from backend service and data consistency discrepancies[cite: 11].

---

## BUG-006: Upsell entry remains clickable when time-slot inventory reaches to 0

- **Severity:** High[cite: 11]
- **Status:** Closed[cite: 11]
- **Steps to Reproduce:**
  1. Set slot inventory to `1` in Admin UI[cite: 11].
  2. Complete purchase on Device A[cite: 11].
  3. Refresh PDP on Device B and tap Upsell banner[cite: 11].
- **Root Cause & Resolution:**
  - **Ownership:** Frontend H5 Cache[cite: 11]
  - **Fix:** Updated the client component to bind button state directly to the live availability payload and render a `"Sold Out"` badge when inventory reaches zero[cite: 11].

---

## BUG-009: The original time-slot inventory not released after date change to other time

- **Severity:** High[cite: 11]
- **Status:** Closed[cite: 11]
- **Steps to Reproduce:**
  1. Book a fastpass for the first available day[cite: 11].
  2. Reschedule the fastpass to another available day via Date Change flow[cite: 11].
  3. Check the inventory of the first available day in Admin Portal[cite: 11].
- **Root Cause & Resolution:**
  - **Ownership:** Backend Order Service[cite: 11]
  - **Fix:** Added transactional release of the original time-slot inventory after successful date-change confirmation[cite: 11].
