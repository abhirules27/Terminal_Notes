# Terminal_Notes
Codes for fast usage of Terminal in Kali LInux

# Banner Grabbing after doing NMAP
$ nmap -p- --min-rate=1000 -T4 10.10.10.161 > Forest.nmap

Getting Port No only from Forest.nmap
$ cat Forest.nmap | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//
Output: 53,88,135,139,389,445,464,593,636,3268,3269,5985,9389,47001,49664,49665,49666,49667,49671,49676,49677,49684,49703,49959

Banner Grabbing
nmap -sV --script=banner -p53,88,135,139,389,445,464,593,636,3268,3269,5985,9389,47001,49664,49665,49666,49667,49671,49676,49677,49684,49703,49959 10.10.10.161

