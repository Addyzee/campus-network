# Networking Infrastructure Design for Koitalel arap Samoei University College
![Network Image](/PROJECT/DOCS/net_image.png)

This project was an assignment for my network design class.


## **Project Overview**
Koitalel arap Samoei University College (KSUC), a constituent college of the University of Nairobi, requires the installation of a robust networking infrastructure at its Mosoriot campus located in Nandi County. The infrastructure will include Local Area Networks (LANs), a backbone connection using fiber, server-room LANs, and wireless LANs, all interconnected to support the campus's academic and administrative activities.

[Video link](https://youtu.be/QJCHFcZ7Vaw)



## **Project Deliverables**
1. **Local Area Networks (LANs):**

   - Wired LANs using copper cabling within buildings.
   - Wireless LANs for departmental, laboratory, and hostel access.

2. **Backbone Infrastructure:**
   - Fiber optic cabling to interconnect buildings.

3. **Departmental Networks:**
   - Separate networks for each department, including faculty offices, administrative offices, and computer labs.

4. **Wireless Access:**
   - Wireless access points for:
     - Student access within computer labs.
     - Staff and student access within hostel areas.

5. **Server Setup:**
   - Static IP configuration for servers in the data center.
   - Configuration of servers for local and university-wide services, including SMIS, ERP, email, and the UoN web server.

6. **Internet Access:**
   - Border router configuration to connect to the ISP and main campus.
   - Implementation of NAT for translating private IP addresses (172.16.0.0/16) to public IPs (105.12.32.15/28).
   - Access restrictions for faculty and students (YouTube and Google for faculty; Google only for students).

7. **WAN Connectivity:**
   - Configuration of leased-line WAN to connect Mosoriot campus to UoN main campus.

8. **Routing Configuration:**
   - Dynamic routing protocol (OSPF) for internal routers.
   - Static routing between the ISP and border router.



## **Network Design Specifications**
### **Buildings and Departments:**
1. **Building 1: Administrative Departments**
   - **Floor 1:** Finance (10 PCs, 1 printer), Human Resource (10 PCs, 1 printer)
   - **Floor 2:** Administration (10 PCs, 1 printer), Procurement (10 PCs, 1 printer)

2. **Building 2: Engineering Departments**
   - **Floor 1:** Civil Engineering (15 PCs, 1 printer), Mechanical Engineering (15 PCs, 1 printer)
   - **Floor 2:** Electrical Engineering (15 PCs, 1 printer), Computer Lab (100 PCs)

3. **Building 3: Science and Mathematics Departments**
   - **Floor 1:** Computer Science (20 PCs, 2 printers), Physics (15 PCs, 1 printer)
   - **Floor 2:** Mathematics (20 PCs, 2 printers), Computer Lab (100 PCs)

4. **Building 4: IT and Data Center**
   - **Floor 1:** IT Department (40 PCs, 4 printers)
   - **Floor 2:** Data Center (4 servers)

5. **Building 5: Hostel**
   - Ground Floor: Male Hostel (80 users)
   - First Floor: Female Hostel (65 users)

### **IP Addressing:**
- **Private IP:** 172.16.0.0/16
  - Dynamic allocation for faculty and student devices.
  - Static allocation for servers and printers.
- **Public IP:** 105.12.32.15/28
  - Two addresses reserved for the web server and email server.

### **Access Restrictions:**
- Staff and students: Access to SMIS only.
- IT, Finance, and Administration: Access to SMIS and ERP.
- Faculty: Access to Google and YouTube.
- Students: Access to Google only.


## **Additional Notes**
1. **Predefined Conditions:**
   - Inter-department communication is mandatory.
   - Secure and scalable network topology to ensure reliability and easy maintenance.

2. **Network Security:**
   - Implementation of access control lists (ACLs) to enforce browsing and resource access restrictions.

3. **Connectivity with Main Campus:**
   - WAN connectivity with leased lines for communication with the main campus's centralized systems.

---

## Thanks to my other group members:
- Purity, Sade, Millicent, Don
