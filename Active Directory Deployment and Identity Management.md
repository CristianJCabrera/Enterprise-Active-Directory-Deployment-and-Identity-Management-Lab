# Active Directory Deployment and Identity Management Lab

## Overview
This lab focuses on deploying a structured Active Directory environment that models a multi-regional enterprise organization. The implementation emphasizes proper Organizational Unit (OU) design, identity management, and group-based access control by organizing users, computers, and servers across regional and departmental boundaries. The lab demonstrates foundational Active Directory administration practices used in real-world IT and cybersecurity environments, including standardized naming conventions, security group management, and scalable domain organization.

## Skills Learned
- Active Directory Domain Services (AD DS)
- Organizational Unit (OU) Design
- User, group, and computer account management
- Windows Server administration

## Technologies & Tools Used
- Windows Server 2022
- VMware Workstation Pro

## Lab Tasks
### I. Create Organizational Units (OUs)

Create the following top-level OUs to represent company regions:
- USA
- Europe
- Asia

### II. Create Groups 

Within each regional OU, create the following groups:

**User Groups**
- IT
- Accounting
- HR
- Sales
- Management

**Computer Groups**
- IT
- Accounting
- HR
- Sales
- Management

**Servers Group**
- Servers

### III. Create User Accounts
- Create 3 user accounts per department in each region.
- Assign users to their appropriate department security group.
- Use a standardized naming convention (firstnamelastname)

### IV. Create Computer Accounts
- Create 1 computer account per department in each region.
- Add each computer to its corresponding Computers security group.

### V. Server Organization
- Create a Servers OU under each regional OU.
- Add at least one server object to each Servers OU.
- Add each server to the Servers security group.

## Lab Execution
### I. Create Organizational Units (OUs)
The Active Directory environment was deployed using the domain name HomeLab.local as the root of the forest. To simulate an enterprise structure, top-level Organizational Units (OUs) were created: USA, Europe, and Asia. These OUs represent different geological regions working under the same enterprise and help maintain users, computers, and servers organized. 

### <img width="603" height="328" alt="Ref1" src="https://github.com/user-attachments/assets/36e3162f-59df-495c-bdd4-0de2d12f3ee3" />

### II. Create Groups

I initially created all required groups within the group OUs inside the USA OU according to the project tasks. However, when attempting to develop the IT_Users group within the Europe OU, the operation failed because a group with the same name already existed in the domain. This issue highlighted that Organizational Units (OUs) do not provide a naming boundary in Active Directory; instead, object names must be unique across the entire domain.

### <img width="727" height="495" alt="Screenshot 2025-12-17 162908" src="https://github.com/user-attachments/assets/d57f0579-47a4-4eca-9c07-35fa49770941" />

To resolve this, I implemented a more descriptive naming convention in which each user, computer, and server group includes its associated region. This approach ensures domain-wide uniqueness, improves clarity, and aligns with real-world enterprise Active Directory best practices. This was then applied to all groups in all of the region OUs. All groups were created using a global group scope and security group type to organize departments under the same domain while granting them job-specific permissions.  

### <img width="530" height="372" alt="image" src="https://github.com/user-attachments/assets/5a1740bc-3c73-47b2-af7a-5f620bb48245" /> 

### <img width="509" height="378" alt="image" src="https://github.com/user-attachments/assets/7afff873-bdab-4dfa-afdc-d3acfdff102d" />

### III. Create User Accounts

Two additional Organizational Units were created under the Users OU in each region: Groups and User Accounts. This separation helps organize security groups independently from user accounts and improves the overall Active Directory structure. Each department was provisioned with three user accounts, resulting in a total of 45 user accounts across all regions. 

### <img width="625" height="432" alt="image" src="https://github.com/user-attachments/assets/fb92f190-31eb-427a-8798-d278b96ed653" />

All user accounts were created using a standardized naming convention (firstnamelastname) and were assigned to the appropriate departmental security group.

### <img width="433" height="372" alt="Screenshot 2025-12-17 164827" src="https://github.com/user-attachments/assets/1d46ef1d-124d-4c03-946f-ec30f69f3b93" />

### <img width="456" height="245" alt="image" src="https://github.com/user-attachments/assets/dbdcdfe6-43ce-4bb2-8d0d-1461260744cf" />

Each account was configured with a temporary password that is required to be changed at first logon.

### <img width="422" height="372" alt="image" src="https://github.com/user-attachments/assets/f7de5d0a-94fe-442d-bbce-521814476f02" />

### IV. Create Computer Accounts

Similarly to Part III, two additional Organizational Units were created under the Computers OU in each region: Groups and Computer Accounts. Each department was assigned one computer account, resulting in a total of 15 computer accounts across the enterprise.

### <img width="570" height="450" alt="image" src="https://github.com/user-attachments/assets/0bf239ea-95a0-405d-94c5-cd88bbfd0213" />

After completing the computer accounts for the USA region, an error occurred while creating computer accounts in the Europe region. The computer name accounting-pc01-Europe was automatically cut down to ACCOUNTING-PC01 for the pre-Windows 2000 (legacy) computer name. This caused a naming conflict with the Accounting computer in the USA region, which shared the same legacy name. To resolve this issue, a shortened, region-based naming convention was implemented in the legacy computer name to ensure all computer names remained unique and within the 15-character legacy name limit. 

### <img width="735" height="476" alt="image" src="https://github.com/user-attachments/assets/270cfba0-d136-48ec-931b-b1885526243e" />

### <img width="460" height="508" alt="image" src="https://github.com/user-attachments/assets/e2dfc992-d1b5-4a47-ad46-e1ad9f0fc455" />


Each computer account was assigned to their appropiate departmental computer security group. 

### <img width="744" height="449" alt="image" src="https://github.com/user-attachments/assets/b0593740-90e2-4e58-b905-1c6aad6e2c63" />

## Key Takeaways

In Progress...

## References

- East Charmer. *Installing Active Directory on Windows Server on Virtual Machine (Home Lab) (Ep. 1)*. YouTube. https://www.youtube.com/watch?v=GsmJowwIh8Q&list=PLAdEnQWAAbfXMY2D4HVZOe-ChfTKmaJfQ



