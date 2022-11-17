# Use Cases & Threat Models

## Participate
- https://github.com/antifraudcg/use-cases/issues

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Introduction](#introduction)
- [Use Cases](#use-cases)
  - [Account Creation](#account-creation)
  - [Account Takeover](#account-takeover)
    - [Credential Cracking](#credential-cracking)
    - [Credential Stuffing](#credential-stuffing)
    - [Phishing](#phishing)
    - [Token Theft](#token-theft)
  - [Invalid Traffic (IVT) in Advertising](#invalid-traffic-ivt-in-advertising)
  - [Ecommerce Fraud](#ecommerce-fraud)
    - [Scalping](#scalping)
    - [Sniping](#sniping)
  - [Payment Fraud](#payment-fraud)
    - [Carding](#carding)
    - [Card Cracking](#card-cracking)
    - [Cashing Out](#cashing-out)
    - [Promotion Abuse](#promotion-abuse)
  - [Sensitive Data Scraping](#sensitive-data-scraping)
    - [Scraping](#scraping)
  - [Online Spam & Fake Engagements](#online-spam--fake-engagements)
    - [Skewing](#skewing)
    - [Spamming](#spamming)
  - [Denial of Service](#denial-of-service)
    - [Denial of Service](#denial-of-service-1)
  - [Theft of Intellectual Property](#theft-of-intellectual-property)
  - [Unauthorized access](#unauthorized-access)
- [Capabilities](#capabilities)
  - [Motivation](#motivation)
  - [Enumeration of Capabilities](#enumeration-of-capabilities)
  - [Qualities of Capabilities](#qualities-of-capabilities)
- [References](#references)
- [Glossary](#glossary)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Introduction

Our goal is to capture a non-exhaustive, but highly diverse list of fraud and abuse that
has at least partial reliance on online workflows/technologies that are in the scope of
the W3C Anti-Fraud Community Group (CG). The CG will use this to help focus future
discussions and proposals, but just because a certain abuse tactic or fraud method is
not explicitly included does not mean that it is out of scope for the CG.

## Use Cases

### Account Creation

Account authentication and account creation workflows are abused from bad actors who manually or programmatically attempt to create accounts that they can subsequently use to abuse a platform.

Bad actors misrepresent their identities during the account creation process. There are three main approaches, known in the fraud industry as:

* **Identity theft** - wherein a bad actor claims to be somebody that they are not, using a legitimate identity that was previously compromised.  
* **Synthetic identity** - wherein a bad actor uses a combination of fake and real identity attributes to create a new ‘synthetic’ identity that can be partially verified, thus bypassing verification controls.  
* **1st party fraud** - wherein a person submits their own data, perhaps with minor alterations and then subsequently claims to be a victim of identity theft.  

### Account Takeover

Bad actors use a variety of techniques to obtain access to an account. Once an account is compromised, user credentials or profile data (address, email, phone, etc) are often modified to elongate the window of opportunity for abuse. Changes to account profile attributes or passwords are often the first sign that an account has been hijacked. From there, bad actors can instigate all sorts of financial crimes, which are naturally specific to the compromised institutions. This includes payments fraud, crypto-jacking, online ecommerce, benefits fraud, and compromised lines of credit.

#### Credential Cracking

See [OAT-007 Credential Cracking](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-007_Credential_Cracking.html).

#### Credential Stuffing

See [OAT-008 Credential Stuffing](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-008_Credential_Stuffing.html).

#### Phishing

Phishing is a type of social engineering where an attacker sends a fraudulent (e.g., spoofed, fake, or otherwise deceptive) message designed to trick a person into revealing sensitive information to the attacker or to deploy malicious software on the victim's infrastructure like ransomware ([https://en.wikipedia.org/wiki/Phishing](https://en.wikipedia.org/wiki/Phishing))

#### Token Theft

Session credentials for authenticated users are traditionally stored as cookies, which are trivially extracted by malware running with user privileges. Services traditionally defend against this by associating certain invariant client properties (screen size, webGL renderer, etc) with a user’s cookie, and rejecting the session credential (forcing the use to re-authenticate) if it appears that the cookie is used on a new device.

### Invalid Traffic (IVT) in Advertising

Invalid traffic is any activity that doesn't come from a real user with genuine interest. It can include accidental clicks caused by intrusive ad implementations, fraudulent clicking by competing advertisers, advertising botnets and more (per [Google’s](https://www.google.com/ads/adtrafficquality/invalid-activity) definition).

See [TAG IVT Taxonomy](https://f.hubspotusercontent40.net/hubfs/2848641/Invalid%20Traffic%20Taxonomy%20(IVT)/IVT%20Taxonomy%20v2.0.pdf) and [Invalid Traffic Detection and Filtration Standards Addendum](http://mediaratingcouncil.org/IVT%20Addendum%20Update%20062520.pdf) for more details in the underlying threat models in advertising.

### Ecommerce Fraud

Automation is used to abuse the purchase workflows of digital or physical goods. Bad actors are able to complete purchases faster (e.g. sneaker bots, auction sniping) and at larger quantities compared to other buyers.

#### Scalping

See [OAT-005 Scalping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-005_Scalping.html).

#### Sniping

See [OAT-013 Sniping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-013_Sniping.html).

### Payment Fraud

Payment workflows are abused using automated or manual techniques in order to buy merchandise using stolen payment cards, validate stolen payment cards, brute force and crack payment cards, or abuse promotions.

#### Carding

See [OAT-001 Carding](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-001_Carding.html).

#### Card Cracking

See [OAT-010 Card Cracking](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-010_Card_Cracking.html).

#### Cashing Out

Fraud in eCommerce channels typically takes advantage of compromised credit cards, or compromised accounts linked to credit cards. Fraudsters will purchase high value items such as laptops with the intent of reselling them. As a result, merchants incur ‘doubled’ losses - the loss of the merchandise and then another loss due to a payment chargeback. In other cases, fraudsters utilize these schemes to purchase gift cards which are then resold on various marketplaces. Gift cards are often employed as a money laundering tactic, and as means of converting stolen credit cards to cash.

Fraudsters frequently employ remailer services in order to cover their tracks. Remailers are innocent 3rd parties who provide an address for shipping and then send the goods on to another location.

Also see [OAT-012 Cashing Out](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-012_Cashing_Out.html).

#### Promotion Abuse

Brands will frequently offer promotions to accelerate adoption by new users. Once fraud rings realize that they can successfully exploit sign up flows at scale, they begin to target these organizations with high volumes of new accounts, in order to reap promotional benefits.

Paypal was recently the victim of such an attack. Paypal announced that 4.5 million fake accounts were created to take advantage of a promotion where new users received a free balance of $5 or $10. Paypal announced this in the Q4 2021 earnings call. This news, along with slow growth in legitimate users, was followed by a 25% drop in stock price.

### Sensitive Data Scraping

Sensitive data (e.g. user profiles, product prices, user generated content) that is available in the public domain (account authentication may or may not be required) is programmatically exfiltrated at scale for use elsewhere.

#### Scraping

See [OAT-011 Scraping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-011_Scraping.html).

### Online Spam & Fake Engagements

Mass spammy user generated content (videos, reviews, comments, likes, audio/video playback). Bypassing creator's restrictions on accessing content. A particular subclass is fake engagement where the attacker wishes to inflate (or deflate) the listing’s reputation or ranking via automated, inorganic engagement with the page.  Engagements may be active (e.g. A click) or passive (e.g. an impression, or time spent on site). In some cases, filtration decisions need to be made in real-time (e.g. to report live-stream concurrent viewership).

Fake engagements may be _simulated _(i.e. generated by something other than the claimed platform), _automated_ or _hijacked _(i.e. generated on the claimed platform, but without genuine user intent), or _incentivized_ (i.e. generated by a human in exchange for an undisclosed incentive).

#### Skewing

See [OAT-016 Skewing](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-016_Skewing.html).

#### Spamming

See [OAT-017 Spamming](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-017_Spamming.html).

### Denial of Service

Unwanted traffic sent for the purpose of making a service unavailable for legitimate users.

#### Denial of Service

See [OAT-015 Denial of Service](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-015_Denial_of_Service).

### Theft of Intellectual Property

Attackers are sometimes after the developer’s intellectual property. It may materialize as scraping the developer’s database (product catalog, map tiles, search results), or re-selling the service under a different brand (e.g. video stream pulled into a foreign player).

### Unauthorized access

Attackers seeking private data (e.g. bearer tokens, passwords, form entries, emails) belonging to a user will attempt to compromise the system holding this data. In addition to the mechanisms listed in the “account takeover” category, this may be possible through malware or exploitation of security bugs. 

### Domain Spoofing
Domain spoofing (also referred to as Domain Laundering) is a form of Sophisticated Invalid Traffic (SIVT) in which a false representation is made about the domain associated with an ad impression. Two examples are when the domain in the ad request is different from the domain of the actual inventory being supplied or the actual ad is rendered to a different website or application than the one identified in the ad request. (See “False Representation” on page 8 of the Trustworthy Accountability Group (TAG) TAG Invalid Traffic Taxonomy v2.0.)

## Capabilities

### Motivation

Many of the heterogenous use cases listed above are rooted in common patterns of deception: For example, DoS, invalid ad traffic, and bulk account creation are amplification attacks (i.e. a small number of users presenting as many distinct users) with vastly different latency requirements (i.e. how much time we have to decide whether to reject or accept a request).  

Owners of these disparate use cases may ask a common set of questions, for example: Are these N requests coming from \~N distinct clients? Are intentional users making these requests? Are these users coordinating with the intent to deceive?  

Such questions are answerable if the defender has the requisite “capabilities,” each of which provides a specific inference that may be enforced upon on its own, or in combination with inferences from complementary capabilities. These capabilities may be backed by a variety of sources of truth, including high-entropy client signals, hardware integrity checks, white-box cryptography, reputation ledgers, and other relevant technologies yet to be identified.   

### Enumeration of Capabilities

This section lists the capabilities that we have identified as useful for our key use cases. (Think of these as the requirements we have for our key use cases, deferring implementation opportunities or challenges to a subsequent design proposal). 

#### Recognize whether the same device is seen again in the context of the same identity
This applies to both within the same domain or across domains. Detecting a same device returning would traditionally happen through storing IDs persistently in the browser and reusing them when a device is seen again. The lifespan of detection needs to be at a minimum 7 days.  

##### Use cases
Account Creation: Seeing an identity being used with a device it has never been seen with before (or that's very different from the devices it has been seen with before) can indicate identity theft where a fraudster uses a known identity to open new accounts.  
Account Takeover: An account that is taken over will be accessed from a new device, i.e. a device it hasn’t been used with before. This can be treated as an additional risk compared to devices that have been regularly seen with said account. The lifespan during which a device can be recognized as ‘seen again’ is very relevant here, as shorter windows will make every account access look as if it came from a never-before-seen device.  
1st Party Fraud: A person committing 1st party fraud and then claiming to be a victim of identity theft can in some cases be detected by recognizing that their own device was used to commit said fraud.  

####  Recognize whether the same device is seen again in the context of multiple identities
Similar to the above, but recognizing the usage of the same device with different identities. 

##### Use cases
Account Creation: Fraudsters often steal multiple identities. Seeing many different identities’ data coming from the same device is a high risk signal, since legitimate users mostly use a single identity with their device.  
Account Takeover: A similar point to the above holds for account takeover when e.g. a fraudster is using a list of leaked usernames and passwords to takeover multiple victims' accounts. Recognizing that these logins into multiple accounts are happening from the same device can be used to indicate high risk.  

#### Retrieve a device’s IP address
Knowledge of the IP address offers many benefits in the fight against identity fraud:  


##### Related capabilities
###### Build and maintain a reputation of networks connecting to your system (datacenters, geo-hopping proxies) (from VPN/TOR detection)
VPN/TOR detection: Many cases of fraud are committed from devices on VPNs. This is therefore a valuable risk signal.  


###### Distinguish client endpoints for rate limiting, fraud detection, or preventing repeat abuse 
Many use cases are currently addressed by treating IP as a relatively unique identifier: Similar to the use cases above. For example: 
Account Creation: seeing unusual numbers of account creations from the same IP or IP range indicates risk.

###### Distinguish client endpoints for risk based authentication / resource binding
Account Takeover: seeing an identity with an IP address that it has never been associated with. These are ways in which knowledge of the IP address can contribute to risk insights.  
IP block nature: If certain IPs within a block have been associated with fraud, the overarching block can be preemptively labeled as more risky.
Approximate location information: IP addresses are associated with geolocation information. During account creation if an IPs geolocation is far removed from the submitted address this indicates higher risk of fraud.  

###### Know a client endpoint's network and which client endpoints belong to a network


#### Know the geographic location of the device
This refers to geolocation information through GPS / Wi-Fi triangulation, as this offers additional confidence over only IP-based geolocation, particularly when proxies are being used.  

#### Know that the geographic location of a device is being manipulated
Determine instances where the user's actual location is not aligned with the stated location. Users may disguise their location to be in a more trusted country to bypass anti-abuse defenses.  
Determine instances where the page being visited claims to be another, so as to manipulate ad prices.  

##### Use cases
Account Creation: Similar to how IP geolocation helps, discrepancies between device geolocation and a submitted address increase fraud risk.  
Account Takeover: When an account is taken over it generally happens from a different location than where the victim usually has been using their account. Also, impossibly fast jumps in geolocation between two logins for an identity are indicators of account takeover. (I.e. a person logging in from New York and 5 minutes later from San Francisco is not physically possible). 
1st Party Fraud: A person committing first-party fraud can change their IP address but still be in the same physical location. Detecting fraud being committed from the same location is an indicator of 1st party Fraud.  
Ad Fraud: Alterations to the apparent location of a user can distort publisher metrics related to CPC and CPM.  

#### True traffic origin and destination
Determine instances where the page being visited claims to be another. This is relevant in ad fraud where such tactics can be used to manipulate ad prices.  

#### Know that the device is a real device and its type
This includes detecting the device’s type and whether or not it is running in a simulator.  

##### Knowledge of the device types used improves accuracy of fraud detection:

Detecting the device types used by a fraud ring improves accuracy when filtering e.g. an IP block, in order to avoid blocking good users who are not in the fraud ring.  
Detecting the device types or brands used by a good identity informs risk when unexpected device types or brands are used for that identity. (e.g. traditional Chromebook user switching to a Macbook).  

#### Know that a human user is interacting with the device
This comes down to having the capabilities required to detect bots/headless browsers/scripts. Invalid traffic defenses should be able to determine the realness and human qualities of ad interactions, for example:  

-Real and authentic mouse/keyboard/touchscreen inputs.  
-"Non-human" low latency of reaction time.  
-"Non-human" low or artificially high variability in time between actions/user-events.  
-Authenticity of device, environment, and event are critical inputs to effective assessment of authentic interactions.  

##### Use Cases
Account Creation: Fraudulent account creation is often automated and can employ bots. Identifying an automated user from a human user is a powerful risk indicator.  
Account Takeover: A large-scale account takeover attack can be automated. Also, account takeover can be bootstrapped through a set of logins and snooping before stealing funds. This process of logins and snooping can also be automated.  
Ad Fraud Detection

#### Coordinated Attack Detection

The detection of threats that are generated by multiple actors working in a unified, synchronized, and coordinated manner. Such attacks include fraud attacks on commercial organizations, or ad fraud tactics such as coordinated clicking from a ring of publishers who all agree to click on each others' ads (eg. co-clicking, bad actor rings).

### Qualities of Capabilities

Capabilities should be unambiguous and specific in their inference, avoiding broad qualitative verdicts in favor of specific attestations or refutations (e.g. a boolean verdict attesting to a specific fact). The utility of a capability for a specific use case may be contingent upon certain criteria, such as latency (how quickly can I get an answer?), accuracy (how many false positives/negatives can by use case tolerate?), friction (can I potentially interrupt the user, or do I need a passive assertion?), and others.

## References
* [OWASP automated threats](https://owasp.org/www-project-automated-threats-to-web-applications/)
* [TAG IVT Taxonomy](https://f.hubspotusercontent40.net/hubfs/2848641/Invalid%20Traffic%20Taxonomy%20(IVT)/IVT%20Taxonomy%20v2.0.pdf)


## Glossary
* **Manual fraud** - Fraud executed manually by a human without the use of software, scripts, or other tools that automate the process.
* **Remailers** - An anonymous remailer is a server that receives messages with embedded instructions on where to send them next, and that forwards them without revealing where they originally came from.
