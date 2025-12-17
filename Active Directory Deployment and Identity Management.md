# Active Directory Deployment and Identity Management

## Overview
This lab focuses on deploying a structured Active Directory environment that models a multi-regional enterprise organization. The implementation emphasizes proper Organizational Unit (OU) design, identity management, and group-based access control by organizing users, computers, and servers across regional and departmental boundaries. The lab demonstrates foundational Active Directory administration practices used in real-world IT and cybersecurity environments, including standardized naming conventions, security group management, and scalable domain organization.

## Skills Learned

## Technologies & Tools Used

## Implementation/Lab Tasks

### I. Create Organizational Units (OUs)

Create the following top-level OUs to represent company regions:
- USA
- Europe
- Asia

### II. Create Security Groups 

Within each regional OU, create the following groups:

User Groups
- IT
- Accounting
- HR
- Sales
- Management

Computer Groups
- IT
- Accounting
- HR
- Sales
- Management

Servers Group
- Servers

### III. Create User Accounts

- Create 3 user accounts per department in each region.
- Assign users to their appropriate department security group.
- Use a standardized naming convention (firstname_lastname)

### IV. Create Computer Accounts

- Create 1 computer account per department in each region.
- Move each computer into the correct department OU.
- Add each computer to its corresponding Computers security group.

### V. Server Organization

- Create a Servers OU under each regional OU.
- Add at least one server object to each Servers OU.
- Add each server to the Servers security group.

## Key Takeaways

## References


