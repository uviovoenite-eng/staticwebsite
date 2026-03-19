# staticwebsite
Creating a static website
1. Objective
In this lab, you will deploy your first public-facing resource in Azure. Instead of building a complex server to host a simple website, you will use Azure Blob Storage. This introduces you to the concept of PaaS (Platform as a Service) and Serverless hosting, where you focus on the content, and Azure handles the infrastructure.
2. Architecture Diagram
(Imagine a simple diagram: User (Internet) -> Public URL -> Azure Storage Account ($web container) -> index.html)
3. Prerequisites
[ ] Active Azure Subscription (Free Tier is fine).
[ ] Completed Week 1 Video Modules.
[ ] A basic text editor (Notepad, TextEdit, or VS Code).
4. Lab Variables (Naming Convention)
Use these names to ensure consistency.
Resource Group: rg-lab01-enite
Location: East US
Storage Account Name: stlab01enite
Note: Storage account names must be globally unique, all lowercase, and no special characters.
5. Step-by-Step Instructions
Phase 1: Create the Resource Group
Log in to the Azure Portal (https://www.google.com/search?q=portal.azure.com).
Search for Resource Groups in the top search bar.
Click + Create.
Basics Tab:
Subscription: Select your subscription.
Resource Group: Enter rg-lab01-enite.
Region: Select (US) East US.
Click Review + create -> Create.
Phase 2: Create the Storage Account
Search for Storage accounts in the search bar.
Click + Create.
Basics Tab:
Resource Group: Select rg-lab01-enite.
Storage account name: stlab01enite Remember: All lowercase, numbers and letters only.
Region: (US) East US.
Performance: Standard.
Redundancy: Locally-redundant storage (LRS). This is the cheapest option for labs.
Click Review + create.
Wait for validation to pass, then click Create.
When deployment finishes (about 30 seconds), click Go to resource.
Phase 3: Enable Static Website Hosting
On the left-hand menu of your Storage Account, look under the Data management section.
Click on Static website.
Static website: Switch from "Disabled" to Enabled.
Index document name: Enter index.html.
Error document path: Enter 404.html (Optional, but good practice).
Click Save.
CRITICAL: Once saved, a Primary endpoint URL will appear. Copy this URL. This is your website's address.
Phase 4: Create Your Website File
Open your text editor on your computer.
Paste the following simple HTML code:
<!DOCTYPE html>
<html>
<head>
    <title>My First Cloud Site</title>
    <style>
        body { font-family: sans-serif; text-align: center; margin-top: 50px; background-color: #f0f0f0; }
        h1 { color: #0078d4; }
    </style>
</head>
<body>
    <h1>Hello from the Cloud!</h1>
    <p>This site is hosted on Azure Blob Storage.</p>
    <p>Deployed by: Enite Uviovo </p>
</body>
</html>


Save this file on your desktop as index.html.
Phase 5: Upload Content
Go back to the Azure Portal (you should still be on the Static website blade).
On the left menu, click on Containers (under Data storage).
You will see a new container named $web. This was created automatically. Click to open it.
Click Upload at the top.
Browse for your index.html file on your desktop.
Click Upload.
Phase 6: Validation
Open a new browser tab.
Paste the Primary endpoint URL you copied in Phase 3.
Hit Enter.
You should see your "Hello from the Cloud!" message.
Congratulations! You just deployed a serverless website.
6. Troubleshooting / Common Issues
Issue: "404 - The requested content does not exist."
Fix: Did you name the file exactly index.html? Azure is case-sensitive. Index.html or index.txt will not work.
Fix: Did you upload the file to the $web container? If you uploaded it to a different container, it won't work.
Issue: "Storage account name is already taken."
Fix: Storage names must be unique across all of Azure, not just your account. Add some random numbers to the end of your name (e.g., stlab01jhante99).
7. Clean Up Resources
Important: Always clean up to keep your cloud environment tidy.
Go to Resource Groups.
Click rg-lab01-enite.
Click Delete resource group.
Type the name to confirm.
Click Delete.
