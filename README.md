# Installed Certificates Checker
## Summary
The excellent sigcheck Windows Sysinternals tool can identify currently installed certificates and more specifically, any that are not rooted by a certificate on the trusted Microsoft root certificate list.

This is useful when hunting for [Superfish](https://en.wikipedia.org/wiki/Superfish) like certificates that could be used to intercept encrypted communication.  

Combining the output of the sigcheck tool with a git repo can provide a history of changes and allows reuse of git tools to easily compare the diffs.

## Guide
1.  Create a git repo (or clone this one)
2.  Download Sigcheck (Windows Sysinternals Tool) from https://technet.microsoft.com/en-us/sysinternals/bb897441.aspx
3.  Unzip Sigcheck tool into the git repo
4.  Open command prompt where sigcheck is located
5.  Execute the following command: sigcheck -q -tv -c > mycerts.csv
6.  Examine mycerts.csv (ideally the first line will be column headers and the next line will say: No certificates found.)
6.  Commit mycerts.csv to the git repo
7.  Compare diffs using a git tool like https://desktop.github.com/
