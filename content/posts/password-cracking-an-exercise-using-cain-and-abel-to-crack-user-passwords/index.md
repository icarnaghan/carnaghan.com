---
author: "icarnaghan"
title: "Password Cracking - An Exercise Using Cain and Abel to Crack User Passwords"
date: 2011-02-25
categories: 
  - "cybersecurity"
tags: 
  - "csec-610"
---

The objective of this exercise was to use the various password cracking tools available in the Cain and Abel software application and to determine the efficiency and effectiveness of each technique.  The following user accounts were created for testing purposes.  The first user account had a relatively easy to break password and the two that followed had slightly more complex password structures.

**Username           Password            Character set** ictest1                   testing                  Lowercase letters ictest2                   break1ng             Lowercase letters and numbers ictest3                   Bre@k1ng           Lowercase letters, uppercase letters, numbers and symbols

None of the above passwords created were overly complex for the purpose of testing the capabilities of the Cain and Abel software.  The results of the lab follow along with addressing the following questions:

1. Explain the two different types of attacks that can be performed in Cain and Abel to crack user account passwords. Which do you think is the most effective and why?
2. Compare and contrast the results from the two methods used to crack the accounts. What conclusions can you make after using these two methods?
3. Research another algorithm used to store passwords that was not discussed here. (Include references in APA format.)
4. Research another password recovery software program and provide a thorough discussion of it.  Compare and contrast it to Cain and Abel. (Include references in APA format.)
5. Anti-virus software detects Cain and Able as malware. Do you feel that Cain and Able is malware? Why or why not?

## Types of Attacks using Cain and Abel

Two different types of attacks were used in this lab in attempts to break three different Windows usernames, each with a password slightly different in level of sophistication.  These types of attacks are known as brute-force and dictionary attacks.

Yan (Yan, J, Blackwell, A., Anderson r. & Grant, A., 2004) describes a brute-force attack as method of using all possible combinations of keys when trying to discover a password.  Cain and Abel provides the ability to use predefined character sets and define the minimum and maximum password length.  The character sets can include a mixture of lowercase letters, uppercase letters, numbers and special symbols.  The more complex the character set, the longer it will take the software to run the different combinations during an attack.

Dictionary attacks are more refined than brute-force where they don’t simply try all combinations but focus on a list of most likely used words.  Pinkas (Pinkas, B. & Sander, T., 2002) reminds us that most users choose passwords that come from a small domain, or list of common words and phrases.  This in effect enables “adversaries to attempt to login to accounts by trying all possible passwords, until they find the correct one.”  These forms of attack require access to large compilations of commonly used words usually in the form of a text document.  For the lab, we used the default supplied text file wordlist.txt, which was just over three megabytes in size.  Files of this nature in real attacks can be upwards of seventy gigabytes in size.  Dictionary attacks are potentially more efficient than brute-force methods because they are not blindly attempting all combinations of letters, numbers and symbols, as they are relying on higher probabilities choosing commonly used words and phrases.

## Contrasting the Lab Results

During the lab exercise both brute-force and dictionary attacks were used in attempts to crack the passwords of the three test accounts.  The results of these attempts follow:

**User 1: ictest1 / testing**

A brute-force attack was attempted on ictest1.  The settings used for this attack included the default lowercase letter character set and a maximum number of password letters set to seven.  The brute-force attack succeeded in recovering the password ‘testing’ in just over four minutes.  When the character sets were adjusted to more complex combinations including upper case letters, numbers and symbols it was noted that the estimated time for completion jumped significantly.  In the default state of using a brute-force attack on a 16 character password, an estimate for over 2 years to completion was provided.

Next a dictionary attempt was made on ictest1.  Using the default wordlist dictionary, this attack took just under 18 seconds to successfully retrieve the password.  Both methods succeeded during this test, however clearly the winner in efficiency was the dictionary method of attack.

**User 2: ictest2 / break1ng**

The next test involved a slightly more complicated password which included a mix of letters and numbers.  During this test the brute-force attack estimated a completion of three days using the more advanced character set including lowercase letters and numbers as well as seven maximum characters.  This test was stopped after five minutes.  The dictionary attack again successfully cracked the password in a matter of seconds using the wordlist file, proving once again to be the winner in this scenario.

**User 3: ictest3 / Bre@k1ng**

During the third test neither methods of attack successfully recovered the password.  The brute-force method used the more complex character set including lowercase letters, uppercase letters, numbers and symbols.  It estimated 2.3 years to completion.  The dictionary attack concluded after twenty seconds of reviewing the entire wordlist.txt file and unsuccessfully being able to retrieve the password.

## Concluding Thoughts

In terms of efficiency the dictionary method of attack was proven to be the winner during these basic tests.  While the brute-force method certainly took much longer to complete, it did prove to be successful during the first test and given enough time for the subsequent tests, it may have proven to successfully retrieve the passwords of the second and third users.

The dictionary attack is only as good as the file it feeds from, in this case a three megabyte text file was the base of its attack, which was successful for the first two accounts.  Given a larger more sophisticated dictionary file to feed from, this method of attack could be potentially the most efficient and effective means of extracting passwords.  While the brute-force method did prove to be much slower, if it had the opportunity to sit in the background without being noticed, over time it could eventually succeed.  In conclusion, for the purpose of these small lab tests, the dictionary attack proved to be the most efficient and effective.

## MD5

MD5, which stands for Message-Digest algorithm 5 is a widely used algorithm for encrypting passwords used in software applications.  It has become a popular specification in many widely used web application programs such as Internet bulletin board software, Content Management Systems (CMS) and general user authentication tools.   Sasaki (Sasaki, Y., Yamamoto, G & Aoki, K., 2007) describes MD5 as “hash function with Merkle-Damg°ard structure, which takes an arbitrary length message M as input, and outputs 128-bit length hash value H(M).”  These hash values are the values that are stored in the database instead of plain text passwords.

While MD5 has been around for a long time and is still used in many systems today, it has come under a lot of criticism in recent years due to vulnerabilities in the algorithm.  In his paper, ‘MD5 to be considered harmful someday,’ Kaminsky (2004) demonstrates that there is a very clear trend regarding the security level of MD5 with regards to its weaknesses and many recommend using newer algorithms such as SHA-2 (Secure Hash Algorithm).  As the security industry continues in advancements towards more secure algorithms, more weaknesses and vulnerabilities will no doubt be discovered over time so it is very likely that we will see many more ways of storing passwords through the use of algorithms in the future.

## Ophcrack

During the lab test, two methods of attack were used in an effort to discover the passwords from the test accounts, brute-force and dictionary.  A third method known as cryptanalysis, which is also supported in Cain and Abel wasn’t used in the lab tests described earlier.  The cryptanalysis approach, like the dictionary method, also relies on a data file in order to carry out its attack.  In the case of cryptanalysis, a file known as a rainbow table is used instead of a basic dictionary file.  These rainbow tables according to Vacca (2009) are lookup tables of every possible iteration of the password hash values.  Ophcrack is an open source password recovery tool, which relies on these rainbow tables to decrypt user passwords.  One of the advantages of the application is the user does not need to be logged into a Windows based environment, they can simply create a bootable disc to access the system and begin cracking attempts on the system passwords.

According to their website, Ophcrack comes supplied with free rainbow tables for Windows XP and Vista.  It also has the capability of using brute-force methods of password recovery for simpler passwords.  Fisher (2011) reviewed Ophcrack and considered it a very easy to use password recovery tool for Windows.  It doesn’t have as many features as Cain and Abel and one of its limitations is that it cannot break passwords greater than 14 characters, however overall it is a very simple to use tool for people with little experience in password recovery.

## Is Cain and Abel Malware?

Certain anti-virus tools claim that it is, however the authors of Cain and Abel claim on their website that “Cain & Abel v2.0 does not infect files, it does not send your passwords over the Internet or anything like that....”  They claim that their software is not dangerous and does not perform any actions without the owner’s consent.  Yin (Yin, H., Song, D., Manuel, E.,Kruegel, C. & Kirda, E., 2007) discuss malware and its nature to access and tamper with information on the computer without the user’s knowledge.  They state that “This behavior is typically exhibited without the user’s knowledge or consent and it is this fundamental trait that separates such malicious applications from benign software.”

Cain and Abel must be installed with the user’s knowledge on their PC under an administrator role in the system.  The software does not perform any means of accessing information or doing any other tasks strictly without the user’s consent.  While the software can be used to retrieve other user passwords on the system, it will only do this when requested by user.  The conclusion is that Cain and Abel, while considered as malware by certain applications, is in fact not malware and simply an application in a long list of others has the potential to be abused if not used for ethical purposes.

## References

Kaminsky, D. (2004) _MD5 to be considered harmful someday_. Cryptology ePrint Archive. Retrieved from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.58.8575&rep=rep1&type=pdf

Fisher, P. (2011) Ophcrack V3.3.1 Review. About.com. Retrieved from http://pcsupport.about.com/od/toolsofthetrade/gr/ophcrack.htm

Ophcrack. (2011). _Ophcrack_. Retrieved from http://ophcrack.sourceforge.net/

Oxid.it  (2011). _Oxid Information_. Retrieved from http://www.oxid.it/info.html

Pinkas, B. & Sander, T. (2002). Securing Passwords Against Dictionary Attacks.  _In proceedings of the ACM Computer and Security Conference (CCS' 02)_. ACM Press.

Sasaki, Y., Yamamoto, G & Aoki, K. (2007). _Practical password recovery on an md5 challenge and response_. Cryptology ePrint Archive. Retrieved from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.66.2517&rep=rep1&type=pdf

Vacca, J. (2009). _Computer and Information Security Handbook._ Burlington, MA: Morgan Kaufmann Publications.

Yan, J, Blackwell, A., Anderson r. & Grant, A. (2004). Password Memorability and Security: Empirical Results. _IEEE Security & Privacy Magazine_, p. 27. September/October, 2004.

Yin, H., Song, D., Manuel, E.,Kruegel, C. & Kirda, E. (2007). Panorama: Capturing System-Wide Information Flow for Malware Detection and Analysis. _ACM Conference on Computer and Communications Security_, Alexandria, VA, October 2007.
