**01.10.2015**
* download bug fix, in some PCs consume too much CPU
* now you can specify in config which AV engines you prefer
	* engines = AVG, etc, for correct engine name look on VT page or -V will show all engines result with correct av names 

**23.09.2015**

* -V, --version - option to show script version
* download bug fixed if you have access to intelligence but not private api

**16.09.2015**
* --hashes is alias for all in one - (un)detected downloaded, (un)detected referred and (un)detected communicated

**08.09.2015**

* -nm or --name for download, to save with that name

**05.09.2015**
* In --return-all-info added
    * --ITW-urls options
    * --compressedview option
    * --submission_name option
    * --detailed-email-parents - contains info about all emails related to that hash
* Now to see all info in allinfo(--return-all-info) use -v for verbose mode, as detections, hashes, and few other data will not shoved by default

**03.09.2015**

* Intelligence search support with -si or --search-intelligence
* Get comments(-gc) now support url as parameter 

**01.08.2015**

* Big code update
* new --as-owner option
* Team cymru asn data removed, as vt provide it now
* Can be used as library, value must be as list:
	* return_raw parameter will return original raw response json 
	* Example:
		* vt.getIP(**{'value': ['8.8.8.8'],'return_raw':True})
	* return_json will return only data what you specify, as for example passive_dns, asn, etc
	* Example: 
		* vt.getDomain(**{'return_json':True, 'asn':True, 'passive_dns':True, 'value':['google.com']})

**25.07.2015**

* Private api download bugfix
* Url parameter now reconize correctly in download
* Some other bug fixes

**18.04.2015**

* Team-Cymru ASN info, now apart of number will show data, example:
* [+] TEAM-CYMRU ASN details:
	15169 - US - arin - 2000-03-30 - GOOGLE - Google Inc.,US

**17.04.2015 - added new domain and ip options, other new stuff soon**
* detected-referrer-samples
* undetected-referrer-samples
* whois
* whois-timestamp
* passive-dns
* asn
* country
* subdomains
* domain-siblings
* categories
* alexa-cat
* alexa-rank
* opera-info
* drweb-cat
*

**31.05.2015:**
* Support downoad by passsing link of sample
	* Example: `vt --download https://www.virustotal.com/en/file/<hash_here>/analysis/`

**02.04.2015:**
* Download from VT intelligence 

**24.03.2015:**
* -dds, --detected-downloaded-samples now works correctly
* -wh, --whois added
* requests InsecureRequestWarning: Unverified HTTPS request is being made - disabled


**15.12.2014:**
* Now doesn't matter if you put -d or -i for domain/ip, it will catch it correctly :)
  * Example: -d 127.0.0.1 it will be passed to ip not to domain, and vice versa 

**11.10.2014:**

* Big upgrade, with bug fixes, code cleaning, a lot of improvement
* Now you can have file with list of hashes to download, or pass them as param
* Domain walk - will get all ips and check information about them
* Private api improvement and full support, before was hardcoded 4 items to check, now if you have private api will check up to 25 items in only one petition
* You can pass more then 4 url/hashes to check with your public api, it will do it with waiting before every 4 petition, the same for private api but between 25 petitions
* Can retrieve information about many domain/ips, now you don't need bash loop or check one by one :)
* etc

PS I will try to document all tricks of using of this script, when I will have a bit of time

**04.08.2014:**

* Ip search (-i) now can be used scheme search like this http://ip, urlparse will extract domain
* Windows expand user home support added, thanks to @truekonrads

**28.07.2014:**

* Search bug fixed
* Domain search (-d) now can be used scheme search like this http://domain.com, urlparse will extract domain

**26.06.2014:**

* Now show file name when scan/search file
* In file-search option can now be used md5 hash
* Rescan option now support wildcard, for example samples/*, will generate file hash on the fly

**29.04.2014:**

* Bug fix related with csv dumps

**23.03.2014:**

* Table improvement, now result show is more prettiest, column sizes adjustment

**12.03.2014:**

* Added option --csv, which permit dump AVs result into csv file

* Now AVs results are sorted from a to z, to help found more quickly searched AV result

* Added AV version and Last AV signature update

**09.03.2014:**

* Added posibility to scan urls passed in file, filename must be urls_for_scan.txt and one url per line.

  Execution as arg: vt.py -u/-ur urls_for_scan.txt

* Removed limits for 4 urls only with public api

**20.11.2013 Updates:**

* Small bug fixed, when internet connection doesn't work correctly

* Added option for file(s) search, without submitting file.
Now you don't need to get hash of file and search it in VT if you just want to get the report, check option -fs/--file-search

* In search without verbose mode now if someone/all of Kaspersky/Sophos/TrendMicro
don't have results, you will see detections by others engines

**16.11.2013 Updates:**

* Code optimization/cleaning, and small print fix

**15.11.2013 Updates:**

* Added support for get apikey from file, now you can put is as before into apikey value at line 1409 or put it to config file
if api key not in value , will check by default ~/.vtapi, but you can put it to another file and use -c/--config-file option

* Limit reached issue patched
