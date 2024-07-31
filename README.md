# Warper Installation Guide on WSL for Windows
Welcome to the Warper installation guide! This document will walk you through the seamless steps to install Warper, a powerful command-line tool, on WSL (Windows Subsystem for Linux) for Windows because he  currently does not support native **Windows installation**.

## What is Warper?

Warper is a modern terminal reimagined to boost developer productivity with advanced features. Built with Rust he offers:

- **Modern Editing** -🖥️: Command editing similar to an IDE, with features like inserting, copying, selecting, and smart completions.

- **Warp AI** 🧠: Integrated AI for command suggestions and troubleshooting.

- **Warp Drive** 💽 : Organize and reuse terminal workflows with ease.

 - **Custom Themes** 🎨: Personalize the terminal's appearance.


### Why Use Warper Instead of a Normal Command Line?

Warper provides several enhancements over a traditional command line, such as:

- **Faster Command Input** 🚀: Modern editing tools and smart completions.

- **Increased Efficiency** ⚡: Reusable workflows and command recall.

- **Team Collaboration**  🤝: Shared terminal knowledge and collaborative tools.

- **User-Friendly Features** 🌟: Improved navigation, error highlighting, and auto-suggestions.

For more details, visit [Warp](https://www.warp.dev/) or watch this [demo](https://youtu.be/34INSNevPOk) to explore more.

## ⚙️ Prerequisites

Before you begin, ensure that you have the following prerequisites installed and configured:

- **Windows 10 or 11**: Make sure you are running Windows 11.

- **WSL (Windows Subsystem for Linux)**: WSL should be installed and configured on your system. 

   - **If you haven't installed WSL yet**, follow these steps:
     1. Open PowerShell as an administrator.
     2. Run the command:
        ```sh
        wsl --install
        ```
     3. Restart your computer if prompted.
     4. Set up your Linux distribution by following the on-screen instructions.
   
   - **If WSL is already installed**, you can verify its installation by running the following command in PowerShell:
     ```sh
     wsl --list --verbose
     ```
     This command will list all installed distributions and their status like this : 
      ![image](https://github.com/user-attachments/assets/aca36911-ad89-47f1-b700-148c5dc63469)


- **Ubuntu on WSL** 📦: It's recommended to use the Ubuntu distribution on WSL for this installation.
   - **If you haven't installed Ubuntu yet**, follow these steps:
       1. Open the Microsoft Store.
       2. Search for "Ubuntu" and select the desired version.
       3. Click "Get" to install the distribution.
          
       ![install Ubuntu microsoft ](https://github.com/user-attachments/assets/8dd24752-3b9e-46d9-b66d-9c05446b5b8d)

       5. Launch Ubuntu from the Start menu and complete the initial setup.
       6. 
- **XLaunch**: XLaunch should be installed for running GUI applications on WSL.

   - **To install XLaunch**, follow these steps:
     1. Download XLaunch from the [Xming website](https://sourceforge.net/projects/xming/).
     2. Run the installer and follow the on-screen instructions.
     3. During the setup, select "Multiple windows" and "Start no client".
     4. Once installed, launch XLaunch from the Start menu.
        
  ## 📥 Installation Steps
  
  ➡️ **Upgrade Ubuntu Packages**: Open your WSL terminal and run the following commands to update your package lists and upgrade your existing packages to the latest version:
     
   ```
   sudo apt update
   sudo apt upgrade -y
   ```
  ➡️ **Download Warper**: From your Windows environment, download the Linux version of Warper from the official [Warper website](https://www.warp.dev/) .

  ➡️ **Access Windows Downloads from WSL**: In your WSL terminal, navigate to the Windows Downloads folder:

  ```
  cd /mnt/c/Users/<YourUsername>/Downloads
  ```
  ➡️ **Install Warper**:  download the `.deb` version of Warper because he is easy to install it just with the following command : 
  ```
  sudo dpkg -i warper-linux.deb
  ```
  🚨 Attention: If you encounter any issues during installation, it may be due to missing dependencies. The error message will indicate which additional packages are required. You can resolve this by running:
  ```sh
   sudo apt-get install -f
   ```
  ➡️ Configure XLaunch : If XLaunch is not working after installation and you need to run Warper on WSL, you may need to configure the display settings. Follow these steps:
    1. Open your `.bashrc` file in a text editor:
       ```
       nano ~/.bashrc
       ```
    2. Add the following line to export the display environment variable:
    ```
    export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0.0
    ```
    3. Save and close the file (in nano, press `Ctrl + X`, then `Y`, and `Enter`).
  
    4. Reload your `.bashrc` file to apply the changes
    ```
    source ~/.bashrc
    ```
    ##  🏃 Running Warper : 

    After you have installed Warper, follow these steps to run it:
    
    1. Make sure XLaunch is running. You can start XLaunch from the Windows Start menu.
    
    2. Open your WSL terminal.
    
    3. Run Warper by entering the following command:
       ```sh
       warper
       ```

    


   

          

