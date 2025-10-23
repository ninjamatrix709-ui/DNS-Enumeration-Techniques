🧠 Lab Summary — DNS Enumeration Techniques
🎯 Objective

Use DNS enumeration tools to gather detailed information about a target domain, identify subdomains, and understand how attackers perform DNS reconnaissance.

⚙️ Step-by-Step Overview

Setup

Run the lab on Kali Linux with tools like dnsenum and dig.

Enumerate DNS Records

Run:

dnsenum example.com


Collect DNS records: A, MX, NS, and their corresponding IPs.

Attempt Zone Transfer

Try a DNS zone transfer (AXFR) using dig:

dig axfr example.com @[nameserver_IP]


Observe if zone transfer is allowed or denied (usually fails due to security restrictions).

Reverse DNS Lookup

Discover hostnames from IPs:

dig -x [Target_IP]


Identify if any hostnames reveal internal or sensitive infrastructure.

Brute-Force Subdomain Discovery

Use enumeration mode to discover hidden subdomains:

dnsenum --enum example.com


Save Results

Store enumeration output:

dnsenum example.com > dns_results.txt
cat dns_results.txt


Analyze Findings

Identify potential targets such as:

Web servers: ftp.cisco.com, apps.cisco.com

Mail servers: aer-mx, rcdn-mx

Review DNS servers for misconfigurations or leaked version info.

Reflection

Understand how DNS enumeration helps attackers map networks.

Discuss securing DNS servers (restrict AXFR, hide version info, monitor DNS queries).

Cleanup

Shut down the Kali VM after saving your results.

🧩 Key Takeaways

Learn how DNS reveals valuable intelligence about network infrastructure.

Use tools like dnsenum and dig for ethical reconnaissance.

Recognize how to harden DNS against information leakage and zone transfer abuse.
