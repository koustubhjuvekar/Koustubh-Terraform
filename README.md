# 📘 Terraform - My Guide

<details>
  <summary>🚀 Terraform Installation</summary><br>

  <details>
    <summary>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1️⃣ Installation of Terraform on EC2</summary>
    
    - Step 1: Update the package list  
      ```bash
      sudo apt update && sudo apt upgrade -y
      ```
    - Step 2: Install required packages  
      ```bash
      sudo apt install -y wget unzip
      ```
    - Step 3: Download Terraform  
      ```bash
      wget https://releases.hashicorp.com/terraform/1.8.5/terraform_1.8.5_linux_amd64.zip
      ```
    - Step 4: Unzip and move binary  
      ```bash
      unzip terraform_1.8.5_linux_amd64.zip
      sudo mv terraform /usr/local/bin/
      ```
    - Step 5: Verify installation  
      ```bash
      terraform -v
      ```

  </details>

  <details>
    <summary>2️⃣ Installation of Terraform on Visual Studio Code</summary>

    - Step 1: Install **Visual Studio Code** → [Download VS Code](https://code.visualstudio.com/)  
    - Step 2: Install **Terraform extension**  
      - Open VS Code  
      - Go to **Extensions** (Ctrl+Shift+X)  
      - Search for **HashiCorp Terraform**  
      - Install the extension  
    - Step 3: Verify Terraform is installed on your system (`terraform -v`)  
    - Step 4: Create `.tf` files and start writing configurations in VS Code  

  </details>

</details>
