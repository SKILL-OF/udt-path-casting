# UDT Path Casting Safety

Safe patterns for universal data type path operations:

## 1. Path Validation
Before using path: verify format is valid, contains no escapes, is scoped correctly.

## 2. Atomic Operations
Path casting is atomic: input path → output type. Never partial conversions.

## 3. Type Safety
Verify target type is compatible before casting. Fail fast on type mismatch.

## 4. Scope Containment
Casted paths never escape declared scope. Root jail is enforced.

## 5. Audit Trail
Record: source path, target type, cast result, verification status.

**Enables safe type casting in agent path systems.**
