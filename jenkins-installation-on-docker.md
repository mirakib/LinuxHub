# Install Jenkins Using Docker

1. Pull the jenkins:lts-jdk21 image

   ```docker pull jenkins/jenkins:lts-jdk21```

2. Create a volume for Jenkins data

   ```docker volume create jenkins_volume```

3. Use the image and volume to run a container

    ```bash

        docker run --detach \

            --volume jenkins_volume:/var/jenkins_home \

            --publish 8080:8080 \

            --name jenkins \

            jenkins/jenkins:lts-jdk21

    ```

4. Get the initial administrator password

   ```docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword```

5. Complete the installation process in your browser

   ```http://localhost:8080```
   
