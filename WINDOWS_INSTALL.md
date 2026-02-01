# Installation Instructions for Windows (PowerShell & VS Code)

This guide describes how to install this version of `gimme-aws-creds` with WebAuthn support on Windows, using PowerShell and VS Code.

## Prerequisites

*   **Python 3.10+**: Ensure Python is installed and added to your PATH. Verify by running `python --version` in PowerShell.
*   **VS Code**: Installed and ready.
*   **PowerShell**: Default shell in VS Code terminal.

## Installation Steps

1.  **Open the Project in VS Code**
    *   Launch VS Code.
    *   Open the folder containing the `gimme-aws-creds` repository.

2.  **Open a Terminal**
    *   Press `` Ctrl + ` `` (backtick) or go to **Terminal > New Terminal**.
    *   Ensure the terminal is using **PowerShell**.

3.  **Create a Virtual Environment**
    *   Run the following command to create an isolated Python environment named `venv`:
        ```powershell
        python -m venv venv
        ```

4.  **Activate the Virtual Environment**
    *   Run the activation script:
        ```powershell
        .\venv\Scripts\Activate.ps1
        ```
    *   *Note:* If you see an error about script execution policies, you may need to run this command first (requires Admin privileges, or scope to Process):
        ```powershell
        Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
        ```
    *   Once activated, you should see `(venv)` at the start of your prompt.

5.  **Install gimme-aws-creds**
    *   Install the package from the current source directory:
        ```powershell
        pip install .
        ```
    *   This will automatically install dependencies, including `ctap-keyring-device` which is required for WebAuthn support.

6.  **Verify Installation**
    *   Check that the tool is installed and accessible:
        ```powershell
        gimme-aws-creds --version
        ```
    *   You should see the version number output.

## Using WebAuthn

With this version, WebAuthn support is enabled for Windows Python 3.10+. When prompted for MFA, you can now select **WebAuthn** and touch your security key (e.g., YubiKey) when requested.
