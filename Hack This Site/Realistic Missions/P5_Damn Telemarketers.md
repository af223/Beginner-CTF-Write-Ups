# Damn Telemarketers (incomplete)

**goal:**
 - get password to the site
 
 **prompt hints:**
  - 'everything they used was 10 years out of date'
  - 'message digest'
  - hash value

**skill:** cryptography

---

Looking around the site under the News tab, we see a hint: "Google was grabbing links it shouldn't be so I have taken extra precautions." This indicates a robots.txt file. Going to the page (hackthissite.org.missions/realistic/5/robots.txt), you'll see two directories that robots aren't allowed to look in: `/lib` and `/secret`.

The `/secret` directory contains two files: `admin.php` and `admin.bak.php`. 'admin.php' shows Invalied Password when you click on it, but 'admin.bak.php' displays the message 

`error matching hash aaea7dbeea8aa9155a3c0a716ae3969a`

Going to the `/lib` directory, there's a file called 'hash'. It's a 32-bit ELF file which presumably performs the hashing. 
The 'message digest' and '10 years out of date' hint from the prompt implies the use of either MD4 or MD5 as the hash.

I have yet to find the password that hashes to 'aaea7dbeea8aa9155a3c0a716ae3969a' so I'll get back to this once I figure out a way.
