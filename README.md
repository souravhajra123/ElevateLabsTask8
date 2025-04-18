# Run a Simple Java Maven Build Job in Jenkins

## 1. Launch an EC2 Instance
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/1.JPG)

## 2. Connect to the EC2 Instance and Update it
```bash
sudo apt-get update
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/2.JPG)

## 3. Install `Git`
```bash
sudo apt-get install git
git --version              # To check the version after installation is complete
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/3.JPG)

## 4. Install `java` and `Jenkins`
```bash
nano java-jenkins.sh                 # `ctrl+s` to save the file, `ctrl+x` to exit the nano editor mode
-----------------------
sudo apt-get update
sudo apt install fontconfig openjdk-17-jre -y
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y
------------------------
java --version                      # To check the version after installation is complete
systemctl status jenkins            # To check status of Jenkins
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/4.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/5.JPG)

## 5. Install `Maven`
```bash
sudo apt-get install maven -y
mvn --version              # To check the version after installation is complete
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/6.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/7.JPG)

## 6. Create a sample maven project
```bash
mvn archetype:generate -DgroupId=com.example -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
# This will create a sample maven project with sample `pom.xml` in /my-app directory and a sample java code `App.java` in /my-app/src/main/java/com/example directory
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/8.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/9.JPG)

```markdown
# pom.xml :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/10.JPG)

```markdown
# App.java :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/11.JPG)

