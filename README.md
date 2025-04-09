# Log Behavior by Log Level

| **Log Level**   | **Logged Levels**             | **Explanation**                                                                                             |
|------------------|-------------------------------|-------------------------------------------------------------------------------------------------------------|
| **0 (Nothing)** | 0                             | Nothing will be logged and no logfile will be generated.                                                      |
| **1 (Critical)** | 1                             | Only critical logs (`LogCritical`) will be logged.                                                         |
| **2 (Warning)**  | 1, 2                         | Critical and warning logs (`LogCritical`, `LogWarning`) will be logged.                                    |
| **3 (Info)**     | 1, 2, 3                     | Critical, warning, and informational logs (`LogCritical`, `LogWarning`, `LogInfo`) will be logged.         |
| **4 (Debug)**    | 1, 2, 3, 4                  | Critical, warning, informational, and debug logs (`LogCritical`, `LogWarning`, `LogInfo`, `LogDebug`) will be logged. |
| **5 (Kill/Damage)** | 2, 5                     | **Only** warnings (`LogWarning`) and Kill/Damage logs (`LogKillsDamage`) will be logged explicitly.         |
| **6 (Everything)** | 1, 2, 3, 4, 5, 6          | **All logs** at all levels (`LogCritical`, `LogWarning`, `LogInfo`, `LogDebug`, `LogKillsDamage`, `LogEverything`) will be logged. |

---

## Log Level Definitions
0. **Nothing** (`LogCritical`): No logs will be generated at all and also no logfiles.
1. **Critical** (`LogCritical`): Logs severe events requiring immediate attention.
2. **Warning** (`LogWarning`): Logs potentially harmful situations or warnings.
3. **Info** (`LogInfo`): Logs general informational messages about normal operations.
4. **Debug** (`LogDebug`): Logs detailed debugging messages for developers.
5. **Kill/Damage** (`LogKillsDamage`): Logs specific events related to kills or damage in the system.
6. **Everything** (`LogEverything`): Logs everything, regardless of level.

---

## Special Cases

### Log Level 5 (Kill/Damage)
When `LogLevel` is set to **5**, the logger explicitly behaves as follows:
- Logs **Warnings** (`LogWarning`) with a log level of **2**.
- Logs **Kill/Damage** (`LogKillsDamage`) with a log level of **5**.
- **All other log levels** (1, 3, 4) are **ignored**.

### Log Level 6 (Everything)
When `LogLevel` is set to **6**, the logger explicitly behaves as follows:
- Logs **everything**, regardless of log level.

---

# Examples

## Log Level = 1 (Critical)
- **LogCritical("Critical event.")** → Logged
- **LogWarning("Potential issue.")** → Not logged
- **LogInfo("System running smoothly.")** → Not logged
- **LogDebug("Detailed debug information.")** → Not logged
- **LogKillsDamage("Kill/Damage event.")** → Not logged
- **LogEverything("Log all events.")** → Not logged

## Log Level = 3 (Info)
- **LogCritical("Critical event.")** → Logged
- **LogWarning("Potential issue.")** → Logged
- **LogInfo("System running smoothly.")** → Logged
- **LogDebug("Detailed debug information.")** → Not logged
- **LogKillsDamage("Kill/Damage event.")** → Not logged
- **LogEverything("Log all events.")** → Not logged

## Log Level = 5 (Kill/Damage)
- **LogCritical("Critical event.")** → Not logged
- **LogWarning("Potential issue.")** → Logged
- **LogInfo("System running smoothly.")** → Not logged
- **LogDebug("Detailed debug information.")** → Not logged
- **LogKillsDamage("Kill/Damage event.")** → Logged
- **LogEverything("Log all events.")** → Not logged

## Log Level = 6 (Everything)
- **LogCritical("Critical event.")** → Logged
- **LogWarning("Potential issue.")** → Logged
- **LogInfo("System running smoothly.")** → Logged
- **LogDebug("Detailed debug information.")** → Logged
- **LogKillsDamage("Kill/Damage event.")** → Logged
- **LogEverything("Log all events.")** → Logged
