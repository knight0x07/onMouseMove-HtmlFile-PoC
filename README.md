# onMouseMove-HtmlFile-PoC
PoC for onMouseMove HTML file used in the Russian APT Group campaign targeting Ukraine

The HTML File is included as an attachment in the phishing email, when the victim opens the html file and moves the mouse, this triggers the event handler attribute "onmousemove" which runs the Javascript, which further decodes the base64 encoded blob present in the HTML Body. The base64 decoded blob is executed which further checks the Operating System and if the check is satisfied it downloads the next stage i.e the ZIP File from another base64 encoded blob. In the PoC, the ZIP file has a text file :) but in the ITW campaign it had a malicious Windows Shortcut File (.LNK) which remotely executed a HTA file via mshta.exe.

Note: I've removed the usage of document.onmousemove event handler as it was not necesary, added the viewport height (100vh) which covers the complete browser window.

Ref. https://blog.strikeready.com/blog/armageddon-is-more-than-a-grammy-nominated-album/
