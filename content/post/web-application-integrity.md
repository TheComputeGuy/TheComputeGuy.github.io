---
title: "Google's Web Application Integrity proposal - DRM for the Web?"
date: 2023-08-01
description: "My thoughts on Web Environment Integrity, a DRM-like proposal for the web"
tags: ["Web"]
---

## What is WEI after all?

Link to the explainer - [https://github.com/RupertBenWiser/Web-Environment-Integrity/blob/main/explainer.md](https://github.com/RupertBenWiser/Web-Environment-Integrity/blob/main/explainer.md)

**Why** - Websites want to be able to trust that users are running secure client environments, and that real users are using the website. This is useful primarily in the advertising business where advertisers want to make sure that humans are seeing their ads, and not bots. The explainer mentions other uses like eliminating fake engagement on social media, cheat detection in online multiplayer games and detection of malicious software for banking software. In short, the authors want a *low-entropy* method to identify real and *good* users from automation, in a privacy-preserving manner.

**What** - An API that lets the website request an "attestation token" that validates key aspects of the client environment. Cryptographic signing of the token will prevent tampering.

**Who** - The attestation will be provided by a third-party, and can come from different sources, most probably implemented via an OS-level mechanism, like [App Attest](https://developer.apple.com/documentation/devicecheck/validating_apps_that_connect_to_your_server) on Apple devices or [Play Integrity](https://developer.android.com/google/play/integrity) on Android, or a TPM-based token generation mechanism in Windows. The website can then evaluate the attestation and act accordingly.

---

Recently, four Google engineers put out a new proposal for attestation and integrity on the web - Web Environment Integrity. Put simply, it is a mechanism for websites to understand whether the client making the request is a "secure environment", following which, they can decide whether or not to serve this request, or how to treat this user. This definition of a *secure environment* is not defined, and therein lies the slippery slope.

The proposal starts by mentioning how _Users often depend on websites trusting the client environment they run in_, but then quickly devolves into how it is a great way to ensure ads are seen by real eyeballs and other *business* cases rather than user benefits. Having said that, this proposal (which is being quickly [shipped into Chromium](https://github.com/chromium/chromium/commit/6f47a22906b2899412e79a2727355efa9cc8f5bd)) has potential to restrict the *openness* of the web and our computers, the same openness which has gotten many of us into this world of computer software and hardware. So what are these concerns?

First things first, *attestation and integrity* have potential to be DRM for the web, and DRM doesn't have a great reputation in the community, for all its business virtues. Simply put, this means that websites can now decide whom to serve and whom not to, and with reliable indicators via WEI tokens. Your bank might decide that Firefox on Qubes OS is not a safe enough environment to access internet banking, or $big_ad_co won't let you access their shiny new platform without installing their data collection agent on your device. Or your streaming company can decide that your usage of an ad blocker is hurting them too much, and decide not to serve you unless you uninstall it. And the list goes on. The attester can decide what variables to factor into attestation, including the plugins installed, browser used and other software installed on the computer, not to mention, jailbreak status of the device (e.g. - rooting in Android). Thus, it makes it easier for businesses like the big G to make it hard for devices running tools and software that hurt their bottom line from accessing the web. Given their market dominance and past actions, it is evident that Google will have a noticeable presence in the attestation process.

Then there are the other issues, like who gets to be an attester, and what parameters they use to decide their attestation status. If the attesters becomes an elite club dominated by big tech, it will soon become a way of enforcing their standards on the web, with the ease of doing so depending on their market share. We've already seen such behaviour for good and bad in walled garden mobile platforms on iOS and Android. Similarly, attesters can use their own *judgement* to decide whether or not they consider a device and browser as *secure*. Lastly, there are user privacy concerns, including whether this proposal allows the attester to now track user behaviour and browsing activity and whether WEI has potential to enhance user fingerprinting (the proposal authors make a pinky promise to not use WEI for fingerprinting).

Attestation isn't a new concept - Apple, along with Cloudflare and Fastly, implemented [Private Access Tokens](https://developer.apple.com/news/?id=huqjyh7k) or PATs, a similar concept to determine whether an HTTP request is coming from a *legitimate* client. Microsoft has been pursuing this path since early 2000s too, via it's [Next-Generation Secure Computing Base](https://en.wikipedia.org/wiki/Next-Generation_Secure_Computing_Base) which was later killed owing to negative reception. So why the big furore now? For one, despite it not even being on the standards track, Google is already integrating it into Chromium. But the bigger worries cast by the community stem from the large share that Google and Chrome commands over the browser market, and the impact of its actions and directives on the directions that websites take. Chromium has been a hallmark of quality software and continuous innovation, with a lot of contributions to improving the web. But proposals like these have potential to do more harm than good (Occam's Razor is always to be applied).

In the best case, this proposal cuts down on CAPTCHAs seen by users and spam and scrapers from the web. But going off the defined path, it can quickly become a way to suppress *insecure environments*. This would sound the death knell for many custom operating systems and browsers (both of which are extremely complicated to develop and secure), but more generally, it would lead to the decline of the freedom of writing software, especially considering the shift of compute to the browser. OS and browser authors might have to go through a lengthy attestation process, possibly multiple times, as different attesters adopt differing standards.

Mozilla has already [declared](https://github.com/mozilla/standards-positions/issues/852) that it opposes this proposal, and Brave has also [mentioned](https://community.brave.com/t/braves-stance-on-web-environment-integrity/497890/9) that it does not intend to ship WEI. There has also been a significant discussion on various platforms, including [conversations](https://groups.google.com/a/chromium.org/g/blink-dev/c/Ux5h_kGO22g/m/XCAIgPtxAQAJ) on the blink-dev mailing list. 

As a user on the web, you might be neutral about this proposal, as it does not affect you one bit - rather reduces CAPTCHAs and spam. But, lets not forget that the modern web is built on top of the voluntary hardwork of many computer scientists and software engineers who hacked their way into building more competitive OS and browsers, believing in the fact that their computers are owned by them and nobody can tell them what to do with their devices. A natural followup question comes along - had Microsoft implemented an equivalent of this in 2006 with Internet Explorer and had websites started denying users access to untrusted browsers, would we have gotten Chromium? Or would we still be stuck in the era of IE?

---

There has been a significant discussion against WEI all over the internet, often heated. Let's look at some positives though. 

Whether or not we like it, the average internet user does not want to pay for content, and ads have taken over the monetization of the web (partly also because paying every single website for their content and services might quickly become a huge pain for the users, and digital businesses have worsened the situation with subscriptions and making it difficult to cancel them). And as with everything that gets famous, gamification of the advertising ecosystem started, with some ad frauds raking in millions of dollars with no tangible benefit to the advertiser or the ad network (Cybereason's Malicious Life podcast recently released [two](https://open.spotify.com/episode/2isfuKGQ2GS0Oxxu86kW5C) [episodes](https://open.spotify.com/episode/18hi3GkhrJOK5YT0wHJLeG) on the topic). With ads being a major revenue source for most large tech companies today, it quickly has become an important problem for some of our most brilliant engineers to solve. Attestation definitely will give these websites a strong signal that their product is going to the right customers, and not bots.

Then there's also the point about scraping and illegal use of intellectual property. With the growing furore over OpenAI's use of information all over the internet for training their landmark GPT models, this gains importance. Websites can simply decide not to make content available to clients that are identified as scrapers by the attester. A similar argument can be made about crawlers and search engine spiders. While website owners relied on bots respecting robots.txt, WEI can make it possible to simply disallow them from crawling your website.

Lastly, the proposal also mentions *holdbacks*, purposefully denying websites attestation information "for a meaningful number of requests over a significant amount of time" to prevent websites from totally relying on WEI as a source of truth to serve information and avoid alienating users.

---

Even if we concede that this proposal has been put out there with the best intentions of fighting fraud and spam with the least user impact, the intended use of a technology does not deter its abuse. 