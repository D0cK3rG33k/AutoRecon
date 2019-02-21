# AutoRecon
![Banner](https://image.noelshack.com/fichiers/2019/03/5/1547806549-ti-banner.png)![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg) ![made-with-bash](https://img.shields.io/badge/Made%20with-Bash-1f425f.svg)  ![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)

## Features
- Enum subdomains with [Amass](https://github.com/OWASP/Amass/), [Sublist3r](https://github.com/aboul3la/Sublist3r), [Crtsh](http://crt.sh/) & [Certspotter](https://certspotter.com/)
- Combination of results, check with [MassDNS](https://github.com/blechschmidt/massdns)
- Check for TakeOver with [Subjack](https://github.com/haccer/subjack) & [TkoSubs](https://github.com/anshumanbh/tko-subs)
- Find JS files & find endpoints with [LinkFinder](https://github.com/GerbenJavado/LinkFinder)
- WAF detection with [WafW00f](https://github.com/EnableSecurity/wafw00f)
- Scan with [Aquatone](https://github.com/michenriksen/aquatone) 
- Creation of an archive and upload with unique link on Transfer.sh

![Workflow](https://image.noelshack.com/fichiers/2019/08/4/1550767106-autorecon.png)

## Installation
- Installation tested on Debian 9 / Kali 2018.4
- Recon tested on Debian 9 / Kali 2018.4 & 2019.1 / Arch linux (Manjaro 18.x)

Requierement : [Golang](https://golang.org/doc/install)
```bash
git clone https://github.com/JoshuaMart/AutoRecon
cd AutoRecon
```
Edit the following variables on install.sh & create ToolsDir directories :
```bash
ToolsDIR="/root/Recon/Tools" #Directory where tools was installed
GoPath="/root/go" #Your Go Workspace
```
And the following variables on recon.sh :
```bash
ToolsDIR="/root/Recon/Tools" #Directory where tools was installed
ResultsPath="/root/Recon" #Directory where you want scans results
AquatonePorts="small" #Aquatone option, see his options
TransferSH="https://transfer.sh" #Change this if you have you own transfer.sh
subjackDebug="/root/go/src/github.com/haccer/subjack/fingerprints.json" #Subjack bug without this ...
```
Run installer :
```bash
./install.sh
```
## Usage

```bash
./recon.sh -d domain.tld -a -u
```
![screen](https://image.noelshack.com/fichiers/2019/08/2/1550585488-2019-02-19-15-10-37-mremoteng-confcons-xml-debian-light.png)

Options :
```bash
-d | --domain (required) : Launch passive scan (Passive Amass, Aquatone, Subjack, TkoSubs)
-a | --active (optional): Launch active scans (Active Amass, Sublist3r LinkFinder, Aquatone)
-u | --upload (optional): Upload archive on Transfer.sh
```