# Configuring Git Credential Manager on Linux

## Install Git Credential Manager (GCM)
Before configuring Git Credential Manager, ensure it is installed on your system. You can install it from your package manager or download it from the [official GitHub repository](https://github.com/git-ecosystem/git-credential-manager).

## Verify Installation
Once installed, confirm that Git Credential Manager is available by running:
```bash
git-credential-manager --version
```
If installed correctly, this command will display the installed version.

## Configure Credential Store
To securely store your credentials, you need to configure the credential store.

### Setting the Credential Store
On Linux, the default storage option is `secretservice`. Configure it with:
```bash
git config --global credential.credentialStore secretservice
```

### Verify the Credential Store
Ensure that the credential store is set correctly by running:
```bash
git config --global credential.credentialStore
```
This should output:
```bash
secretservice
```

## Store Credentials
Now that the credential store is configured, you can securely save your credentials.

Run the following command to store credentials manually:
```bash
git-credential-manager store
```

### Enter Credential Information
When prompted, enter your GitHub credentials in the following format:
```bash
protocol=https
host=github.com
username=<your-username>
password=<your-personal-access-token>
```
Press **Enter** after inputting the credentials to save them.

## Confirm Configuration
To check if credentials are stored correctly, try cloning a private repository or running:
```bash
git credential reject https://github.com
```
If properly configured, Git should now authenticate automatically without prompting for credentials.
