# onMouseMove-HtmlFile-PoC
PoC for onMouseMove HTML file used in the Russian APT Group campaign targeting Ukraine

The HTML File is included as an attachment in the phishing email, when the victim opens the html file and moves the mouse, this triggers the event handler attribute "onmousemove" which runs the Javascript, which further decodes the base64 encoded blob present in the HTML Body. The base64 decoded blob consisting of further javascript routine which checks the Operating System and if this OS check is satisfied it drops the next stage i.e the ZIP archive decoded from another base64 encoded blob. In the PoC, the ZIP archive has a text file :) but in the ITW campaign it had a malicious Windows Shortcut File (.LNK) inside thr archive which remotely executed a HTA file via mshta.exe.

A Classic Anti-Sandbox Technique =)

*Note:* I've removed the usage of document.onmousemove event handler used in the ITW sample, as it was not necesary, adding the viewport height (100vh) covers the complete browser window.

Ref. https://blog.strikeready.com/blog/armageddon-is-more-than-a-grammy-nominated-album/
