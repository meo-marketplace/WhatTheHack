# Challenge 08 - Authenticating with marketplace APIs - Coach's Guide 

[< Previous Solution](./Solution-08.md) - **[Home](./README.md)** - [Next Solution >](./Solution-10.md)

## Notes & Guidance

### Check point: 
**CONFIRM** that the student has turned on **Requires Auth** in the Emulator, set in the Config page.

The challenge creates a second app registration and adds values to the .env file.

In the Azure portal the student will need to create a new **App Registration**, in Active Directory:
- create as Single tenant
- in Certificates and secrets create a new client secret - copy this to the `.env` file
- copy the **Application (client) ID** to the `.env` file


**Troubleshooting:**
If the authentication fails and the solution is configured correctly **and** the student is using WSL check the time on the WSL clock, type `date` in the WSL terminal.
If the WSL clock is out of sync with the Windows clock run the following command in the WSL terminal:
`sudo hwclock -s`. Check the time again with `date` and retry the authentication.