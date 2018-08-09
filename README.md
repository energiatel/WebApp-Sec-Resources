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

<a href="https://github.com/haccer/subjack"><h2>subjack</h2></a>
<pre>./subjack -w subdomains.txt -o subjack_results.txt -ssl -a -v</pre>


<a href="https://github.com/EdOverflow/can-i-take-over-xyz"><h2>Can i take over xyz</h2></a>
An interesting source to understand IF and HOW is possible a subdomain takeover


<a href="https://github.com/sa7mon/S3Scanner"><h2>Scan for open S3 buckets and dump</h2></a>

<h2>Google dork</h2>
<ul>
  <li>intext:"There isn't a Github Pages site here" and intitle:"Site not found · GitHub Pages"</li>
</ul>

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

<h2>Lists</h2>
<ul>
  <li>https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Open%20redirect</li>
</ul>

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

<h2>Some resources and tutorial</h2>

<ul>
  <li><a href="https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Open%20redirect">By swisskyrepo</a></li>  
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

<h2><a href="https://forum.bugcrowd.com/t/how-do-you-approach-a-target/293/3">Test on parameters: what happens if...</a></h2>
<ul>
  <li>you put in a minus number?</li>
  <li>you increment or decrement the number?</li>
  <li>you put in a really large number?</li>
  <li>you put in a string or symbol characters?</li>
  <li>you try traverse a directory with …/</li>
  <li>you put in XSS vectors?</li>
  <li>you put in SQLI vectors?</li>
  <li>you put in non-ascii characters?</li>
  <li>you mess with the variable type such as casting a string to an array</li>
  <li>you use null characters or no value</li>
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



<h2>Ways data are transmitted via client</h2>
<ul>
  <li>Hidden form field</li>
<li>HTTP Cookies</li>
<li>URL Parameters (?name=value)</li>
<li>Referer header</li>
<li>Opaque data (encrypted or obfuscated data in hidden form field, in cookie etc)</li>
<li>ViewState in ASP.NET (if not protected with MAC protection)</li>
 </ul>
 
<h2>Authentication</h2>

<h3>Bad password</h3>
<ul>
  <li>Too short or blank</li>
  <li>Common dictionary words or names</li>
  <li>Same as username </li>
  <li>Set to default value</li>
</ul>

<h3>Brute forcible login</h3>
<ul>
  <li>No limits un login attempts </li>
  <li>Common dictionary words or names</li>
  <li>Stored in clear text (no need to use any encryption to bruteforce)</li>
  <li>Login attempts number only on client side (eh cookie such as failedLogin = 1)</li>
  <li>Login attempts number held in current session (so only have to obtain fresh session eg deleting session cookie)</li>
  <li>Account locked after a certain number of login attempts but application still confirm if password is correct. In this case maybe account is unlocked after certain delay automatically</li>
</ul>

<h3>Verbose failed login message</h3>
<ul>
  <li>Application response whether the reason for failure was unrecognised username or wrong password (so can iterate with common username list to guess a valid one. After can do the same for password)</li>
  <li>Username disclosure in registration form (to prevent duplicates) or password change form or forgotten password function</li>
  <li>Predictable username (username is email address, email name or automatically generated as user123 user124 user125)</li>
  <li>Subtle failed login response when wrong or valid username is provided. Response may appears the same but cookie, http response or html code can contains differences</li>
  <li>Time attacks: different response time for wrong and valid username. Try it with a common username list and if possible with at least one valid username</li>
</ul>


<h3>Password change function</h3>
<ul>
  <li>Sometimes this function is accessible without authentication</li>
  <li>Allow unrestricted (eg no rate limits) guesses of existing password</li>
  <li>Verbose message for username validity</li>
  <li>New password and confirm password fields may change their value if existing password is valid or if current and new password are identical</li>
  <li>If this function is accessible only for authenticaticated users, maybe it hide somewhere  (hidden form field, cookie, other) the username whom which password is going to be changed. Try to override this hidden username </li>
</ul>


<h3>Forgotten password function</h3>
<ul>
  <li>Easy guessable challenge (public information as mother's name, birthday)</li>
  <li>Bruteforcible response to challenge</li>
  <li>Password recover hint equal to password</li>
  <li>User dropped in authenticated session after successfull completion of a challenge</li>
  <li>Recovery URL sent to an address which is specified and not to registered email address</li>
  <li>Recovery URL or user email visible in hidden fields or in cookie</li>
  <li>Password reset after successfull completion of challenge</li>
</ul>


<h3>Remember me function</h3>
<ul>
  <li>Only username is stored in cookie which is used to allow user access</li>
  <li>Only user ID or another identifier is stored on cookie which is used to allow user access</li>on logged in computer</li>
</ul>


<h3>User impersonate function </h3>
<ul>
  <li>No access control so anyone who knows this function URL can use it</li>
  <li>User controllable data may determine which user is impersonated</li>
  <li>If administrators accounts may be impersonated, attacker can gain full control of the application</li>
  <li>A default password is used to impersonate any user on login function </li>
</ul>


<h3>Incomplete validation of credentials</h3>
<ul>
  <li>Only firsts password n character are validated</li>
  <li>Case insensitive check of password</li>
  <li>Unusual characters stripped before checking password</li>
</ul>


<h3>Non unique username</h3>
<ul>
  <li>May append that two users can register with same password</li>
  <li>Unpredictable conseguences on users login</li>
</ul>


<h3>Predictable username</h3>
<ul>
  <li>Usernames can be nonintrusively discovered</li>
</ul>


<h3>Predictable initial password </h3>
<ul>
  <li>Default password for any new account </li>
  <li>The means of generating passwords can be replicated by an attacker</li>
</ul>


<h3>Insecure distribution of credentials</h3>
<ul>
  <li>Insecure distribution of credentials</li>
  <li>Majority of users will not modify initial credentials</li>
  <li>Activation token can be guessed</li>
  <li>Username and password sent together</li>
</ul>

<h2>Implementation flaws in authentication </h2>

<h3>Fail-open logic mechanism</h3>
<ul>
  <li>If username or password are empty, the application throws an exception and login succeed</li>
</ul>

<h3>Multistage login mechanism</h3>
<ul>
  <li>Application may assume that user who access to stage two have cleared stage one</li>
  <li>Application may trust data on stage two because this was validated on stage one</li>
  <li>Application assume that the same user identity is used in every stage</li>
</ul>

<h3>Insecure storage of credentials</h3>
<ul>
  <li>Passwords stored in clear text</li>
  <li>Passwords encrypted in standard algorithm</li>
</ul>

<h1>Attacking session management</h1>




<h2>Token generation</h2>
<ul>
  <li>Meaningful tokens</li>
  <li>Can be decrypted and its structure disclosed</li>
  <li>May be not all components in decrypted token are validated server side. So fuzzing become faster</li>
 </ul>

<h2>Predictable tokens</h2>
<ul>
  <li>With a small sample of tokens it's possible to guess all session tokens</li>
  <li>Concealed sequences: try to discover mean of generating </li>
  <li>Time dependency: eg token contain ID and timestamp. With this predictable pattern it's easy to brute force and gain a valid session token</li>
  <li>Weak random number generation: random generation may be deterministic, eg generated based on user's ip (php 5.3.2 with phpwn tool)</li>
  <li>Burp can test quality of randomness with a sample of session tokens and sequencer</li>
 </ul>

<h2>Encrypted tokens</h2>
<ul>
  <li>ECB Ciphers</li>
  <li>CBC Ciphers (flip bit with burp intruder)</li>
 </ul>

<h2>Liberal cookie scope</h2>
<ul>
  <li>Cookie domain restrictions</li>
  <li>Cookie path restrictions</li>
 </ul>


<h1>Attacking Access controls</h1>


<h3>Common vulnerabilities</h3>
<ul>
  <li>Vertical access control: from user to admin</li>
  <li>Horizontal access control: from user to user</li>
  <li>Context--dependent access control: user should access only what it permitted to</li>
 </ul>

<h3>Completely unprotected functionality</h3>
<ul>
  <li>Anyone who knows admin URL can access it with full use of administrative functions</li>
  <li>Links to administrative functions may be hide in javascript or in hidden fields or in comments</li>
  <li>Administrative methods can be reached directly through API or javascript </li>
 </ul>

<h3>Identifier-based functions</h3>
<ul>
  <li>User who knows resources URL can access it even if not logged or if resources is owned by another user</li>
 </ul>

<h3>Multistage functions</h3>
<ul>
  <li>Application assumes that earlier stage has been completed when accessing to later stage</li>
 </ul>

<h3>Static files</h3>
<ul>
  <li>Can be accessed directly</li>
 </ul>

<h3>Platforms misconfiguration</h3>
<ul>
  <li>A function may be made to work with POST but still works with GET</li>
  <li>Application handle request that use unrecognized HTTP methods by passing to GET</li>
 </ul>

<h2>Insecure access control methods</h2>

<h3>Parameters based access control</h3>
<ul>
  <li>User role is determined via client transmitted parameters (hidden forms fields, cookie, query string parameters</li>
 </ul>

<h3>Referer based access control</h3>
<ul>
  <li>Application check referer to allow administrative functions use. If they comes from administration page they're allowed </li>
 </ul>

<h3>Location based access control </h3>
<ul>
  <li>Can be circumvented using proxy, VPN, client side manipulation of geolocation mechanism</li>
 </ul>
