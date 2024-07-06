<p align="center"><strong>3D-Portfolio-Project</strong></p>
<p align="center">
  <img src="https://github.com/Herr-Aksoy/Responsive-Website-Design/blob/main/project-images/readme-gif/Responsive-Website-Design.gif" width="700" height="250"/>  
</p>

<br><br>

## Project Owners   
<table align="center" style="width: 67%;">
  <tr >
    <td><img src="project-images/readme-images/AhmetAksoy.png" alt="Ahmet Aksoy" align="center" width="250" ></td>
    <td><img src="project-images/readme-images/MehmetSever.png" alt="Mehmet Sever" align="center" width="250" ></td>
  </tr>
  <tr align="center" style="width: 67%;">
    <td><a href="" align="center">---------->Ahmet Aksoy<---------</a></td>
    <td><a href="" align="center">---------->Mehmet Sever<---------</a></td>
  </tr>
  <tr>
  <td align="center" style="width: 67%;">
    <a href="https://github.com/Herr-Aksoy">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40' title='Github Profile'>
    </a>
    <a href="https://www.linkedin.com/in/aksoy-ahmet/">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/linkedin.svg' alt='linkedin' height='40' title='Linkedin Profile'>
    </a>
    <a href="https://www.instagram.com/updated_devops?igsh=N3kxOWMwdDhsaTZl">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40' title='Instagram Profile'>
    </a>
    <a href="https://www.xing.com/profile/Ahmet_Aksoy68/web_profiles?expandNeffi=true">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/xing.svg' alt='xing' height='40' title='Xing Profile'>
    </a>
  </td>                                       <!--Mehmet Sever abi burdan asagi kisim senin-->
    <td align="center" style="width: 67%;">
    <a href="https://github.com/8mehmet11">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40' title='Github Profile'>
    </a>
    <a href="https://www.linkedin.com/in/mehmet8sever/">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/linkedin.svg' alt='linkedin' height='40' title='Linkedin Profile'>
    <!-- </a>
    <a href="https://www.instagram.com/updated_devops?igsh=N3kxOWMwdDhsaTZl">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40' title='Instagram Profile'>
    </a>
    <a href="https://www.xing.com/profile/Ahmet_Aksoy68/web_profiles?expandNeffi=true">
      <img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/xing.svg' alt='xing' height='40' title='Xing Profile'>
    </a> -->
</tr>
</table>
<br><br>
<!-- <table>
  <tr>
    <td colspan="3"><img src="project-images/readme-images/contributions.png" alt="Contributions to main" width="850"></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/Herr-Aksoy/3D-Portfolio-Project/graphs/contributors" title="More information">Contributions to main, excluding merge commits</a></td>
  </tr>
</table> -->
  
<!-- <br><br> -->

## Live Project: https://portolio2-my-projects.netlify.app 

<br><br>

## Strengthen Your Professional Image with Our Responsive-Website-Design

Creating our Responsive-Website-Design helps strengthen your personal brand and establish a professional image. By effectively showcasing your resume and achievements, you can leave a positive impression on potential employers or partners. Moreover, sharing your contact information expands your professional network and directs traffic to social media and other platforms. Regularly updating your portfolio to highlight recent projects and new skills demonstrates your current and active status. Building your own portfolio website or page allows for uniqueness and creativity, enabling you to shape design, content, and presentation according to your personal style. This empowers you to independently narrate your story and professional journey.

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

