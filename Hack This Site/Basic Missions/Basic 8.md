# Basic 8

**skill:** Server Side Includes (SSI)

SSI is the language that servers use to execute actions before the user sees the page. In order to signify that an HTML file uses SSI, the file should have extensions of `.shtm`, `.stm`, or `.shtml`. The syntax for an SSI command is 
`<!--#directive paramter=value parameter=value-->`

For example, the command:
`<!--#exec cmd="ls .."-->`
lists the files of the parent directory.

The site takes in raw input from the user without cleaning special characters like '<' and '!' so it will execute any SSI commands it receives.

Sources:

  [Wikipedia entry](https://en.wikipedia.org/wiki/Server_Side_Includes)

  [OWASP SSI Injection](https://owasp.org/www-community/attacks/Server-Side_Includes_(SSI)_Injection)

---

You can use an SSI Injection to find the password. The prompt reveals that the password is kept in /var/www/hackthissite.org/html/missions/basic/8/. Looking at the URL, you can see that is also the name of your current directory. Testing out a sample entry for the name, we see that we are in the /tmp directory, so we want the files in the parent directory (/basic/8). 

In the box to enter your name, enter:
`<!--#exec cmd="ls ../"-->`
to list all the files in the parent directory. The file au12ha39vc.php looks like it could be the password file.

Navigating to that page by adding /au12ha39vc.php to the end of the URL in the /basic/8 directory, we find the password: 927cdeea
