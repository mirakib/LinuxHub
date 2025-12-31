# Install the JDK

1. **Use Package Manager:**

For Debian-based systems (e.g., Ubuntu), run: 

```sh
sudo apt update
sudo apt install -y openjdk-21-jdk
```

2. **Set Environment Variables:**

Open the terminal and edit the `.bashrc` file:

```sh
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

Save the file and run `source ~/.bashrc`.

3. **Verify Java installation:**

```sh
java -version
```


### Set default Java runtime

```sh
sudo update-alternatives --config java
```

### Or install automatically with shell script

```sh
#!/bin/bash
set -e
sudo apt update -y
sudo apt install -y openjdk-21-jdk

sudo update-alternatives --set java $(update-alternatives --list java | grep java-21)
sudo update-alternatives --set javac $(update-alternatives --list javac | grep java-21)

JAVA_HOME_PATH="/usr/lib/jvm/java-21-openjdk-amd64"

sudo tee /etc/profile.d/java.sh > /dev/null <<EOF
export JAVA_HOME=${JAVA_HOME_PATH}
export PATH=\$JAVA_HOME/bin:\$PATH
EOF

source /etc/profile.d/java.sh

java -version
javac -version
echo "JAVA_HOME=$JAVA_HOME"
```


# Remove JDK packages

```sh
sudo apt remove -y openjdk-21-jdk openjdk-21-jre
```

```sh
sudo apt purge -y openjdk-21-jdk openjdk-21-jre
```

**Remove unused dependencies:**

```sh
sudo rm -f /etc/profile.d/java.sh
```
