# WebApp-Sec-Resources
I needed a place to collect all tools, resources, tutorial about web application security and testing. This is my way.



<h1>Subdomain enumeration</h1>

<h2>Lists</h2>
<ul>
  <li>https://github.com/jhaddix/SecLists/tree/master/Discovery/DNS</li>
  <li>https://github.com/caffix/amass/tree/master/wordlists</li>
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
<pre>Not tested yet</pre>


<a href="https://github.com/caffix/amass</h2></a>
<pre>amass -d upwork.com</pre>
         Lists can be found <a href="https://github.com/caffix/amass/tree/master/wordlists">here </a>


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

<a href="https://github.com/caffix/amass"><h2>Amass</h2></a>
<pre>amass -d upwork.com</pre>


<h2>Others</h2>
<ul>
  <li>https://www.robtex.com/</li>
  <li>https://www.virustotal.com/#/domain/domain.com</li>
</ul>



<h1>After subdomain enumeration</h1>

<a href="https://github.com/FortyNorthSecurity/EyeWitness"><h2>EyeWitness</h2></a>
<pre>./EyeWitness.py --timeout 31 --prepend-https -f domain_domain_list.txt</li></pre>

<h1>Subdomain takeover</h1>


<a href="https://github.com/Ice3man543/SubOver"><h2>SubOver</h2></a>
<pre>SubOver -l /root/Documents/company_subdomain_list.txt -https -v</pre>


<a href="https://github.com/EdOverflow/can-i-take-over-xyz"><h2>Can i take over xyz</h2></a>
An interesting source to understand IF and HOW is possible a subdomain takeover



