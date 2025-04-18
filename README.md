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
git --version                        # To check the version after installation is complete
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
bash java-jenkins.sh
java --version                      # To check the version after installation is complete
systemctl status jenkins            # To check status of Jenkins
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/4.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/4ba19d59721e3082d0b6038c85b4c9796e9828eb/images/5.JPG)

## 5. Install `Maven`
```bash
sudo apt-get install maven -y
mvn --version                       # To check the version after installation is complete
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

## 7. Initiate .git repository inside `/my-app` directory and the add and commit all the changes
```bash
git init
git status
git add .
git commit -m "sample maven project is added with a sample java code"
git status
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/b7b326ef7ea54288bfc464addf0c5c52d6222144/images/12.JPG)

## 8. Now push everything to GitHub repository
```bash
git branch -M main
git remote add origin <GitHub_repo_URL>
git push -u origin main
git status

# Now go to GitHub repository and refresh the page, you can see all the contents are available in the repository 
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/b7b326ef7ea54288bfc464addf0c5c52d6222144/images/13.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/b7b326ef7ea54288bfc464addf0c5c52d6222144/images/14.JPG)

## 9. Configure `Jenkins` Dashboard
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/15.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/16.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/17.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/18.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/19.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/20.JPG)

## 10. Add `java`, `git` and `Maven` in `Dashboard > Manage Jenkins > Tools`
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/21.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/22.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/23.JPG)

## 11. Now create a Freestyle project
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/24.JPG)

```markdown
# Add general details :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/25.JPG)

```markdown
# Add Source Code Management  :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/26.JPG)

```markdown
# Add Triggers  :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/27.JPG)

```markdown
# Add Build Steps  :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/28.JPG)

```markdown
# Project got created  :
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/29.JPG)

## 12. Build the Project manually to test it and check the console output
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/30.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/e47e0618ab2c877b22331e1d0c6a341ee16fd62e/images/31.JPG)

## 13. Add `Webhook` to your `GitHub` repository to trigger the `Build` automatically
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/32.JPG)
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/33.JPG)

## 14. Add a README file to your GitHub repository to trigger the Build
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/34.JPG)

## 15. Now check Jenkins Dashboard, you can see that Build got triggered automatically
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/35.jpg)

## 16. Check console output
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/36.JPG)

## 17. After Successful build go to your terminal and change directory to `/var/lib/jenkins/workspace/hello-java-maven-pipeline/target/` to see the package(my-app-1.0-SNAPSHOT.jar) got created
```bash
cd /var/lib/jenkins/workspace/hello-java-maven-pipeline/target/
```
![image alt](https://github.com/souravhajra123/ElevateLabsTask8/blob/9acbdc4bb5465f331f5ea5b4f17a8bc009e1fba7/images/37.JPG)

# THANK YOU
