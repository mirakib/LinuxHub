<h1 align="center">Terraform Upgrade</h1>

<h3 align="center">Windows</h3>

#### `Note: Run PowerShell as Administrator`
1. If you don’t have Chocolatey:

    ```Powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force
    iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
    ```

 - Then install Terraform:

    ```Powershell
    choco install terraform -y
    ```

 - To see installed version:

    ```Powershell
    terraform -version
    ```

2. If you have Chocolatey:

    ```Powershell
    choco upgrade terraform -y
    ```
 - To see installed version:

    ```Powershell
    terraform -version
    ```


### If Chocolatey is broken

If choco command fails (corrupted install), follow this clean fix:

1. Backup old installation:
   
    ```Powershell
   Copy-Item -Recurse -Force "C:\ProgramData\chocolatey" "C:\ProgramData\choco-backup"
    ```

3. Remove broken install:
   
    ```Powershell
   Remove-Item -Recurse -Force "C:\ProgramData\chocolatey"
    ```

5. Reinstall Chocolatey:
   
   ```Powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force
   iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```

6. Reinstall Terraform:
   
    ```Powershell
   choco install terraform -y
    ```
