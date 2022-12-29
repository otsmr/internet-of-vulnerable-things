# Internet of Vulnerable Things

The results of my small [term paper](Internet_of_Vulnerable_Things.pdf) on the topic of the *Internet of Vulnerable Things*.

**Abstract**

This paper provides a practical demonstration of how insecure the Internet of Things is by hacking a typical
IoT device. Several vulnerabilities were identified in the TP-Link TL-WR902AC, including one that
allows an authenticated attacker to launch a root shell in all current TP-Link routers, bringing them under
the full control of the attacker. How the vulnerability was discovered and how it can be exploited is part of
this paper. As a result of these findings and other examples, we conclude that due to the strong growth of
the Internet of Things, the risk of hacked IoT devices will continue to increase if there is no stronger legal
regulation.


## Disclosure timeline

I reported the found remote code execution via flashing malicious firmware to the manufacturer here is the timeline of the reporting.

> An issue in the firmware update process of TP-Link TL-WR902AC V3 0.9.1 and earlier allows authenticated attackers to execute arbitrary code or cause a Denial of Service (DoS) via uploading a crafted firmware update.

The exploit can be found in `/exploits/malicious-firmware-update.py` together with the reported description.

- `November` - I have started my term paper and found the security vulnerability in this process.
- `Nov 23, 2022` - Vulnerability reported to BSI via [online form](https://www.bsi.bund.de/DE/IT-Sicherheitsvorfall/IT-Schwachstellen/Online_Meldung_Schwachstellen/schwachstellenmeldung_node.html). I decided to do this, because TP-Link has not fixed reported vulnerabilities in [the past](https://pwn2learn.dusuel.fr/blog/unauthenticated-root-shell-on-tp-link-tl-wr902ac-router/).
- `Dec 01, 2022` - The BSI wanted more info from me, which is why the vulnerability was first reported to the manufacturer at this point. (I initially thought it would be enough to simply report that the firmware is not signed and that you can easily manipulate it.)
- `Dec 05, 2022` - TP Link requests an English version on which I have additionally added an exploit script.


- `Dec 26, 2022` - I asked the BSI what the current status is and got the following information one day later:
    - `Dec 23, 2022` - The BSI has asked TP-Link what the current status is. They replied that they had not yet been able to verify the vulnerability and that a final response from the company is expected in early January. Since I wanted a CVE I was advised that I could report it myself. Which is why I found out that this vulnerability was already published a few days ago:
    - `Dec 20, 2022` - [Several CVEs](https://www.opencve.io/cve?vendor=tp-link&cvss=&search=firmware+update) have shown up where the same security vulnerability was found, just on different models.

- `Dec 29, 2022` - Since the vulnerability is already public knowledge, I am publishing my research as well.

