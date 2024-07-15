# Lecture Notes: Setting Up Salesforce Development Environment

## Lecture Flow

### 1. Cloning a Repo from the GitHub Sample Gallery of Salesforce

#### 1.1 Login into a Dev Hub Org
- How to use Trailhead to create a Salesforce org
    - Visit [Salesforce Trailhead](https://trailhead.salesforce.com/)
    - Search for "Create and Enable a Dev Hub" module
    - Follow the steps to create and enable your Dev Hub org

#### 1.2 Cloning the Repository
- Use the sample repository from [Salesforce LWC Recipes](https://github.com/trailheadapps/lwc-recipes)

**Using GitHub Desktop:**
1. Open GitHub Desktop and sign in to your GitHub account.
2. Click on `File` > `Clone repository`.
3. Select the repository URL tab.
4. Enter the repository URL from the GitHub sample gallery.
5. Choose the local path where you want to save the repository.
6. Click on `Clone`.

**Using SourceTree:**
1. Open SourceTree and sign in to your GitHub account.
2. Click on `Clone/New` in the top left corner.
3. Enter the repository URL from the GitHub sample gallery.
4. Choose the local path where you want to save the repository.
5. Click on `Clone`.

### 2. Creating a Scratch Org from Dev Hub Org
- Now since in the new versions sfdx commands are deprecated, we will use sf commands

**Steps:**
1. Open your terminal or command prompt.
2. Authenticate to your Dev Hub org:
    ```bash
    sf org login web --set-default-dev-hub
    ```
3. Create a scratch org:
    ```bash
    sf org create scratch --definition-file config/project-scratch-def.json --set-default --duration-days 7 --alias my-scratch-org
    ```
4. Open the scratch org:
    ```bash
    sf org open
    ```

### 3. Deploying Codes to a Scratch Org
1. In your terminal or command prompt, navigate to the project directory.
2. Deploy the code to the scratch org:
    ```bash
    sf project deploy start --target-org my-scratch-org
    ```

### 4. Assigning Permission Set
1. Assign the necessary permission set to your user:
    ```bash
    sf org assign permset --name YourPermissionSetName --target-org my-scratch-org
    ```

### 5. Importing Data Tree
1. Create a data plan JSON file specifying the data to import.
2. Use the following command to import the data tree:
    ```bash
    sf data import tree --plan path/to/data-plan.json --target-org my-scratch-org
    ```

### 6. Retriving from Salesforce org
1. You can take all the metadata that you created by point and click tools using the command:
    ```bash
    sf project retrieve start
    ```


---

Feel free to reach out if you have any questions or need further assistance. Join our WhatsApp group for updates and discussions: [Join the group here](https://chat.whatsapp.com/H7YV9EZrAE3GAg7Dp4aOXB)

Happy coding!
