---
title: "Professional Experience"
---

I've been working on large-scale government and enterprise projects since the summer of my sophomore year in 2018. Here are some glimpses of my work experience:

### Cybersecurity Engineer at [Visa Inc.](https://usa.visa.com/)
#### Denver, CO | June 2024 - Present | Full-time
* Going back to corporate after school for 2 years, I joined the cybersecurity automation team in Visa as a cybersecurity engineer. The title is a misnomer though, my role had a solid overlap of software and cybersecurity.
* My primary role was to develop cybersecurity automations which helped Visa's cyberdefense, detection engineering, endpoint engineering, data loss prevention and network security teams. I am fortunate to be able to touch almost all aspects of cybersecurity while doing the work I enjoy the most - writing software.
* The primary highlight of my work at Visa was Legatus, a generative AI driven agentic framework, designed to emulate an entry-level cybersecurity analyst doing incident response. We built Legatus from scratch at Visa, and by designing robust integration interfaces before MCP (Model Context Protocol) existed, using standard design principles and context engineering, we built a reliable agentic framework.
* Along with a myriad of cyberdefense use cases, I took an active part in designing secure ways for Legatus to run AI-generated Python code in a sandboxed environment, as well as designing an in-house version of computer use for the browser, to investigate suspicious weblinks.
* Another exciting capability that I built for Legatus was to plan and execute highly specific technical tasks simply from a textual description of a standard operating procedure with zero human involvement.
* Apart from Legatus, I worked on developing and maintaining over 200 automation scripts and a SOAR-based automation framework developed by our team, writing algorithms for credential discovery, applying traditional ML for network security and data-loss prevention, etc.
* **Skills** - Python, Django, IBM QRadar SOAR, Splunk Phantom SOAR, Elasticsearch, Splunk, Ansible, Docker

### Security Researcher at [CyFI Lab](https://cyfi.ece.gatech.edu/)
#### Atlanta, GA | August 2022 - May 2024 | Part-time
* As I started my graduate school, I joined [Prof. Brendan Saltaformaggio's](https://saltaformaggio.ece.gatech.edu/) CyFI Lab as a malware researcher, where I conducted two research projects - one on server-side credit card skimmers, and another on ad fraud using Electron-based cross-platform malware.
* I developed multiple malware detection pipelines, which utilized many concepts in malware analysis, including - deobfuscation, static analysis, data flow traceback and file clustering, many of which aren't supported via libraries in PHP or Python.
* The highlight for me was developing a clustering algorithm - skimmer malware tends to be split over multiple files spread all over the filesystem. I utilized static and controlled dynamic analysis to develop a clustering algorithm that identified linked and imported files.
* For Windows malware, I designed a new Windows 10 sandbox, which would execute binaries, capture network traffic and obtained related forensic artifacts, all in an automated fashion. This was a strong alternative to the dated Cuckoo sandbox.
* I also built a CI/CD workflow to run the malware detection workloads on AWS, utilizing containerization and AWS services like Batch and Lambda.
* **Skills** - Python, Web Malware Analysis, Academic Research, Docker, AWS

### Cybersecurity Intern at [Visa Inc.](https://usa.visa.com/)
#### Denver, CO | May - August 2023 | Internship
* As a cybersecurity intern at Visa, I developed a threat history and IP reputation database to track malicious web scanners and identify their *modus operandi*.
* The aim was to improve automated detection systems, tune alerts and reduce the mean-time-to-respond, reducing the visibility that attackers get into Visa's network.
* Utilizing various open-source and proprietary threat intelligence feeds, attack patterns, origin and behaviours were identified and recorded.
* A historical database of tactics, techniques and procedures (TTPs) was generated, cataloging over 200 unique indicators useful for incident response.
* Techniques like threading, queues and locks were leveraged to build a scalable system suitable to be deployed to production.
* **Skills** - Python, Cybersecurity Automation, Elasticsearch, Splunk, IBM QRadar, Ansible

### Software Engineer at [Fidelity Investments](https://www.fidelity.com/)
#### Remote (India) | August 2020 - August 2022 | Full-time
* In my first full-time role, I worked on Netbenefits, Fidelity's 401k product. I worked as a full-stack software engineer on the Netbenefits Homepage team.
* My work at Fidelity ranged from improving coarse-grained authorization ('Entitlements') systems, developing accessible user interfaces and building a cloud-based cache system for a heavily-used API, among others.
* The highlight of my time at Fidelity was leading a full system rewrite from scratch - the architecture and capacity planning discussions, performance testing and design discussions were a great learning curve. We rebuilt the Netbenefits homepage to have a modern and accessible UI, and modularized for maintainability.
* I also got to learn and play with AWS (Solutions Architect - Associate [certified](https://drive.google.com/file/d/1e-ZqUa1LIBAhvFBYBAbjKOaCU6CwuxEt/view?usp=sharing), various internal projects), Docker and Kubernetes (by migrating applications from AWS ECS onto Kubernetes), which built my skills in DevOps.
* As an aside, owing to the impact of the pandemic, I was able to try additional roles in the team temporarily, including that of a scrum master. This was a rewarding experience, allowing me to look beyond the clouds into the world of business and product management.
* **Skills** - Java, Python, Javascript, Docker, Kubernetes, Product Management

### Co-Founder at Project Bridge
#### Remote | December 2019 - January 2022 | Part-time
* Project Bridge was an initiative to build a student community to help each other grow. It was a great learning curve for me to understand not just how to build technology, but how to get people to use it.
* I contributed to building the technology supporting the platform for Project Bridge, including the [Android app](https://play.google.com/store/apps/details?id=com.maverick.bridge), the website and a whole host of hacky services that made up our backend, including Firebase and Google App Scripts.
* Working outside the technology domain was the bigger learning - including how to get your team to believe in your vision and how to get customers to believe in what you are trying to do.
* Although Project Bridge did not manifest into a startup or a large platform, I gained valuable skills in people management, product management and marketing, which *might* not be learnt as effectively in a B-school classroom.

### Software Engineering Intern at [Fidelity Investments](https://www.fidelity.com/)
#### Chennai, India | May - July 2019 | Internship
* In my first corporate role, I built a web-based video conferencing system (before the pandemic-fueled boom of Zoom and friends)
* I studied and used WebRTC and socket programming towards this goal, including by building a screen-sharing functionality and live chat from scratch.
* I also built a role-based authorization framework to provide additional privileges to the meeting host, a session server and other utilities.
* The system was deployed to AWS, giving me a taste of server administration and devops. I utilized a combination of shell scripts and Docker to build a playbook for deployment.
* **Skills** - Node.js, Python, Docker, AWS, Lua

### Intern at [Robert Bosch Center for Cyber-Physical Systems](https://cps.iisc.ac.in/)
#### Bengaluru, India | May - July 2018 | Internship
* This was my first foray into building large-scale production systems. I contributed to IDEAM, which is today's India Urban Data Exchange [(IUDX)](https://iudx.org.in/), the middleware supporting India's Smart Cities Program.
* I developed [Adapters](https://github.com/rbccps-iisc/isc-adapters/tree/shubham), a glue to connect various data producers to the middleware, and the middleware to the consumers, solving the problem of protocol interoperability. 
* It enabled seamless integration of sensors using many different protocols (including HTTP(S), MQTT, LoRA, BLE) to communicate with the middleware.
* Adapters adopted many distributed systems techniques, including message passing, queues, parallel processing and CAP considerations in system design.
* The system was deployed and tested in real-time using a network of weather monitoring sensors and live security camera feeds from the city of Bengaluru.
* **Skills** - Python, MQTT, Redis, Distributed Systems, Celery
