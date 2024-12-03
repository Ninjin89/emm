# Log Behavior by Log Level

| **Log Level** | **Logged Levels**          | **Explanation**                                                                                              |
|---------------|----------------------------|--------------------------------------------------------------------------------------------------------------|
| **1 (Critical)** | 1                        | Only critical logs (`LogCritical`) will be logged.                                                          |
| **2 (Warning)**  | 1, 2                    | Critical and warning logs (`LogCritical`, `LogWarning`) will be logged.                                     |
| **3 (Info)**     | 1, 2, 3                | Critical, warning, and informational logs (`LogCritical`, `LogWarning`, `LogInfo`) will be logged.          |
| **4 (Debug)**    | 1, 2, 3, 4             | Critical, warning, informational, and debug logs (`LogCritical`, `LogWarning`, `LogInfo`, `LogDebug`) will be logged. |
| **5 (Kill/Damage)** | 2, 5                | **Only** warnings (`LogWarning`) and Kill/Damage logs (`LogKillsDamage`) will be logged explicitly.          |

---

## Log Level Definitions

1. **Critical** (`LogCritical`): Logs severe events requiring immediate attention.
2. **Warning** (`LogWarning`): Logs potentially harmful situations or warnings.
3. **Info** (`LogInfo`): Logs general informational messages about normal operations.
4. **Debug** (`LogDebug`): Logs detailed debugging messages for developers.
5. **Kill/Damage** (`LogKillsDamage`): Logs specific events related to kills or damage in the system.
