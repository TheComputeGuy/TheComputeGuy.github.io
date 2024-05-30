---
title: "Projects"
---

Some projects that I enjoyed building:

### NoSkim
* NoSkim was developed as a part of a research study about server-side credit card skimmers on ecommerce websites.
* It is a cloud-based sandbox which utilizes Regex and AST-based signatures, as well as controlled dynamic analysis to identify malicious code and data flows.
* Following the flow of data from card skimmers, we also identify endpoints used by the attacker for data extraction - including email IDs, telegram chat IDs and FTP endpoints, with an **accuracy of 93%** and a **2% false positive rate**, with a 100% accuracy for Telegram-based exfiltration.
* PHP malware is often distributed across multiple files, defeating simple automated static analysis. Therefore, a novel algorithm was used to identify files dependent on each other and the complete picture of the malware was created.
* We neutralized **1041 varieties** of international financial and identity theft campaigns on compromised servers.


### [Kratos](https://github.com/TheComputeGuy/kratos)
* Kratos is a web malware detection pipeline tailored for Content Management System (CMS) plugin files.
* Kratos was developed as a part of a research study on the prevalence and types of malware present in nulled CMS plugin files downloaded from the web, torrents and Telegram-based marketplaces.
* It uses various code (Regex) and behavioural (Abstract Syntax Tree-based) signatures to detect and classify PHP malware.
* The tool identified **1851 malicious plugins** out of a sample of ~2400 plugins from the aforementioned sources.

### Webc2-Greencat - [Static](https://github.com/TheComputeGuy/static-analysis-plugin), [Dynamic](https://github.com/TheComputeGuy/dynamic-analysis-pin-tools), [Control Flow](https://github.com/TheComputeGuy/control-dependence)
* Performed a complete static and dynamic analysis of webc2-greencat, a malware attributed to APT1, using IDA Pro and Intel Pin.
* Used IDA APIs to build control-flow and data dependence graphs to analyze the behaviour of the malware, and used Intel Pin to instrument the binary and capture execution traces in various paths.

### [PDF OCR Tool](https://github.com/TheComputeGuy/PDFOCRtool)
* Built a Python-based tool to add a multi-lingual Optical Character Recognition layer to a given PDF file
* This was built to enable a low-vision friend to use screen readers to read documents lacking a text layer

### [Request X-Ray](https://github.com/TheComputeGuy/request-xray)
* Built a webservice intended to intercept and act as a man-in-the-middle, to read-through HTTP requests made to various services from an app
* The tool forwards requests and response appropriately, while storing request information like headers, body and query params to help application teams triage incidents with their APIs
