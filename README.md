#  Threat model for streamers

Threat model for the "new" hype and ways to protect

![GitHub last commit](https://img.shields.io/github/last-commit/Skeptical-Security/threat_model_streamers?label=last%20update%3A)

## What's a threat model?

[OWASP](https://owasp.org/www-community/Threat_Modeling) defines threat modeling as the act of "identifying, communicating, and understanding threats and mitigations within the context of protecting something of value."

In other words, it consists of taking the appropriate security measures according to your situation and your activities.

For example, security researchers do not have the same threat model as standard users, as their activities (e.g., online searches, exploiting bugs to demonstrate vulnerabilities) can be considered as particularly sensitive.

**Online streamers are primary targets** in 2023, especially the most popular ones, as they usually generate substantial revenues and have a large audience (hundred of thousands, perhaps millions of viewers/subscribers).

Note that having "only" hundreds of subscribers is enough to become an attractive target.

## Disclaimer

This very short guide is based on personal thoughts/researches and only provided for convenience. I'm not trying to speak with authority.

It's only a text-based document to keep things as simple as possible (no diagram, etc).

## Steps by steps

### What is a streamer exactly?

> A person who broadcasts his or herself in real time (referred to as streaming) while playing video games is known as a streamer. Those who want to stream their play may do so through online platforms such as Twitch and YouTube

> Many streamers attempt to make it a profession, dedicating full-time hours in hopes of receiving a steady pay check. Streamers make money from their viewers in the form of donations, subscriptions, sponsors, and advertising. As video game streaming has seen a large rise in popularity, it can be quite difficult to generate income as a streamer as the market is quite competitive.

[Source: computerhope](https://www.computerhope.com/jargon/s/streamer.htm)

### Things that can go wrong

* attackers might hack the account to delete published content, which could cut your revenues
* attackers might hack the account to spam or scam viewers, or spread malware
* attackers might disclose your personal info (PII) publicly, including your online habits but also your physical address, your friends, and family
* attackers might attempt to DoS your connection
* attackers might hack the account to attack your other businesses (streamers usually have multiple ways to monetize their audience)
* attackers might be politically driven and hack you to spread their messages (less probable but not impossible)
* attackers might target the entire platform (way less probable, but it already happened, for example, with the [Twitch leaks on 4chan](https://arstechnica.com/information-technology/2021/10/twitch-admits-to-major-leak-exposing-source-code-creator-earnings/))

### Techniques that could be used

While it's not exhaustive, the following techniques seem probable:

* phishing, spear phishing (more targeted phishing)
* use of community forums and chats to send you tricked payloads
* more "direct" social engineering, like malicious phone calls
* social engineering on your collaborators (e.g., community managers, associates) 
* technical exploits targeting the streaming platform or your personal websites, social platorms or eShop (e.g., merchandizing)
* if they manage to compromise your machine: ransomware (video files, other documents), RATs (Remote Access Trojans), reverse shells, 
* denial of service on your wireless connection if your address is known/leaked (the streaming platform itself usually has anti-DDoS systems, but the streamer might be "DoSed" directly at home)

### Robust protections

* use app-based/Yubikeys 2FA/MFA (double/multi-factor authentication) everywhere, including you and all your collaborators (SMS should be avoided unless it's the only method available)
* use password managers to generate and autofill **long and random** passwords for your online accounts
* have a robust **and tested** backup strategy (may require a budget)
* be extra careful with your social networks (e.g., OSINT, social engineering attacks)
* use secure browsers with adblockers (may sound paradoxical for a streamer ^^ but threat actors might leverage ads) and [uBlock origin](https://ublockorigin.com/)
* keep your machine and applications up-to-date and use anti-malware solutions
* always use secured hardware (e.g., don't use cheap wireless accessories)

Also you might follow [the short list](#short-list)!

## Underestimated threats

### Mental health

**Online Harassment** can literally destroy you. It may include hate speech, bullying, or inappropriate comments. Of course, platforms allow moderating or ban people who cross boundaries.

However, it can be bypassed in multiple ways. Streamers must take regular pauses, perhaps vacations. The human brain is not meant for such pressure (constant stimulation, especially negativity).

### Intellectual property

Streamers must be really careful with copyright laws or DMCA, as things can turn bad quickly. It's not uncommon for companies and other licence holders to claim their rights.

Streamers also have rights, so plagiarism or unauthorized "sampling" can be stopped. Do not hesitate to report it. Although, it's not illegal to criticize the content of other streamers, so it's sometimes difficult to stop shaming and other kinds of harassment.

## Short list

* if possible, use a pseudo instead of your real name (but it will be hard to keep it private, especially if you become very popular)
* use a new email address **dedicated** to your stream
* prioritize robust platforms for your "merch" (e.g., Shopify, Squarespace)
* **secure payments** if you use alternative methods and even consider higher plans (professional/business offers) if you use Paypal
* secure all your uploads: remove EXIF data from documents, especially images, and don't expose family and friends if possible
* don't mention your physical location if possible (might be very hard to keep it private if you become popular)
* have a robust internet connection, which is not just good for your audience but also for your safety (maybe invest in a more expensive plan that may include security options)
* consider using a VPN permanently
* take some privacy measures, as other online activities could potentially harm your reputation

## Nothing is bulletproof

**Least privileges** is a pretty self-explanatory term. Don't give too much permissions, including to your own accounts, if that's not necessary.

[This example](https://www.theverge.com/2023/3/24/23654996/linus-tech-tips-channel-hack-session-token-elon-musk-crypto-scam) reminds us motivated attackers will find their way eventually.

Cybercriminals managed to make the YouTube platform remove several popular channels owned by Linus, a famous tech YouTuber who is perfectly aware of  security threats.

The attackers leverage social engineering, phishing emails, and malicious payloads in seemingly-harmless PDFs to steal session tokens and ultimately hack the targeted accounts and maintain a rogue access despite passwords updates and other classic countermeasures.

The poisoned attachments were not sent with the first email. The attackers gained the trust of one of the staff's member, offering a generous but fake sponsorship, taking their time to look credible. Besides, it was not an `.exe` file that most people and email clients would flag. Indeed, there are many other formats to hide executables (e.g., `.scr`) and trick the victims into downloading malware.

The Google's platform appeared to be unprepared for such incidents, as the incident response team was not allowed to communicate with creators directly, according to the tech YouTuber, leaving the victims with no answer for hours.

Worse, modifying critical settings in the interface did not require re-entering any password, an additional security layer that many platforms provide, including Google, but not on this interface! Because the victim had managment access, his session tokens granted the equivalent of an admin access.

Pretty scary, so, more than ever:

* don't click on any attachment blindly: maybe ask for another format
* don't trust the platform, even if it's Google. Probably the kind of things creators will now have to check before they even choose their platform. Such disaster will likely happen again.
