# WebApp-Sec-Resources
I needed a place to collect all tools, resources, tutorial about web application security and testing. This is my way.



<h1>Subdomain enumeration</h1>

<h2>Lists</h2>
<ul>
  <li>https://github.com/jhaddix/SecLists/tree/master/Discovery/DNS</li>
  <li>https://github.com/caffix/amass/tree/master/wordlists</li>
  <li>https://github.com/danielmiessler/RobotsDisallowed</li>
</ul>

<a href="https://github.com/aboul3la/Sublist3r"><h2>Sublist3r</h2></a>
<pre>python sublist3r.py -d domain.com -o domain_report_sublist3r.txt</li></pre>


<a href="https://github.com/OJ/gobuster"><h2>Gobuster</h2></a>
<pre>gobuster -u domain.com -fw -m dns -v -w list.txt -o domain_report_gobuster.txt</pre>


<a href="https://github.com/jhaddix/domain"><h2>enumall.sh</h2></a>
<pre>./enumall.py domain.com</pre>


<a href="https://github.com/blechschmidt/massdns"><h2>MassDNS</h2></a>
<pre>Not tested yet</pre>


<a href="https://github.com/vysec/DomLink"><h2>DomLink</h2></a>
<pre>python domLink.py -D domain.com -o domlink_report_domain.txt</pre>


<a href="https://github.com/caffix/amass"><h2>Amass</h2></a>
<pre>amass -d domain.com</pre>
Lists can be found <a href="https://github.com/caffix/amass/tree/master/wordlists">here</a>


<a href="https://youtu.be/Qw1nNPiH_Go?t=22m50s"><h2>Burp Suite</h2></a>
<ul>
  <li>Scanner -> Live scanning -> Live Passive Scanning -> Don't scan</li>
  <li>Spider -> Options -> Form submission -> Don't submit forms or Prompt for guidance</li>
  <li>Target -> Scope -> "Use advanced scope control" and -> Add -> Host field -> Domain name (eg if it is example.com i use "example" keyword)</li>
  <li>Manually browse</li>
  <li>Target -> Site map -> Filter -> Show only in-scope items</li>
  <li>Target -> Site map -> manually select host to spider, right click and Spider Selected items</li>
</ul>


<a href="https://www.google.com"><h2>Google (dork)</h2></a>
<ul>
  <li>inurl: example.com (removing every new host using -already_known_host)</li>
  <li>Trademark: "© 2015 - 2018 Company Name Inc." depending what format is used (look for it in main domain footer)</li>
</ul>

<a href="https://crt.sh/"><h2>crt.sh</h2></a>
<ul>
  <li>Insert domain.com and check for SLL certificate to get others domains and subdomains covered by the same certificate</li>
</ul>

<a href="https://censys.io/"><h2>censys.io</h2></a>
<ul>
  <li>Insert domain.com and check for SLL certificate to get others domains and subdomains covered by the same certificate</li>
</ul>

<a href="https://censys.io/"><h2>crunchbase.com</h2></a>
<ul>
  <li>Can find information, related companies, new acquisition and a lot of other stuff about a company and its domain(s)</li>
</ul>


<h2>Others</h2>
<ul>
  <li>https://www.robtex.com/</li>
  <li>https://www.virustotal.com/#/domain/domain.com</li>
</ul>


<a href="https://youtu.be/Qw1nNPiH_Go?t=1h9m26s"><h2>Search all js for hidden path and urls with BurpSuite</h2></a>
<ul>
  <li>Right click on target site/</li>
  <li>Engagement tools -> Find scripts -> Search</li>
  <li>Once found -> Export script (eg. for use in some JS parser)</li>
</ul>


<a href="https://github.com/nahamsec/JSParser"><h2>JSParser</h2></a>
<pre>python handler.py</pre>
<pre>Then visit http://localhost:8008</pre>


<a href="https://github.com/GerbenJavado/LinkFinder"><h2>LinkFinder</h2></a>
<pre>Sounds interesting. Have to test it yet</pre>

<h1>After subdomain enumeration</h1>

<a href="https://github.com/FortyNorthSecurity/EyeWitness"><h2>EyeWitness</h2></a>
<pre>./EyeWitness.py --timeout 31 --prepend-https -f domain_domain_list.txt</pre>


<a href="https://web.archive.org/"><h2>Archive.org/web</h2></a>
<pre>If i found a 401/403, basic auth or some is locked down</pre>


<a href="https://github.com/tomnomnom/waybackurls"><h2>waybackurls</h2></a>
<pre>cat domains.txt | waybackurls > urls</pre>
Get all links from archive.org using a domains list


<h1>Subdomain takeover & Cloud misconfiguration</h1>


<a href="https://github.com/Ice3man543/SubOver"><h2>SubOver</h2></a>
<pre>SubOver -l /root/Documents/company_subdomain_list.txt -https -v</pre>


<a href="https://github.com/EdOverflow/can-i-take-over-xyz"><h2>Can i take over xyz</h2></a>
An interesting source to understand IF and HOW is possible a subdomain takeover


<a href="https://github.com/sa7mon/S3Scanner"><h2>Scan for open S3 buckets and dump</h2></a>

<h1>Content discovery</h1>

<a href="https://github.com/OJ/gobuster"><h2>Gobuster (again)</h2></a>
<pre>gobuster -u domain.com -fw -v -w list.txt -o domain_report_gobuster.txt</pre>
An interestin list is <a href="https://github.com/danielmiessler/RobotsDisallowed">RobotsDisallowed</a><br>
An useful list to add while bruteforcing for subdirectory maybe <a href="https://github.com/jhaddix/SecLists/blob/master/Discovery/Web-Content/Common-DB-Backups.txt">this DB backup filename</a>

<a href="https://github.com/maK-/parameth"><h2>Discover unknown parameters in script with parameth</h2></a>
<pre>Will test soon.</pre>


<a href="https://github.com/PortSwigger/backslash-powered-scanner"><h2>Backslash Powered Scanning (Vulnerability scanner)</h2></a>
<pre>Too early to say something</pre>


<h1>Open redirect</h1>

<h2>Some tricks</h2>
<ul>
  <li>Typical parameters to look at:
    <ul>
      <li>redirect_to=</li>
      <li>domain_name=</li>
      <li>checkout_url=</li>
      <li>r=<li>u=</li>
      <li>returnTo=</li>
      <li>return=</li>
      <li>go=</li>
      <li>redirect=</li>
      <li>url=</li>
    </ul>
  </li>
  <li><a href="https://zseano.com/tutorials/1.html">Common pages are: </a>login, register, logout, change site language, links in emails. </li>
</ul>


<h2><a href="https://zseano.com/tutorials/1.html">Methods for bypassing filters</a></h2>
<ul><li>java%0d%0ascript%0d%0a:alert(0)<br>
(crlf injection to bypass javascript: being blacklisted)</li>
<li>//google.com<br>
(incase http:// is blacklisted)</li>
<li>https:google.com<br>
(browsers accept this, good if // is blacklisted!)</li>
<li>//google%E3%80%82com<br>
(%E3%80%82 is 。 encoded. A HUGE thanks to filedescriptor for showing me that)</li>
<li>\/\/google.com/<br>
(useful for bypassing // http:// blacklists. Browsers see \/\/ as //)</li>
<li>/\/google.com/<br>
(same as above)</li>
<li>//google%00.com<br>
(null byte to bypasses blacklist filter. can be used anywhere)</li>
<li>http://www.theirsite.com@yoursite.com/<br>
(oldie, but browsers will redirect to anything after @)</li>
<li>http://www.yoursite.com/http://www.theirsite.com/<br>
(if @ is blacklisted and they check if their domain is in the param, make a folder as their domain :D)</li>
<li>";alert(0);//<br>
(example from above. if the url is echo'd in a variable and we want to get xss in script tag)</li>
</ul>


 
<h1>HTTP Parameter pollution</h1>

<h2>Some tricks</h2>
<ul>
  <li>Add new parameter with the same name (e.g. ?par1=123&par2=456&par1=789)</li>
  <li>Replace ampersand character "&" with "%26"</li>
  <li>Change parameter position</li>
  <li>Try to change typical or intelligible parameters names (edit, view, delete)</li>
  <li>Change HTTP method (POST if GET and viceversa)</li>
 </ul>


<a href="https://www.owasp.org/index.php/Testing_for_HTTP_Parameter_pollution_(OTG-INPVAL-004)#Expected_Behavior_by_Application_Server"><h2>Expected Behavior by Application Server</h2></a>
Given the URL and querystring: http://example.com/?color=red&color=blue
<table>

<tbody><tr>
<th> Web Application Server Backend </th>
<th> Parsing Result </th>
<th> Example
</th></tr>
<tr>
<td> ASP.NET / IIS </td>
<td> All occurrences concatenated with a comma </td>
<td> color=red,blue
</td></tr>
<tr>
<td> ASP / IIS </td>
<td> All occurrences concatenated with a comma</td>
<td> color=red,blue
</td></tr>
<tr>
<td> PHP / Apache </td>
<td> Last occurrence only </td>
<td> color=blue
</td></tr>
<tr>
<td> PHP / Zeus </td>
<td> Last occurrence only </td>
<td> color=blue
</td></tr>
<tr>
<td> JSP, Servlet / Apache Tomcat </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> JSP, Servlet / Oracle Application Server 10g </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> JSP, Servlet / Jetty </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> IBM Lotus Domino </td>
<td> Last occurrence only </td>
<td> color=blue
</td></tr>
<tr>
<td> IBM HTTP Server </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> mod_perl, libapreq2 / Apache </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> Perl CGI / Apache </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> mod_wsgi (Python) / Apache </td>
<td> First occurrence only </td>
<td> color=red
</td></tr>
<tr>
<td> Python / Zope </td>
<td> All occurrences in List data type </td>
<td> color=['red','blue']
</td></tr></tbody></table>


<h2>References</h2>
<ul>
  <li><a href="https://www.owasp.org/index.php/Testing_for_HTTP_Parameter_pollution_(OTG-INPVAL-004)#Server-side_HPP">Server side HPP manual testing workflow</a></li>
  <li><a href="https://www.owasp.org/index.php/Testing_for_HTTP_Parameter_pollution_(OTG-INPVAL-004)#Client-side_HPP">Client side HPP manual testing workflow</a></li>
 </ul>


<h1>CSRF</h1>


<h2>Some tricks</h2>
<ul>
  <li>If a site is sending CSRF token with POST request, try changing its value or removing it to ensure the server is validating its existence.</li>
 </ul>


<h1>SSRF</h1>


<h2>Some tricks</h2>
<ul>
  <li><a href="https://gist.github.com/jhaddix/78cece26c91c6263653f31ba453e273b">Cloud Metadata Dictionary useful for SSRF Testing</a></li>
 </ul>


<h1>File Upload</h1>


<h2>Some tricks</h2>
<ul>
  <li>Rename file extension. Eg. file.png -> file.png.php, file.php -> file.php.png</li>
  <li>Rename file extension changing case. Eg. file.png -> file.png.PHP, file.php -> file.PhP.png</li>
  <li>Change extension position. Eg. file.png.php -> file_png.php</li>   
  <li>Use unusual file extension like pht (can execute php in html)</li> 
  <li>Insert a Null Byte in file name: shell.php<b>%00</b>1.jpg or shell.php\x00.jpg</li>
  <li>Insert a payload in Exif Headers</li> 
  <li>Upload a huge file so to get a DOS on server</li> 
  <li>If filename is not changed before being inserted in DB, maybe possible an Sql Injection</li> 
 </ul>

<h2>Some tricks</h2>
<ul>
  <li><a href="https://hackerone.com/reports/357858">Upload php as image</a></li>
 </ul>


<h1>XSS</h1>


<h2>[BLIND XSS] Some tricks</h2>
<ul>
  <li><a href="https://medium.com/bugbountywriteup/blind-xss-for-beginners-c88e48083071">Try blind XSS injection into User-Agent</a> or Referrer/Origin Headers. <a href="https://addons.mozilla.org/en-US/firefox/addon/user-agent-switcher-revived/?src=search">Firefox User Agent Switcher</a> extension can be useful to change UA on fly</li>
 </ul>


<a href="https://github.com/s0md3v/XSStrike"><h2>XSStrike</h2></a>
<pre>python3 xsstrike</pre>


<a href="https://github.com/faizann24/XssPy"><h2>XssPy</h2></a>
<pre>python XssPy.py -d website.com -v -e</pre>

<h2>Tutorials and resources</h2>
<ul>
  <li><a href="https://forum.bugcrowd.com/t/tutorial-injectx-to-find-xss/790">Tutorial: InjectX to Find XSS</a></li>
</ul>


<h1>Information disclosure</h1>


<h2>Php Information disclosure</h2>
<ul>
  <li><a href="https://blog.it-securityguard.com/bugbounty-yahoo-phpinfo-php-disclosure-2/">Scan a CIDR for phpinfo() to get php information disclosure</a>.<br>This script can scan huge amount of IPs for phpinfo.php file.<pre>#!/bin/bash
for ipa in 98.13{6..9}.{0..255}.{0..255}; do
wget -t 1 -T 5 http://${ipa}/phpinfo.php; done &</pre></li>
 </ul>


<a href="https://github.com/s0md3v/XSStrike"><h2>XSStrike</h2></a>
<pre>python3 xsstrike</pre>


<a href="https://github.com/faizann24/XssPy"><h2>XssPy</h2></a>
<pre>python XssPy.py -d website.com -v -e</pre>

<h2>Tutorials and resources</h2>
<ul>
  <li><a href="https://forum.bugcrowd.com/t/tutorial-injectx-to-find-xss/790">Tutorial: InjectX to Find XSS</a></li>
</ul>


<h1>Application logic</h1>


<h2>Ways data are transmitted via client</h2>
<ul>
  <li>Hidden form field</li>
<li>HTTP Cookies</li>
<li>URL Parameters (?name=value)</li>
<li>Referer header</li>
<li>Opaque data (encrypted or obfuscated data in hidden form field, in cookie etc)</li>
<li>ViewState in ASP.NET (if not protected with MAC protection)</li>
 </ul>
 Also take a look to fields length limit in form fields (can be changed?), script-based validation (eg javascript: can be overwritten or deleted?), disabled elements (are they processed by server?)
