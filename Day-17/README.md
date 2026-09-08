# Day 17: Project Overview

Today I was tasked with creating an Azure Storage Account and provisioning a public Blob Storage container. This exercise focused on configuring storage designed to serve unstructured data such as images or documents directly to the internet with anonymous access, taking account of every configuration event in the deployment pipeline.

## Key Learnings

**Storage Account Provisioning:** Successfully deployed an Azure Storage Account, navigating through the Basics, Advanced and Networking configuration tabs to tailor the resource.
***Public Container Configuration:** Created a blob container and intentionally configured its public access level to allow anonymous read access for blobs, enabling direct internet access.
**Access Level Validation:** Deepened my understanding of how Azure routes public requests by uploading a test file and successfully accessing it via its public URI without authentication.

## Why Public Blob Storage Matters

While private containers are essential for sensitive data, public blob storage plays a crucial role in modern web architecture by offloading static asset delivery from compute resources.

### Here is why it is useful:

1. **Hosting Static Assets:** Public containers are ideal for hosting static web assets like images, CSS and JavaScript files for front-end applications.
2. **Cost-Effective Media Distribution:** It provides an incredibly cheap and highly scalable way to distribute public documents or media files to users globally.
3. **Seamless CDN Integration:** Public blob containers can easily be integrated with Azure Content Delivery Network (CDN) to cache assets at edge nodes worldwide.

## Step-by-Step Execution

### 1. Task Instructions and Scenario
Reviewing the initial project prompt outlining the requirements for creating the storage account and public blob container.
![Task Scenario](./Scenario.png)

### 2. Navigate to Storage Accounts
Searching for and selecting the "Storage accounts" service from the Azure Portal global search bar.
![Navigate to Storage](./Step-1.png)

### 3. Initialize Creation
Clicking the "+ Create" button to open the deployment wizard for a new Storage Account.
![Initialize Creation](./Step-2.png)

### 4. Configure Basics
Setting up the fundamental details: selecting the Subscription, creating/selecting a Resource Group, inputting a globally unique Storage account name, and choosing the Region, Performance (Standard), and Redundancy (LRS/GRS) options.
![Configure Basics](./Step-3.png)

### 5. Advanced Configuration (Enable Public Access)
Navigating to the "Advanced" tab to ensure that the "Allow Blob public access" setting is enabled at the storage account level. This prerequisite must be toggled on before individual containers can be made public.
![Enable Public Access](./Step-4.png)

### 6. Review and Deploy
Passing the final automated validation checks and clicking "Create" to initialize the ARM template deployment. 
![Review and Create](./Step-5.png)

### 7. Go to Resource
Once the deployment succeeds, clicking "Go to resource" to access the newly created Storage Account management plane.
![Go to Resource](./Step-6.png)

### 8. Navigate to Containers
Scrolling down the left-hand menu to the "Data storage" section and selecting "Containers", then clicking "+ Container".
![Navigate to Containers](./Step-7.png)

### 9. Configure Container Access Level
Naming the new container (e.g., `public-assets`) and explicitly expanding the advanced access level dropdown to select **Blob (anonymous read access for blobs only)**.
![Set Access Level](./Step-8.png)

### 10. Upload a Test Blob
Clicking into the newly created container, selecting "Upload", and browsing for a local test file (like a sample image or text document) to upload into the storage space.
![Upload File](./Step-9.png)

### 11. Validate Public Access
Clicking on the uploaded file to view its properties, copying the generated "URL", and pasting it into a new, incognito browser tab to verify that the file loads successfully without prompting for Azure credentials.
![Validate Access](./Step-10.png)
