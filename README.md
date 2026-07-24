## unlinkedbyte

## 🧑‍💻 About Me

I have always wanted to understand the why behind everything, and my path in cybersecurity is no exception. 

I started in this field by exploring hacking web, but deploying attacks with tools I didn't fully understand simply didn't fit with me. After taking a break to step back and think about which direction I should choose, I decided to clear out the external noise, stop comparing myself to others, and focus entirely on what I truly enjoy: the low level, Linux internals, C programming, conducting my own research, and understanding how software interacts with hardware. 

Currently, I am building utilities to force myself to sharpen my programming skills (C, in this case) and understand how operating systems work under the hood, building the solid foundations that align with my way of thinking.


### 🔬 Research Blog & Labs
I document my low-level learning journey, system analysis, and lab experiments in a dedicated repository.

* **[Blog](https://github.com/unlinkedbyte/unlinkedbyte.github.io/tree/main)** 

* **Latest post:** [I tried to leak heap padding. Glibc had other plans](https://github.com/unlinkedbyte/unlinkedbyte.github.io/blob/main/_posts/2026-07-24-I-tried-to-leak-heap-padding-glibc-had-other-plans.md)


### First Project
* **[Fstab Protection Tool](https://github.com/unlinkedbyte/guardian-fstab-project)** - A utility written in C designed to safeguard the `fstab` file configuration against potential system boot failures (caused by human error, unexpected update behaviors...)

### Current Project
* **[flcarve (Forensic Log Recovery)](https://github.com/unlinkedbyte/flcarve_project)** - A low-level DFIR (Digital Forensics and Incident Response) utility designed to recover deleted data during post-exploitation analysis or incident investigations. This tool was conceived to solve a critical real-world scenario: when a genuine attack is mistaken for a false positive, causing automated `logrotate` policies to unlink and discard critical compressed logs (`.gz`). Since standard file system structures lose track of data once unlinked, this utility performs raw file carving directly on a disk image (`dd`), bypassing traditional file system metadata. By scanning raw storage blocks for gzip magic signatures (`0x1F 0x8B`), it reconstructs and extracts deleted evidence, demonstrating how data persists on disk after deletion. *(Planned purely as an educational exercise to guide my low-level learning journey).*

### Upcoming Projects

* **Slack space scanner**


I recently researched how Linux blocks work for the flcarve tool, and a few days ago I opened a blog to upload a post and break the ice. Thinking about new research to do for the blog, I was torn between investigating the possible vulnerabilities that exist or existed in chunk headers, and the other option, about slack space, which I learned about precisely when reading about blocks. Simply, for the post, I wanted to create a tool that optimized the analysis of inode metadata (listing all the used ones, calculating the space they occupy, how many blocks, where they point...) to subsequently analyze the slack space of the last allocated block. So, eventually, this idea came up to analyze obfuscated malware. The tool would do what I mentioned before, and then analyze the slack space of all the last collected blocks using sliding entropy (about 64 bytes, for example), to later create a temporary directory (e.g., /temp/analysis_slack/) to save all the reports that match. Then, through a call to a local AI via an API, analyze all the available reports after converting them to hexadecimal (having passed a prompt that we can modify in a script created to call the API). The analysis using sliding entropy is designed to theoretically identify malware that is also fragmented. The ideal setup would be for the AI (alongside the human eye) to warn us about which ones are suspicious, which ones are assembly instructions that shouldn't be there... etc.


<details>
<summary><b>Click here to check another idea for a future project</b></summary>
<br>

* **UEFI Boot Auditor** - A low-level firmware and partition integrity utility conceptualized to inspect raw disk images, parse GPT layouts, and analyze bootloader binaries against potential bootkit persistence.


  While studying bootloaders in 'How Linux Works', I realized they must ingest instructions from specific configuration paths to function. This triggered a question: if they process external parameters before the OS is even loaded, how vulnerable are they? And what is the real-world danger of a compromised bootloader? Although my initial instinct was to build an offensive PoC, I chose a defensive path. This tool will allow me to understand better how modern bootloaders initialize, manipulate storage tables, and hand over control before the Linux Kernel is safely loaded into RAM (Like with my other projects, I still have a lot of research left to do. This is a purely educational project).
</details>

### Currently Learning
* Linux Internals & Kernel Concepts
* C Programming
* Ethical Hacking & Cybersecurity Foundations

### Programming Languages & Scripting
* **C** (Core language)
* **Bash** (Basic scripting for automation)
* **HTML & Javascript** (Read-only proficiency focused on code auditing and web vulnerability analysis (e.g., client-side logic, XSS)).
* **SQL** (Fundamental understanding for database structure and injection vector analysis)

### Reading List 

#### Currently Reading
* 📖 *[The C Programming Language](https://github.com/unlinkedbyte/the-c-programming-language-solutions)* — Brian W. Kernighan & Dennis M. Ritchie
* 📖 *How Linux Works* — Brian Ward
* 📖 *Hacking: The Art Of Exploitation* - Jon Erickson


*I also like to read Kris Kaspersky's books on my free time (code optimization, hacker disassembly) to absorb historical context and study how a brilliant researcher thought*

#### Essential Backlog
* 🎯 *Computer Systems: A Programmer's Perspective* (CS:APP) — Randal E. Bryant & David R. O'Hallaron
* 🎯 *The Linux Programming Interface* — Michael Kerrisk
* 🎯 *TCP/IP Illustrated, Volume 1: The Protocols* — Kevin R. Fall & W. Richard Stevens


### Pioneers & Researchers I Like
* **Kris Kaspersky** - *special mention*. A true legend of reverse engineering and the low level scene
* **Dennis Ritchie, Brian Kernighan & Ken Thompson**
* **Richard Stallman & Linus Torvalds**
* **PortSwigger Security Research Team**
* **Jon Erickson**
* **Jann Horn**
* **Gynvael Coldwind**
* **0vercl0k (Axel Souchet)**
* **j00ru (Mateusz Jurczyk)**
* **Rana Khalil**

