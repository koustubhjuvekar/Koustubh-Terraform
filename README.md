# 📘 Terraform - My Guide

<details>
  <summary>🚀 Terraform Installation</summary><br>

  <details>
    <summary>1️⃣ Installation of Terraform on EC2</summary><br>

    1. **Launch an EC2 instance**  
       - Here we are using **AWS as a Cloud Provider**.  
       - Launch an **Ubuntu EC2 instance** from AWS Console.  
       
       <img width="884" height="469" alt="image" src="https://github.com/user-attachments/assets/dcc1f302-9a71-49c6-abff-d9a9567f6d26" />

    2. **Update the package list**
       ```bash
       sudo apt update && sudo apt upgrade -y
       ```

    3. **Install required packages**
       ```bash
       sudo apt install -y wget unzip
       ```

    4. **Download Terraform**
       ```bash
       wget https://releases.hashicorp.com/terraform/1.8.5/terraform_1.8.5_linux_amd64.zip
       ```

    5. **Unzip and move binary**
       ```bash
       unzip terraform_1.8.5_linux_amd64.zip
       sudo mv terraform /usr/local/bin/
       ```

    6. **Verify installation**
       ```bash
       terraform -v
       ```

  </details>

  <details>
    <summary>2️⃣ Installation of Terraform on Visual Studio Code</summary><br>

    1. **Install Visual Studio Code**  
       - Download from 👉 [VS Code Official Website](https://code.visualstudio.com/)  

    2. **Install Terrafo**
