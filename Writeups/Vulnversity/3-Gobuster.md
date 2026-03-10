# Vulnversity – Task 3: Compromise the Webserver

In this task, we need to brute-force directories on the target webserver to find the upload page.

## Command Used

```bash
gobuster dir -u http://MACHINE_IP:3333 -w /usr/share/wordlists/dirb/common.txt
```
Command Breakdown
Part	What It Means
- gobuster-	The tool we're using for brute-forcing
- dir-	Directory/file brute-forcing mode
- -u-	Target URL (add the machine IP after this flag)
- -w-	Path to the wordlist (contains common directory names to try)
What This Command Does
This command will:

Take each word from the common.txt wordlist

Append it to the target URL (http://MACHINE_IP:3333/)

Send a request to each generated URL

Report back any that return a valid response (like 200 OK)
