# Argocd Integration into Azure Kubernetes Cluster

## Create to Azure Kubernetes Cluster

### Step 1- Update Azure CLI and sign in:

```sh

az upgrade
az login

``` 

### Step 2- Create a Resource Group:

You can write your own resource group name instead of **'MyAKS-rg'** and your preferred region instead of **'westeurope'**

```sh

az group create --name MyAKS-rg --location westeurope 

```

### Step 3- Create an AKS Cluster:

In this command, we specify the virtual machine SKU that the nodes will use with the **'--node-vm-size'** parameter. Different SKUs have different CPU and memory capacities, such as **'Standard_D4s_v3'**. For example, the **'Standard_D4s_v3'** SKU includes 4 vCPUs and 16 GB RAM.

```sh

az aks create \
    --resource-group MyAKS-rg \
    --name MyAKSCluster \
    --node-count 1 \
    --node-vm-size Standard_D4s_v3 \
    --generate-ssh-keys \
    --enable-node-public-ip \
    --location northeurope \
    --debug


``` 

**❗Example size:** Standard_B2s


az aks delete \
    --resource-group MyAKS-rg \
    --name MyAKSCluster \
    --yes --verbose


### Step 4- Download and set the kubectl configuration file:

This command downloads and sets the kubectl configuration file required to access your AKS cluster.

```sh

az aks get-credentials --resource-group MyAKS-rg --name MyAKSCluster --overwrite-existing

``` 

### Step5- Verify that the cluster is running:

With this command, you can see the list of nodes and verify that the cluster is working properly.

```sh

kubectl get nodes

``` 
# What is ArgoCD?

ArgoCD is a GitOps continuous delivery tool used to manage applications in Kubernetes clusters. The GitOps approach ensures that application and infrastructure codes are kept in a Git repository and changes in this repository are automatically applied to Kubernetes clusters.

## Purpose of ArgoCD

The main goal of ArgoCD is to improve the software delivery process by automating application deployments and configuration management. By adopting the GitOps approach, it makes application deployments more reliable, traceable and scalable.

## Benefits of ArgoCD

**Automatic Deployment:** Every change made to the Git repository is automatically applied to Kubernetes clusters by ArgoCD. This reduces manual intervention and speeds up the deployment process. Version Control: Since all application and configuration changes are stored in Git, every change can be tracked and reverted. This ensures quick response in case of errors.  

**Traceability and Visualization:** Traceability and Visualization: ArgoCD offers the opportunity to visually monitor application statuses and deployment processes. Thanks to its web-based interface, you can easily see which application is in which version.  

**Notifications and Warnings:** ArgoCD sends notifications and alerts about errors or problems that may occur in the deployment processes. In this way, rapid intervention is possible. Rollout Strategies: Supports rollout strategies such as canary deployments, blue-green deployments. This provides safer and more controlled distribution processes.
Cluster Expansion: ArgoCD is capable of managing multiple Kubernetes clusters. This enables central management of applications in different environments (test, staging, prod).

## What Can Be Managed with ArgoCD

**Application Deployments:** Any application running on Kubernetes can be deployed via ArgoCD. This includes microservices architectures, monolithic applications, databases and more.  

**Configuration Files:** Configuration components such as Kubernetes manifest files (YAML/JSON), ConfigMaps, Secrets can be managed.  

**Infrastructure Components:** Infrastructure configurations such as network components, security policies, RBAC settings needed at the cluster level can be managed.  

**Helm Charts:** Packaging and deploying applications using Helm charts is supported. Kustomize: Using Kustomize, patching and management of Kubernetes YAML files can be done.

## ArgoCD Usage Scenarios

**Continuous Integration/Continuous Delivery (CI/CD):** Integrating with CI tools, automatically testing code changes and distributing successful ones to Kubernetes clusters.  

**Multiple Environment Management:** Consistent and automatic management of applications in different environments such as testing, staging and production.  

**Automatic Rollback:** In case of a faulty deployment, automatic rollback to the previous stable version. ArgoCD is a powerful and flexible tool for teams working on Kubernetes. Thanks to the GitOps methodology, it ensures that deployment processes are more reliable, traceable and manageable. This makes the job of software development and operations teams easier and increases overall efficiency.


#  Installing Argocd in a Kubernetes Cluster

**Internet sitesi:** https://argo-cd.readthedocs.io/en/stable/getting_started/

**Commands:**

```sh

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```

Convert Argocd service to LoadBalancer type.

```sh

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

```

After Argocd installation, you need secret information to connect to the service. Since the installation is done from the ready-made Helm chart, the secrets come embedded in the Chart.  
Let me view the secrets with this command.

```sh

kubectl get secret -n argocd 

```

When you open the secret named argocd-initial-admin-secret with the following command, you will see the password.

```sh

kubectl get secret argocd-initial-admin-secret -n argocd  -o yaml

```

Since the password is encrypted with base64, you must unlock the password with this command.

```sh

echo "< Password >" | base64 -d

```

Reorder the created services. And log in from the Browser with the assigned Public IP.

```sh

kubectl get svc -n argocd

```

Enter the admin username and password in the Argocd interface that opens.


![a1-sing-in](images/a1-sing-in.png)





az aks get-credentials --resource-group MyAKS-rg --name MyAKSCluster

az aks get-credentials --resource-group MyAKS-rg --name MyAKSCluster --overwrite-existing


az vm list-ip-addresses --resource-group  MyAKS-rg --name aks-nodepool1-13610020-vmss000000


c3dd481e-1c4e-4ae7-aa49-afd3c6ef1bd7

az login --tenant af5a547e-983b-442a-9e29-6637088a80e9



## Project Technologies

<table>
  <tr>
    <td><strong>Infrastructure:</strong></td>
    <td>AWS (Amazon Web Services), Terraform</td>
  </tr>
  <tr>
    <td><strong>Containerization & Orchestration:</strong></td>
    <td>Docker</td>
  </tr>
  <tr>
    <td><strong>CI/CD Tools:</strong></td>
    <td>GitHub Actions</td>
  </tr>
  <tr>
    <td><strong>Frontend:</strong></td>
    <td>HTML, CSS, JavaScript</td>
  </tr>
  <tr>
    <td><strong>Backend:</strong></td>
    <td>Python, Flask</td>
  </tr>
  <tr>
    <td><strong>Version Control:</strong></td>
    <td>GitHub</td>
  </tr>
  <tr>
    <td><strong>Cloud Services:</strong></td>
    <td>AWS EC2, AWS VPC</td>
  </tr>
  <tr>
    <td><strong>Container Registry:</strong></td>
    <td>Dockerhub</td>
  </tr>
</table>
  
<br><br>

## Infrastructure Process

With Terraform, we create AWS resources including Virtual Private Cloud (VPC), Elastic Compute Cloud (EC2) instances, key pairs, security groups, and various outputs. When provisioning EC2 instances, we utilize user data. This user data installs software such as Docker, Git, Flask, and pip. Our application consists of HTML, CSS, and JavaScript code, tailored to run on Flask. Using Docker, we package this application to run within a container and execute the Python (.py) file. 

To automatically build a Docker image of our application, we leverage GitHub Actions. In this process, a job is triggered to build a Docker image and push it to Docker Hub. Connecting via SSH to our EC2 instance, we deploy this Docker image and access our application via the specified port.

## CI/CD Process

CI/CD (Continuous Integration/Continuous Deployment) process is a method used to enhance efficiency in software development. This process enables rapid development, testing, and deployment of software projects, while reducing manual intervention. It facilitates continuous integration and continuous deployment.

How It Works?

<strong>Build and Push Stage (build-and-push.yml):</strong> This stage is a YAML file configured with GitHub Actions or similar CI/CD tools. It automatically runs with every new code commit (push operation). It builds the latest version of the Docker image and pushes it to Dockerhub or another container registry.

For example, the build-and-push.yml file may include these steps:

Compiling and testing the code  
Building the Docker image  
Pushing the Docker image to Dockerhub  

<strong>Automatic Triggering:</strong>Automatic Triggering: GitHub or other CI/CD tools configure this YAML file to automatically execute these steps with every new code commit. This eliminates the need for developers or teams to manually initiate these processes with each code change.

<strong>Sending the Latest Version to the Repository:</strong> The Docker image is automatically updated and sent to the container registry with each push operation. This ensures that the most current and functional version is always available.

This process has become an integral part of modern software development practices, enhancing the effectiveness, reliability, and speed of software projects.

### Creating .github\workflows\build-and-push.yml

In order to push images to the Docker Hub repo, we create secrets in the Githup account and use them in the file.

![parameters](project-images/repo-images/secrets-actions.png)

We create a build-and-push.yaml file to use Github Action. And we specify the secrets inside.  

**❗ Sample Code line**

```sh

    - name: Docker Login
      uses: docker/login-action@v3
      with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

    - name: Push Docker image to Dockerhub Public Repo
      run: docker push ${{ secrets.DOCKER_USERNAME }}/projects:Responsive-Website-Design

```

We go to Repo > Setting > Secrets and variables > Actions and create "New repository secrets" here.

![parameters](project-images/repo-images/repo-secrets.png)

# Working process of the project

## a-Responsive-Website-Design.html File:

Enter the required information in the Responsive-Website-Design.html file.

You must add the **"const scriptURL ="** link in the Responsive-Website-Design.html file.

### Step 1: Creating a Blank Google Sheets
Go to Google Drive:

Go to Google Drive.
Create a New Google Sheets:

Click the "New" button in the upper left corner.
Select "Google Sheets" from the menu that opens and then click "Blank spreadsheet."
### Step 2: Accessing Apps Script
Open Google Sheets Document:

Open the Google Sheets document you just created.
Access Apps Script from Plugins Menu:

Click on the "Extensions" menu in the top menu.
Click "Apps Script" from the menu that opens.
### Step 3: Adding Apps Script Code
Add Code to Apps Script Editor:

The Apps Script editor will open in a new browser tab.
Paste the following code in the editor that opens and save it:



```sh

var sheetName = 'Sheet1'; // Type your tab name here, for example 'Data'
var scriptProp = PropertiesService.getScriptProperties();

function doPost(e) {
  var lock = LockService.getScriptLock();
  lock.waitLock(10000);

  try {
    var doc = SpreadsheetApp.openById(scriptProp.getProperty('key'));
    var sheet = doc.getSheetByName(sheetName);

    var newRow = sheet.getLastRow() + 1;
    var rowData = [];
    for (var param in e.parameter) {
      rowData.push(e.parameter[param]);
    }
    sheet.getRange(newRow, 1, 1, rowData.length).setValues([rowData]);

    sendEmail(rowData); // Send email when new data is added

    return ContentService
      .createTextOutput(JSON.stringify({'result': 'success', 'row': newRow}))
      .setMimeType(ContentService.MimeType.JSON);
  } catch (e) {
    return ContentService
      .createTextOutput(JSON.stringify({'result': 'error', 'error': e}))
      .setMimeType(ContentService.MimeType.JSON);
  } finally {
    lock.releaseLock();
  }
}

function setup() {
  var doc = SpreadsheetApp.getActiveSpreadsheet();
  scriptProp.setProperty('key', doc.getId());
}

function sendEmail(rowData) {
  // Recipient e-mail address
  var recipient = "<example@gmail.com>"; // Write your own e-mail address here

  // Email subject and content
  var subject = "Responsive-Website-Design";
  var body = "Contact Me";

  // Organize data in table format
  var message = "";
  message += "<b>New Row Data:</b><br>";
  for (var i = 0; i < rowData.length; i++) {
    message += rowData[i] + "<br>";
  }

  // Email sending process
  MailApp.sendEmail({
    to: recipient,
    subject: subject,
    htmlBody: body + "<br><br>" + message
  });
}


```

### Step 4: Publishing the Script
Save and Publish Script:
Save your script and then run the setup function. To do this, select the setup function and click 
the run button from the menu. This will store the identity (ID) of your Google Sheets document.
Click the Deploy button from the top menu and select New deployment.
Select Web app from the Select type menu.
Select Me in Execute as and Anyone in Who has access.
Click the Deploy button and copy the resulting URL.

### Step 5: Adding the URL to Your HTML Form Code
Paste the URL into the Code:

Paste the URL you copied into the scriptURL variable in your HTML file:

```sh

const scriptURL = 'https://script.google.com/macros/s/your_script_id/exec'

```

## b-Configure the build-and-push.yml File:

Add your own Docker Image Repository to the **build-and-push.yml** file.

## c-Creating and Submitting Images with GitHub Actions:

Run the **build-and-push.yml** file from the Action section of the GitHub repo.  
GitHub Actions will create a Docker image for you and automatically push it to the specified repository.

## d-Terraform Configuration:

Run the **main.tf** file by making the necessary changes in the **userdata.sh** file.

## e-Running Docker Container Automatically:

Normally, you can run the Docker container manually by making an SSH connection to EC2. However, we can add it as a command to the user data to automate this.  

To do this, update the **docker run** command written in the user data according to your needs.  

By following these steps you can automatically install and run your application.

<!-- ```sh


``` -->

