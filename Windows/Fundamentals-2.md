  ### System Configuration

- `MSConfig` is the window's system configuration ultility. It is for advanced troubleshooting [Window's Documentation](https://learn.microsoft.com/en-us/troubleshoot/windows-client/performance/system-configuration-utility-troubleshoot-configuration-errors)
- Requires admin rights

![image](https://github.com/user-attachments/assets/e4ce2f67-2a7c-46e9-92be-ee5d61a584c4)

  - General:
    - Use `Normal Startup` when no troubleshooting is needed.
    - Use `Diagnostic Startup` to check for hardware or core OS problems.
    - Use `Selective Startup` to identify problematic third-party software or drivers.

  - Boot: Might be similar to BIOS/UEFI but they serve different purposes
    - Inside msconfig:
      - controls how windows behaves AFTER hardware initialization
    - Inside BIOS/UEFI:
      - configures hardware-level settings like booting options from DVD/USB etc...
  - Services:
    - Lists all services configured for the system regardless of their state (running or stopped)
    - service: an application that runs in the background
  - Startup: use task manager instead (enable/disable) startup programs
  - Tools: configure the OS further

### Computer Management

- `compmgmt` is the utility

![image](https://github.com/user-attachments/assets/bf0068b9-ee19-4df1-9129-79b6b54c2b69)


- System Tools:
  - Task Scheduler: create and manage common tasks that our computer will carry out automatically at the times we specifiy.
    - Support event-based triggers (user login)
    - not the same as cron on unix systems but similar
  - Event Viewer: 











