# Gobuster – Directory & Subdomain Brute-Forcing Tool

Gobuster is a tool used for brute-forcing. It can discover:

- **Directories and files** using the `dir` mode  
- **Subdomains** using the `dns` mode  

We provide the target URL with the `-u` flag and a wordlist (e.g., `common.txt`, `medium.txt`, `big.txt`) with the `-w` flag. Extensions can be added with `-x` to append to each word, and speed can be increased using the `-t` (threads) flag.

---

## Directory Brute-Force Example

```bash
gobuster dir -u http://testphp.vulnweb.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,html -t 50
```
Breakdown:
gobuster – the tool

dir – directory/file brute-forcing mode

-u – target URL (e.g., http://testphp.vulnweb.com)

-w – path to the wordlist (e.g., directory-list-2.3-medium.txt)

-x – extensions to try with each word: php, txt, html

-t 50 – number of threads (sends 50 requests simultaneously for faster scanning)

What it does:
This command brute-forces directories using the medium.txt wordlist, appending .php, .txt, and .html to each word, and sends 50 requests at a time.

Subdomain Brute-Force Example
```bash
gobuster dns -d example.com -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -t 20
```
Breakdown:
gobuster – the tool

dns – subdomain brute-forcing mode

-d – target domain (e.g., example.com)

-w – path to the subdomain wordlist

-t 20 – number of threads (sends 20 requests at once)

What it does:
This command brute-forces subdomains using the subdomains-top1million-5000.txt wordlist, sending 20 requests at a time.
