# l337_5ub0v3r: A Fast Tool To Check Subdomain Takeover Vulnerability
![Banner](banner.png)

## What is l337_5ub0v3r
l337_5ub0v3r is a tool written in python which is used to check possibility of subdomain takeover vulnerability and it is fast as it is asynchronous.

## Why
During recon process you might get a lot of subdomains(e.g more than 10k). It is not possible to test each manually or with traditional requests or urllib method as it is very slow. Using <b>l337_5ub0v3r</b> you can automate this task in much faster way. l337_5ub0v3r uses <b>aiohttp/asyncio</b> which makes this tool asynchronous and faster.

## How it works
l337_5ub0v3r uses subdomains list from text file and checks for url of <b>404 Not Found</b> status code and in addition it fetches <b>CNAME</b>(Canonical name) and removes those URL which have target domain name in CNAME. It also combines result from <b>subfinder</b> and <b>sublist3r</b>(subdomain enumeration tool) if you don't have target subdomains as two is better than one. But for this sublist3r and subfinder tools must be installed in your system. l337_5ub0v3r is able to check <b>7K</b> subdomains in less than 5 minutes.

## Key Features:
```
- Fast (as it is asynchronous)
- Uses two more tools to increase efficiency
- Saves result in a text file for future reference
- Umm thats it, nothing much !
```
## How to use:
<b>Note: Only works on Python3.7+</b>

- git clone https://github.com/abhinandan-khurana/l337_5ub0v3r.git
- Install dependencies: pip install -r requirements.txt
- Install [Subfinder](https://github.com/projectdiscovery/subfinder) (optional)
- Install [Sublist3r](https://github.com/aboul3la/Sublist3r) (optional)
- python3 l337_5ub0v3r.py -h 

### Using docker
As an alternative, it is also possible to build a Docker image, so no prerequisites are necessary.
```
$ docker build -t sub404 .
$ docker run --rm sub404 -h
```

## Usage example:

<b>Note: If subfinder and sublist3r is installed.</b><br>
This combines result from sublist3r and subfinder tool and checks for possibility of takeover.<br>
<code>$ python3 l337_5ub0v3r.py -d anydomain.com</code>


<br><br><br>
<b> - If subfinder and sublist3r is not installed, provide subdomains in text file</b><br>
<code>$ python3 l337_5ub0v3r.py -f subdomain.txt</code><br><br>
<!-- ![Example](https://github.com/r3curs1v3-pr0xy/sub404/blob/master/example.png) -->
![Example](example1.png)
## Note:
<b>This tool is mostly tested in linux but should works on other OS too.</b>
## Usage options:
```
$ python3 l337_5ub0v3r.py -h
```
This will display help for the tool. Here are all the switches it supports.


|Flag |                Description                                             |                       Example                            |
|-----|------------------------------------------------------------------------|----------------------------------------------------------|
|  -d  | Domain name of the target.                                                | python3 l337_5ub0v3r.py -d noobarmy.org                     |
| -f   | Provide location of subdomain file to check for takeover if subfinder is not installed. | python3 l337_5ub0v3r.py -f subdomain.txt|
| -p | Set protocol for requests. Default is "http".| python3 l337_5ub0v3r.py -f subdomain.txt -p https or python3 l337_5ub0v3r.py -d noobarmy.org -p https|
| -o | Output unique subdomains of sublist3r and subfinder to text file. Default is "uniqueURL.txt" | python3 l337_5ub0v3r.py -d noobarmy.org -o output.txt|
| -h | show this help message and exit | python3 l337_5ub0v3r.py -h|

## Note:
```
This tool fetches CNAME of 404 response code URL and removes all URL which have target domain in CNAME. So chances of false positives are high.
```

## Contributing to l337_5ub0v3r:
```
- Report bugs, missing best practices
- DM me with new ideas
- Help in Fixing bugs
```
## My Twitter:
<b>Say Hello [L0u51f3r007](https://twitter.com/L0u51f3r007/)

## Credits:
[Ice3man543](https://github.com/Ice3man543) - Projectdiscovery's subfinder tool is used to enumerate subdomains<br>
[aboul3la](https://github.com/aboul3la) - aboul3la's sublist3r tool is used to enumerate subdomains

## Current version is 1.0