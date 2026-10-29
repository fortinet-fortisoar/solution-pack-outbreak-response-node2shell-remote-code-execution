# Release Information 

- **Version**: 1.0.0 
- **Certified**: No 
- **Publisher**: Fortinet 
- **Compatible Version**: FortiSOAR 7.4.0 and later 

# Overview 

CVE-2026-111497 is an out-of-bounds write vulnerability in Google's Brotli decoder, a component used to decompress data encoded with the Brotli compression algorithm. Brotli is widely used in web communications and is incorporated into software libraries, runtimes, and HTTP clients, including Node.js. 

 The **Outbreak Response - Node2Shell Remote Code Execution** solution pack works with the Threat Hunt rules in [Outbreak Response Framework](https://github.com/fortinet-fortisoar/solution-pack-outbreak-response-framework/blob/release/2.3.0/docs/background-information.md#threat-hunt-rules) solution pack to conduct hunts that identify and help investigate potential Indicators of Compromise (IOCs) associated with this vulnerability within operational environments of *FortiSIEM*, *FortiAnalyzer*.

 The [FortiGuard Outbreak Page](https://www.fortiguard.com/outbreak-alert/node2shell) contains information about the outbreak alert **Outbreak Response - Node2Shell Remote Code Execution**. 

## Background: 

Brotli is an open-source project developed and maintained by Google for lossless data compression. It shrinks files so they can be transmitted faster without affecting the original data.

The vulnerability occurs when the decoder processes a specially crafted Brotli-compressed stream containing an invalid block switch. Instead of rejecting the malformed input, the streaming decoder may incorrectly request additional input and continue appending data beyond an internal buffer's boundary. This can corrupt memory and potentially cause a denial of service, disclose sensitive process memory, or enable arbitrary code execution.

Exploitation requires a vulnerable application to decompress attacker-controlled Brotli data. Depending on the application, this could occur while processing incoming compressed requests or decompressing responses from an untrusted remote server. The vulnerability is not limited to Node.js: affected Brotli libraries and packages used by other software ecosystems have also been reported. 

## Announced: 

Upgrade Node.js to fixed versions 22.23.4, 24.22.1, or 26.12.1, or later security releases and update Brotli libraries and dependencies. Brotli versions 1.0.3 through 1.2.0 have been identified as affected. The published advisory identifies fixed releases including 1.0.10, 1.1.1, and 1.2.1. Confirm the appropriate fixed version for each package and vendor distribution. 

## Latest Developments: 

October 27, 2026: CISA has added CVE-2026-111497 to its Known Exploited Vulnerabilities (KEV) Catalog, based on evidence of active exploitation.CVE-2026-111497 Google Brotli Unchecked Return Value Vulnerability
https://www.cisa.gov/news-events/alerts/2026/10/27/cisa-adds-two-known-exploited-vulnerabilities-catalog

October 22, 2026: The GitHub Advisory Database published details identifying affected Brotli versions 1.0.3 through 1.2.0. Red Hat also published its advisory, describing the potential for memory disclosure, denial of service, and arbitrary code execution.
https://github.com/advisories/GHSA-9v8h-qqgm-4m35

October 21, 2026: The Node.js project announced security updates for its 22.x, 24.x, and 26.x release lines, documenting the Brotli decoder flaw and its potential impact, including remote code execution
https://nodejs.org/en/blog/vulnerability/october-2026-security-releases 

# Next Steps
 | [Installation](./docs/setup.md#installation) | [Configuration](./docs/setup.md#configuration) | [Usage](./docs/usage.md) | [Contents](./docs/contents.md) | 
 |--------------------------------------------|----------------------------------------------|------------------------|------------------------------|
