# WebApp-Sec-Resources
I needed a place to collect all tools, resources, tutorial about web application security and testing. This is my way.



<h1>Subdomain enumeration</h1>

<a href="https://github.com/aboul3la/Sublist3r"><h2>Sublist3r</h2></a>
<pre>python sublist3r.py -d domain.com -o domain_report_sublist3r.txt</li></pre>


<a href="https://github.com/OJ/gobuster"><h2>Gobuster</h2></a>
<pre>gobuster -u domain.com -fw -m dns -v -w list.txt -o domain_report_gobuster.txt</pre>
