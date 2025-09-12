# Install Java 21 JDK

Systems operating Jenkins must have a Java runtime environment installed. The recommended version of Java for use with Jenkins is Java 21.

Run the following commands to update the package management system and Install openjdk-21-jdk:

```
sudo apt-get update

sudo apt-get upgrade -y

sudo apt-get install -y openjdk-21-jdk
```

## Install Jenkins

Continue in the terminal with the following steps.

1. Install wget; this application will be used to download additional resources:

    ```sudo apt-get install -y wget```

2. Run the following commands to:

    Download the official signing key for Jenkins packages.
    Update the package manager to include the official sources for Jenkins installation files.
    Update the package manager to refer to the new key and installation sources.

             ```bash

             sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \

               https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

 

             echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \

               https://pkg.jenkins.io/debian-stable binary/ | sudo tee \

               /etc/apt/sources.list.d/jenkins.list > /dev/null

 

             sudo apt-get update

             ```

3. Run the following command to install Jenkins:

    ```sudo apt-get install -y jenkins```

4. Confirm that the command completes successfully.

5. Run the following command to retrieve the initial administrator password:

    ```sudo cat /var/lib/jenkins/secrets/initialAdminPassword```

6. Copy the password for use during the next installation steps.

7. Complete the installation by opening a browser and connecting to the system’s network address using port 8080.

    If you are installing Jenkins on a local system, use: ```http://localhost:8080```
    If you are installing Jenkins on a remote system, specify the system’s network name, for example: ```http://system-name.example.com:8080```
