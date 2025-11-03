# AWS Lambda Java Template

> ⚠️ **Warning:** This template is done after trying to create a maven archetype, but I couldn't add the `.gitignore` file to the archetype (yes, I did't want to copy those impressive 5 lines of code to every new project). If you know how to do it, please let me know.

## Description

This project serves as a **template for creating AWS Lambda projects** using **Java with Maven**.  
It includes a **preconfigured CI/CD pipeline** powered by **GitHub Actions** and a **basic `.gitignore`** file suitable for Java and Maven projects.

The goal of this template is to provide a solid starting point to quickly build, package, and deploy AWS Lambda functions through an automated and customizable workflow.

---

## Getting Started

These are some basic steps you should follow when using this template:

1. **Add missing attributes to the `pom.xml` file**  
   Make sure to include the following Maven attributes if they are not already defined:
   ```xml
   <groupId>your.group.id</groupId>
   <artifactId>your-artifact-id</artifactId>
   ```
   These values identify your project within Maven and should follow your organization’s naming conventions.

2. **Set the Java version**
   By default, this template uses **Java 21**.  
   You can change it if necessary.

   Update the version both in:

   - The `pom.xml` file (under `<maven.compiler.source>` and `<maven.compiler      target>`).
   - The GitHub Actions workflow file:  
   `.github/workflows/deploy-by-tag.yml`.

   Example snippet for `pom.xml`:

   ```xml
   <properties>
   <maven.compiler.source>21</maven.compiler.source>
   <maven.compiler.target>21</maven.compiler.target>
   </properties>
   ```

   Example snippet for `deploy-by-tag.yml`:
   ```yaml
    env:
      AWS_REGION: eu-north-1
      JAVA_VERSION: 21
   ```

3. **Add or modify dependencies**
   Update the `pom.xml` file to include any dependencies required by your Lambda functions.
   Use the standard Maven dependency syntax:

   ```xml
    <dependencies>
        <dependency>
            <groupId>com.example</groupId>
            <artifactId>example-lib</artifactId>
            <version>1.0.0</version>
        </dependency>
    </dependencies>
   ```

4. **Configure GitHub Secrets**

   To allow GitHub Actions to deploy your Lambda functions to AWS, you must add the    following secrets in your repository’s  
   **Settings > Secrets and variables > Actions** section:

   - `AWS_ACCESS_KEY_ID`  
   - `AWS_SECRET_ACCESS_KEY`

   These credentials should belong to an AWS IAM user with sufficient permissions to    deploy and manage Lambda functions.






