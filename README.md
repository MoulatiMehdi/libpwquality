# PAM PWQuality Fix

This repository contains a custom-built version of the pam_pwquality.so module designed to address an issue where passwords shorter than 4 characters are not checked for the presence of the username. This fix ensures stricter password validation in compliance with security requirements.

# Purpose

The default behavior of pam_pwquality allows passwords containing the username if they are less than 4 characters long.
This repository provides a fixed binary to replace the default pam_pwquality.so module, preventing this behavior.
it will ensure that the name of the username isnt in the password regardless of the length.

# Installation Instructions

## Clone the repository:
```shell
    git clone https://github.com/MoulatiMehdi/libpwquality.git
    cd libpwquality
```
## make a Backup: **Ensure the existing pam_pwquality.so file is backed up**:

```shell
	sudo mv /lib/x86_64-linux-gnu/security/pam_pwquality.so /lib/x86_64-linux-gnu/security/pam_pwquality.so.bak
	
```
Then replace it with the new file:

```shell
  	sudo cp pam_pwquality.so /lib/x86_64-linux-gnu/security/
```
## Verify the changes: Test the password validation behavior to ensure the fix works as expected.

# Notes

    This fix assumes the default username length check behavior of pam_pwquality and modifies it to ensure stricter validation.

# Disclaimer

This binary is provided as-is. **Use it at your own risk**. 

For any issues or further assistance, feel free to raise an issue in the repository.



