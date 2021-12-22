# PasswordCrackingMethodology
My Password Cracking Methodology

Dictionaries:

hashkiller: https://hashkiller.io/download

crackstation: https://crackstation.net/crackstation-wordlist-password-cracking-dictionary.htm

real-passwords: https://github.com/berzerk0/Probable-Wordlists/tree/master/Real-Passwords

Password aggregation from FlameOfIgnis: https://github.com/FlameOfIgnis/Pwdb-Public/tree/master/wordlists


The rest of the custom wordlists are sourced from: https://hashes.org/leaks.php (I take wordlists and combine and de-dupe them based on the clear text from cracked leaks)

Rules: 

OneRuleToRuleThemAll: https://github.com/NotSoSecure/password_cracking_rules

H0bRules: https://github.com/praetorian-code/Hob0Rules

Masks:

List of masks from a ton of cracked passwords: https://github.com/golem445/Corporate_Masks


First passthrough:

Create a wordlist of SeasonYEAR in format Season?d?d?d?d.

Run that wordlist with hashcat and then with rules.

Rules are in this order for the first pass:

OneRule

H0b Rules

Dive


Rockyou.txt

Rockyou.txt with rules


Then hashkiller.

Then hashkiller with rules.


Then linkedin.txt (linkedin data breach)

Then linkedin.txt with rules.


Then haveibeenpwned.

Then haveibeenpwned with rules.


Then crackstation.

Then crackstation with rules.


Then Top2Billion.txt

Then Top2Billion with rules.


Add masks to your dictionary attacks: 

https://hashcat.net/wiki/doku.php?id=hybrid_atttack_with_rules
https://hashcat.net/wiki/doku.php?id=hybrid_attack

hashcat -m WHATEVER -a 6 dict.txt ?a?a?a?a (Modify your character set accordingly)


When time permits, an incrementing brute force: hashcat -m WHATEVER hashes.txt -a 3 ?a?a?a?a?a?a?a?a --increment

At that point I then start re-running from the top with additional rules in this order:

best64 + OneRule

best64 + H0bRules

best64 + dive

Then start switching rule order and adding in toggles and leetspeak.

Purple rain: https://www.netmux.com/blog/purple-rain-attack

I like running Purple Rain with hashkiller-dict.txt
