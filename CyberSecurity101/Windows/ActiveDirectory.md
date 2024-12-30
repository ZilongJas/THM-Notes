### Security Groups

- Domain Admins
  - Users of this group have administrative privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs.
- Server Operators
  - Users in this group can administer Domain Controllers. They cannot change any administrative group memberships.
- Backup Operators
  - Users in this group are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.
- Account Operators
  - Users in this group can create or modify other accounts in the domain.
- Domain Users
  - Includes all existing user accounts in the domain.
- Domain Computers
  - Includes all existing computers in the domain.
- Domain Controllers
  - Includes all existing DCs on the domain.

### OUs:
- Builtin: Contains default groups available to any Windows host.
- Computers: Any machine joining the network will be put here by default. You can move them if needed.
- Domain Controllers: Default OU that contains the DCs in your network.
- Users: Default users and groups that apply to a domain-wide context.
- Managed Service Accounts: Holds accounts used by services in your Windows domain.

### Managing Users in AD

Delete OUs:

  - Must enable advanced features under `view`
  - To delete, uncheck `Protect object from accidental deletion` under `object` in properties of the OU

Delegation:

  - grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in

### Group Policies

- collection of settings that can be applied to OUs.

![d82cb9440894c831f6f3d58a2b0538ed](https://github.com/user-attachments/assets/a8f97d0f-d0a4-4ea8-bd0c-bbce11e16941)

- Once a change has been made to any GPOs, it might take up to 2 hours for computers to catch up.
- `gpupdate.exe /force` in powershell to apply instantly

### Authentication Methods

Kerberos: Used by any recent version of Windows. This is the default protocol in any recent domain.
  - ticket based
NetNTLM: Legacy authentication protocol kept for compatibility purposes.
  - hash based

### Trees, Forests and Trusts

- Trees: domain that can share the same namespace, like separting countries (uk.company.local, us.company.local)

- Forests: union of several trees with different namespaces into the same network

- Trust Relationships:  allow both domains to mutually authorise users from the other





















