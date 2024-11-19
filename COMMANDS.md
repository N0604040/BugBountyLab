## Recon

subfinder -d `example.com` -o `subfinder:example.com` -all

httpx -l `subfinder:example.com` -sc -cl -ct -title -fc 301,302,307,308 -silent | awk -f `~/AwkScripts/httpx-general.awk` | sort
<br>
httpx -l `subfinder:example.com` -sc -ct -fr -silent | awk -f `~/AwkScripts/httpx-redirects.awk` | sort

ffuf -w `wordlist.txt` -u `https://FUZZ.example.com`
<br>
ffuf -w `wordlist.txt` -u `https://www.example.com` -H `"Host: FUZZ.example.com"`

katana -u `scope.txt` -o `katana.txt` -d 5 -jc
