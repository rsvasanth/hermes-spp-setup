# SPP Engineering Standards & Principles

All agents working on the SPP Porting Project must adhere to these core technical standards:

## 1. Idempotency First
Every synchronization operation must be designed to be idempotent. Agents must check for existing records using unique composite keys before attempting creation to prevent duplicate legacy documents.

## 2. Event-Driven Sync Lifecycle
Standardize all sync status propagation through the `apply_bridge_result` document method. Avoid direct database updates (`frappe.db.set_value`) in favor of document-level methods that trigger appropriate side effects and logging.

## 3. Atomic Cross-System Transactions
Ensure that document submissions (`doc.submit()`) are handled atomically. If a sync fails at any point in the multi-system chain, the transaction log must accurately reflect the failure state for reliable retries.

## 4. Zero-Defect Verification
A task is not "Done" until:
- Unit tests pass for the specific logic.
- A manual or automated UI check confirms visibility in the Console.
- Database logs verify that data reached the Legacy Bridge without discrepancy.

## 5. Security & Redaction
Adhere to the "Tenacity Release" security standards. Sensitive authentication data must remain redacted in logs and shared debug sessions.
