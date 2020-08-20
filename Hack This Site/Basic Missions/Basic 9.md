# Basic 9

**skill:** Server Side Includes (SSI); see Basic 8

SSI is the language that servers use to execute actions before the user sees the page. In order to signify that an HTML file uses SSI, the file should have extensions of `.shtm`, `.stm`, or `.shtml`. The syntax for an SSI command is 
`<!--#directive paramter=value parameter=value-->`

For example, the command
`<!--#exec cmd="ls ../"-->`
lists the files of the parent directory.

The site takes in raw input from the user without cleaning special characters like '<' and '!' so it will execute any SSI commands it receives.

Sources:

  [Wikipedia entry](https://en.wikipedia.org/wiki/Server_Side_Includes)

  [OWASP SSI Injection](https://owasp.org/www-community/attacks/Server-Side_Includes_(SSI)_Injection)

---

The prompt reveals that "there is a way to get the obscured level 9 password" from the previous level, but it's located in /basic/9 instead of /basic/8. Go back to the previous level and navigate to the /basic/9 directory with the command 
`<!--#exec cmd="ls../../9"-->`
to see the list of files in that directory. The file named p91e283zc3.php seems to contain the password.

Navigate to the page by appending '/p91e283zc3.php' to the URL (make sure to change it from /basic/8 to /basic/9) to get the password: 2dc46faf
