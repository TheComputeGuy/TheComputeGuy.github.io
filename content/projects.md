---
title: "Projects"
---

Some projects that I enjoyed building:

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

### [Diabetic Retinopathy (DR) Severity Evaluation](https://drive.google.com/file/d/1vsfcpJQxfufbsKqeh0HtFjrHPd5B__d2/view?usp=sharing)
* Used computer vision techniques to build a deep learning algorithm to evaluate DR severity from eye images
* Used InceptionV3 architecture and weighted cross-entropy, among others to gain a weighted F1 score of 0.537
