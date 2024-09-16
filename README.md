
# WSL Development Environment Setup

This repository provides an Ansible playbook to automate the setup of a development environment in **WSL (Windows Subsystem for Linux)** with Ubuntu. The playbook installs common development tools such as Node.js, Java, Python, and utilities like Zsh, tmux, and htop.

## Prerequisites

Before running this playbook, ensure that you have the following:

1. **WSL**: Windows Subsystem for Linux installed with Ubuntu (or another supported distribution).
2. **Ansible**: Installed in your WSL environment.

Follow the steps below to set everything up.

---

## Step 1: Install WSL on Windows

If you haven't installed WSL yet, follow these instructions to set up WSL with Ubuntu on Windows:

1. **Open PowerShell as Administrator**.
2. Run the following command to enable WSL:

   ```powershell
   wsl --install
   ```

   This will install WSL and Ubuntu by default. You can install another distribution if preferred.

3. Once the installation is complete, restart your system.

4. Launch **Ubuntu** from the Start Menu and complete the initial setup (username, password).

---

## Step 2: Install Ansible in WSL

Once Ubuntu is installed and set up, open your WSL terminal and install Ansible:

1. Update your package list and install Ansible:

   ```bash
   sudo apt update
   sudo apt install ansible -y
   ```

2. Verify that Ansible is installed by checking the version:

   ```bash
   ansible --version
   ```

---

## Step 3: Clone this Repository

Next, clone this repository to your WSL environment:

```bash
git clone https://github.com/<your-username>/wsl-dev-setup.git
cd wsl-dev-setup
```

---

## Step 4: Run the Ansible Playbook

Now you're ready to run the Ansible playbook to set up your development environment:

```bash
ansible-playbook wsl_dev_setup.yml --connection=local
```

The playbook will:

- Update your system.
- Install common utilities (git, curl, wget).
- Install **Java (OpenJDK 11)**.
- Install **Node.js** and build tools.
- Install **Python3** and **pip**.
- Install **Zsh** with **Oh My Zsh**.
- Install other useful tools like **tmux**, **htop**, and more.

---

## Step 5: Optional Customization

You can customize the playbook to fit your specific needs. For example, you can install additional tools, change the Node.js version, or add custom configuration steps.

---

## Conclusion

By following these steps, you'll have a fully set-up development environment in WSL with Ubuntu, Node.js, Java, Python, and many other tools. You can easily re-run the playbook in the future to update or modify your setup.

---

## Troubleshooting

If you encounter any issues, make sure that:

- Your WSL installation is up to date (run `wsl --update` in PowerShell).
- You have the correct permissions to run Ansible with `sudo`.
- All tasks in the playbook have completed successfully.
