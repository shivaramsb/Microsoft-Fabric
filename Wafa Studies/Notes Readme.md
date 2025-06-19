# Introduction to Microsoft Fabric

**Overview of Microsoft Fabric**
- Microsoft Fabric is an all-in-one analytics solution designed for enterprises, bringing together all analytics needs into a single product[1].
- It covers the entire analytics workflow: data movement, data science, real-time analytics, and business analytics[1].
- The platform aims to provide everything required by data engineers, data scientists, and analysts in one place[1].

**Business Analytics Context**
- Businesses need analytics to make informed decisions, such as which products to stock or which stores are performing well[1].
- Business data is often distributed across multiple locations, making analytics complex and requiring integration from various data sources[1].

**Traditional Data Workflow (Before Fabric)**
- Data engineers extract data from multiple sources, transform it, and load relevant subsets into data warehouses (ETL process)[1].
- SQL tables in data warehouses are used for reporting, typically via tools like Power BI, enabling leadership teams to make business decisions[1].
- Different roles involved:
  - Data Engineers: Handle data extraction, transformation, and loading.
  - Data Analysts: Create reports and analyze data for insights[1].

**Tools Previously Required**
- Multiple services were traditionally needed for end-to-end analytics:
  - Azure Data Factory for ETL pipelines
  - Azure Synapse for data warehousing and SQL analytics
  - Apache Spark or Databricks for big data transformations
  - Power BI for reporting
  - Azure Data Explorer for real-time analytics and observational (IoT/sensor) data using Kusto Query Language (KQL)[1].

**What Microsoft Fabric Offers**
- Microsoft Fabric consolidates all these services into a single SaaS (Software as a Service) platform[1].
- Key capabilities included:
  - Data integration (ETL pipelines)
  - Data engineering (Spark for big data)
  - Data warehousing (SQL tables)
  - Data science (ML model creation and training)
  - Real-time analytics (Kusto/ADX for IoT and sensor data)
  - Reporting (Power BI)[1].
- The platform provides a unified storage layer called "OneLake," built on top of Azure Data Lake Storage Gen2, for storing all types of data[1].

**Benefits of Microsoft Fabric**
- Eliminates the need to manage and integrate multiple separate services[1].
- Simplifies security, access control, and storage management since everything is integrated[1].
- Reduces operational complexity and overhead for organizations[1].

**Technical Highlights**
- OneLake serves as the foundational storage, supporting various data formats (e.g., Delta tables, warehouses, Kusto databases)[1].
- Fabric provides multiple compute options: SQL, Spark, Kusto, and Analysis Services[1].
- Enables end-to-end analytics projects within a single environment[1].

**Summary Statement**
- Microsoft Fabric is a comprehensive analytics platform from Microsoft that combines the capabilities of Data Factory, Synapse, Spark, Power BI, and more, providing a single solution for all enterprise analytics needs[1].
- It is designed to streamline analytics workflows, improve security and management, and reduce the need for multiple separate resources.






# Microsoft Fabric Terminologies 

This video covers essential terminology that users need to understand when working with Microsoft Fabric. The session is theoretical and focuses on five key terms that are frequently used throughout the platform.

## **Capacity**

Capacity refers to the computational power or physical resources allocated to your Fabric resource to execute tasks and produce outputs[1]. Think of it as the "horsepower" behind your Fabric operations - whether you're running notebooks, pipelines, or any other fabric operations, they all depend on the capacity allocated to your resource[1].

**How Capacity is Provided:**
- **Trials**: Free trial resources automatically receive capacity allocation behind the scenes, enabling users to create fabric items like pipelines, databases, and lakehouses[1]
- **Fabric SKUs (Stock Keeping Units)**: Purchased licenses that provide capacity through various pricing tiers[1]

## **Experience**

Experience represents the different capabilities or roles available within Microsoft Fabric[1]. Since Fabric combines multiple services (like Data Factory, Spark, Azure Data Explorer/Kusto), each of these integrated services is presented as a separate "experience"[1].

**Available Experiences:**
- **Data Engineering Experience**: For ETL processes and data transformation
- **Data Science Experience**: For machine learning and analytics
- **Data Warehousing Experience**: For structured data storage and querying
- **Real-time Analytics Experience**: Using Kusto for real-time data processing[1]

These experiences can be accessed through the menu system in the Fabric portal, where users can switch between different roles and capabilities[1].

## **Item**

Items are the specific objects or resources you can create within each experience[1]. Every experience allows you to create various types of items relevant to that particular domain.

**Examples of Items:**
- **Under Data Engineering Experience**: Lakehouses (Spark databases with Delta tables), Spark notebooks, Spark job definitions[1]
- Items represent any tangible resource created within a specific experience to accomplish tasks[1]

## **Tenant**

A tenant is a single instance of Microsoft Fabric provided to an entire organization[1]. It's the top-level container that encompasses all Fabric resources for a company and is tied to the organization's Microsoft Entra ID (formerly Azure Active Directory)[1].

**Key Characteristics:**
- One tenant per organization
- Provided through Microsoft Entra ID
- Contains all workspaces and resources for the entire company[1]

## **Workspace**

Workspaces function like folders or project containers within the tenant[1]. They provide organizational structure for different teams, projects, or departments within the company.

**Workspace Functionality:**
- Acts as a project-level container where teams can organize their work
- Contains all items created across different experiences
- Provides the first step in the Fabric workflow - users create a workspace before creating any items[1]
- Multiple people can work on different projects by creating separate workspaces within the same tenant[1]

## **Hierarchical Structure**

The relationship between these terms follows this hierarchy:
1. **Tenant** (Organization level)
2. **Workspace** (Project/Team level)
3. **Experience** (Role/Capability level)
4. **Item** (Individual resource level)
5. **Capacity** (Underlying compute power for all operations)




# Microsoft Fabric Workspace Creation 

This video demonstrates the practical process of creating workspaces in Microsoft Fabric, building upon the theoretical concepts covered in previous videos about terminologies.

## **What is a Workspace?**

A workspace functions as a **folder-like container** within Microsoft Fabric where teams can collaborate on projects. Within an organization's Fabric tenant, multiple workspaces can be created for different projects:

- **Workspace 1**: May contain lakehouses and Power BI reports
- **Workspace 2**: May contain data warehouses  
- **Workspace 3**: May contain notebooks and other items

Each workspace serves as a collaborative space where team members can create and manage fabric items (notebooks, lakehouses, reports, data warehouses, etc.) according to their specific project requirements[1].

## **Step-by-Step Workspace Creation Process**

**Initial Setup:**
1. Navigate to `app.fabric.com` in your browser
2. Log in with your Fabric trial account credentials
3. Access the Microsoft Fabric homepage

**Creating the Workspace:**
1. Click the **Microsoft Fabric icon** from the homepage
2. Select an **experience** (e.g., Data Engineering Experience)
3. Navigate to the **Workspaces menu** (you'll see "My Workspace" by default)
4. Click the **"New Workspace"** button

## **Workspace Configuration Options**

**Required Fields:**
- **Name**: Mandatory field for workspace identification
- **Description**: Optional but recommended for clarity

**Optional Configurations:**
- **Domain Association**: Links workspace to organizational domains for content discovery (covered in future classes)
- **Workspace Image**: Custom icon/logo for visual identification
- **Contact List**: Users who receive email alerts for workspace changes
- **License Mode**: Automatically set based on your Fabric license type

**Advanced Settings:**
- Contact lists enable automatic email notifications when workspace changes occur
- The workspace creator is automatically added as a contact by default

## **Workspace Management Features**

**Pinning Workspaces:**
- Organizations may have hundreds of workspaces across different projects
- **Pin frequently used workspaces** to appear at the top of your workspace list
- Access pinning via the **pin symbol** that appears when hovering over workspace names
- Pinned workspaces appear in a separate "Pinned Workspaces" section
- Unpinned workspaces appear in the "All" category below

**Visual Workspace Hierarchy:**
```
Organization Tenant
├── Pinned Workspaces
│   ├── My Sample Workspace (pinned)
│   └── Other Pinned Workspaces
└── All Workspaces
    ├── Unpinned Workspace 1
    ├── Unpinned Workspace 2
    └── Additional Workspaces
```

## **Key Takeaways**

- Workspaces are essential organizational containers for Fabric projects
- Each workspace can contain multiple types of fabric items across different experiences
- Proper workspace management (naming, descriptions, pinning) improves team collaboration and project organization
- The workspace creation process is straightforward but offers flexibility for customization
- Understanding workspace concepts is crucial before creating fabric items like lakehouses, notebooks, or reports




# Microsoft Fabric Workspace Roles and Access Management 

## **Why Workspace Roles Are Needed**

Workspace roles are essential for controlling user permissions and managing what actions different users can perform within a Microsoft Fabric workspace. Since workspaces can contain various fabric items like:
- Data pipelines
- Notebooks  
- Multiple experiences and capabilities

Roles help administrators control **what users can do** and **what kind of activities** they can perform in the workspace.

## **Four Available Workspace Roles**

### **Visual Role Hierarchy:**
```
Admin Role (Highest Permissions)
├── Full workspace control
├── Update and delete workspace
└── All capabilities available

Member Role
├── Most capabilities
└── Cannot update/delete workspace

Contributor Role  
├── Limited capabilities
└── Can contribute content

Viewer Role (Lowest Permissions)
├── View-only access
├── Cannot edit anything
└── Read-only permissions
```

## **Role Capabilities Matrix**

**Example Capabilities:**
- **Update and delete workspace**: Only **Admin** can perform
- **View and read content of KQL database, KQL query sets, and real-time dashboards**: **All roles** (Admin, Member, Contributor, Viewer) can perform

**Documentation Reference:**
Microsoft provides detailed documentation with a comprehensive table explaining:
- Different capabilities available in Fabric
- Which roles can perform which capabilities
- Specific permissions for each role type

![image](https://github.com/user-attachments/assets/171c4c18-261c-4686-aea4-16e6d558cca3)


## **Step-by-Step Access Management Process**

### **Accessing Workspace Management:**
1. Navigate to `app.fabric.microsoft.com`
2. Go to **Workspaces menu**
3. Click on your desired workspace (e.g., "Mahir Demo Workspace")
4. Workspace appears in **favorites navigation menu** once opened

### **Current Workspace Status:**
- Workspace contains fabric items (e.g., "Pipeline One")
- Initially, only the workspace creator has access with **Admin role**

### **Granting User Access:**

**Visual Process Flow:**
```
Workspace → Manage Access → Add People/Groups → Select Role → Add User
```

**Detailed Steps:**
1. Click **"Manage Access"** button within the workspace
2. Access panel opens showing current users and their roles
3. Click **"Add People or Groups"** button
4. **Enter user details:**
   - Search by email ID or name
   - Example: "Pradip Chatla" 
5. **Select role** from dropdown:
   - Admin
   - Member  
   - Contributor
   - Viewer
6. Click **"Add"** button to grant access

### **Before and After Access Management:**

**Before Adding User:**
```
Workspace Access:
└── Current User (Admin role only)
```

**After Adding User:**
```
Workspace Access:
├── Current User (Admin role)
└── Pradip Chatla (Member role)
```

## **Verification Process**

After adding a user:
1. Close the add user window
2. Click **"Manage Access"** again
3. Verify that both users are listed:
   - Original creator with Admin role
   - Newly added user with assigned role (Member in the example)

## **Key Benefits of Role-Based Access**

- **Security Control**: Limit user actions based on their responsibilities
- **Collaboration**: Enable team members to access workspace with appropriate permissions
- **Flexibility**: Different roles for different team members based on their needs
- **Workspace Protection**: Prevent unauthorized changes to critical workspace settings

## **Important Notes**

- Users can access the workspace immediately after being granted access
- Role permissions determine what capabilities users can perform
- Workspace creator automatically gets Admin role
- Multiple users can be added with different roles as needed
- Role assignments can be modified later through the same manage access interface
