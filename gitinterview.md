# U have cloned the git repo and renamed it in your local dircetory. How do you get the actual git repo location (original git repo)?

``` git remote -V ```

![image](https://user-images.githubusercontent.com/54719289/118531317-9d026500-b73d-11eb-8428-6faee9b9003c.png)


# 
![image](https://user-images.githubusercontent.com/54719289/118531460-c4f1c880-b73d-11eb-9f6f-18e73321dbb0.png)

``` Answer is git clone -b branchname --depth 1 git-url ```

![image](https://user-images.githubusercontent.com/54719289/118532194-958f8b80-b73e-11eb-87f8-84f597c1e912.png)


# What is submodule? Why do we need to use?

![image](https://user-images.githubusercontent.com/54719289/118532478-eb643380-b73e-11eb-84e8-dc0db492d78a.png)
![image](https://user-images.githubusercontent.com/54719289/118532546-fb7c1300-b73e-11eb-8c82-2c4c11b96324.png)

## There is a disadvantage in submodule. Submodules dont track refs or branch and are not automatically updated when host repo is updated


# Another question:

![image](https://user-images.githubusercontent.com/54719289/118533269-c7552200-b73f-11eb-9cc2-070f94580ba8.png)

```  With the help git rm --cached filename  ``` 
we can delete the particular file before commiting ```

![image](https://user-images.githubusercontent.com/54719289/118533415-f53a6680-b73f-11eb-886e-624e9cfdce7a.png)


# Maven Question
![image](https://user-images.githubusercontent.com/54719289/118533736-53674980-b740-11eb-8eb3-76e497c338b3.png)

# Refer this link : https://github.com/logambigaik/Maven_Examples.git

  >> Step2 : In main module(parent module - pom.xml we need to use pom as packaging and also include those main module and as well the submodule in modules tag

```
<?xml version="1.0"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>



  <groupId>calculator</groupId>
  <artifactId>calculator-main</artifactId>
  <version>1.0</version>
  <packaging>pom</packaging>

  <name>calculator_addition</name>

  <modules>
    <module>addition</module>
    <module>substraction</module>
  </modules>
```

  >> Step 2 : Also in sub module, we need to include the parent tag inside child module pom.xml
  
  ```
  <?xml version="1.0"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <parent>
      <groupId>calculator</groupId>
      <artifactId>calculator-main</artifactId>
      <version>1.0</version>
    </parent>
    
   ```
  
  >> Step 3: run mvn tidy:pom command before mvn clean install . Now, you could see jar files under target folder in submodules.
  
  

  
  
   







