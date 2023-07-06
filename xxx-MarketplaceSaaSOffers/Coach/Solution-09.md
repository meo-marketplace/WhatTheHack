# Challenge 09 - <Title of Challenge> - Coach's Guide 

[< Previous Solution](./Solution-08.md) - **[Home](./README.md)** - [Next Solution >](./Solution-10.md)

## Notes & Guidance


**Troubleshooting:**
If the authentication fails and the solution is configured correctly **and** the student is using WSL check the time on the WSL clock, type `date` in the WSL terminal.
If the WSL clock is out of sync with the Windows clock run the following command in the WSL terminal:
`sudo hwclock -s`. Check the time again with `date` and retry the authentication.