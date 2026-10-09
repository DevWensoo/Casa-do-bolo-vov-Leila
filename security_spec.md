# Security Specification for Casa de Bolo Vovó Leila

## 1. Data Invariants
- An Order must contain a valid `storeId`, customer name, valid phone number, positive `total`, and a legitimate `status`.
- Customers can create new orders (`novos` or `preparo`), but cannot delete orders or falsify admin flags.
- Store inventory availability can only be toggled with valid numeric counts.
- Stores metadata contains valid fields, numbers, and phone formatting.

## 2. Dirty Dozen Payloads (Negative Security Cases)
1. Order with negative total price (`total: -50.00`) -> REJECT.
2. Order with oversized customer name (> 100 characters) -> REJECT.
3. Order with invalid status (e.g. `status: "hacked"`) -> REJECT.
4. Order modifying an immutable creation timestamp -> REJECT.
5. Deletion of an existing order by unauthorized client -> REJECT.
6. Store entry with oversized name (> 100 chars) -> REJECT.
7. Injection of arbitrary fields outside blueprint schema into Store -> REJECT.
8. StoreInventory with negative stockCount -> REJECT.
9. SystemSettings modification without master credentials -> REJECT.
10. Cake price set to negative value -> REJECT.
11. Path variable poisoning with malformed IDs -> REJECT.
12. Order with non-existent store target ID -> REJECT.
