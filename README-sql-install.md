# MySQL Installation Guide

### 1. Visit MySQL Website
Go to the official MySQL download page: [MySQL Installer](https://dev.mysql.com/downloads/installer/).

### 2. Choose MySQL Installer
On the download page, select "MySQL Installer for Windows."  
You'll have two options:
- **Web Community** (smaller file, downloads components during installation)
- **Full** (larger file, includes all features)

It's recommended to download the Full installer to avoid issues with internet connectivity during installation.

### 3. Download the Installer
After choosing the installer, click "Download."  
You might be prompted to sign up for an Oracle account. You can bypass this by clicking "No thanks, just start my download."

### 4. Run the Installer
Once downloaded, open the `.msi` file to start the installation process.  
You may need administrative privileges to run the installer.

### 5. Follow the Setup Process

### Choose Setup Type
Select the setup type that best suits your needs:
- **Developer Default:** Installs MySQL server, MySQL Workbench, MySQL Shell, and other developer tools.  **(choose this)**
- **Server Only:** Installs only the MySQL server.
- **Client Only:** Installs client applications like MySQL Workbench and MySQL Shell.
- **Full:** Installs all components.
- **Custom:** Lets you choose exactly what to install.

### Install the Selected Products
Click "Execute" to install the selected components.

### Configuration
After installation, you'll be prompted to configure MySQL.

### 6. MySQL Configuration

### Server Configuration
Choose the type of MySQL server:
- **Standalone MySQL Server:** For a single machine.  **(choose this)**
- **Clustered MySQL Server:** For multiple machines (more advanced setup).

### Type and Networking
Choose the server type:
- **Development Machine:** Configures MySQL for a less resource-intensive setup. **(choose this)**
- **Server Machine:** Standard setup for a server environment.
- **Dedicated MySQL Server:** Optimizes MySQL for a dedicated server.

### Authentication Method
Choose the authentication method for MySQL.

### Root Password
Set a root password. You can also add additional users.

### Windows Service
Configure MySQL to run as a Windows service (recommended). This allows MySQL to start automatically when Windows starts.

### 7. Complete Installation
After configuration, click "Finish" to complete the installation process.

# Setting Up Environment Variables

### 8. Set Up MySQL Environment Variable

1. **Open System Properties:**
   - Right-click on "This PC" or "My Computer" and select "Properties."
   
2. **Advanced System Settings:**
   - In the System Properties window, click on "Advanced system settings" on the left side.
   
3. **Environment Variables:**
   - Click on the "Environment Variables" button.

4. **Add MySQL to Path:**
   - Under "System variables," find the "Path" variable and select "Edit."
   - Click "New" and add the path to the MySQL bin directory. This is typically `C:\Program Files\MySQL\MySQL Server 8.0\bin`.
   - Click "OK" to save the changes.

### 9. Verify MySQL Installation

1. **Open the Command Prompt:**
   - Type `cmd` in the Windows search bar and hit Enter.

2. **Verify Installation:**
   - Type `mysql --version` to verify the installation. It should display the installed MySQL version.

### 10. Open MySQL in CMD

1. **Log into MySQL via Command Prompt:**
   - Open CMD.
   - Type `mysql -u root -p` and hit Enter.
   - You’ll be prompted to enter the root password you set during the installation.

2. **Access the MySQL Shell:**
   - Once entered, you’ll have access to the MySQL shell where you can start executing MySQL commands.

