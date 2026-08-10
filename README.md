## unlinkedbyte

## 🧑‍💻 About Me

I have always wanted to understand the why behind everything, and my path in cybersecurity is no exception. 

I started out in web security, but deploying attacks with tools I didn't fully understand didn't fit the way I think. I stepped back and refocused on what I actually enjoy: the low level, Linux internals, C, and understanding how software behaves underneath the abstractions.

I'm still building those foundations. Most of my time so far has gone into writing small utilities in C and working through K&R, learning by doing rather than by tutorial. More recently I started reverse engineering in parallel: binary analysis, crackmes, and a first look at real router firmware, partly because reading disassembly next to C accelerates both, and partly because it's what pulls me.

I document the process as I go, including the parts I get wrong. Those stay up, corrected in later writeups.

### 🔬 Research Blog & Labs
I document my low-level learning journey, system analysis, and lab experiments in a dedicated repository.

* **[Blog](https://github.com/unlinkedbyte/unlinkedbyte.github.io/tree/main)** 


* **First post:** [The Old Risk Of Residual Data In Physical RAM Cells](https://github.com/unlinkedbyte/unlinkedbyte.github.io/blob/main/_posts/2026-07-13-the-old-risk-of-residual-data-in-physical-ram-cells.md)

* **Second post:** [I Tried to Leak Heap Padding. glibc Had Other Plans](https://github.com/unlinkedbyte/unlinkedbyte.github.io/blob/main/_posts/2026-07-24-I-tried-to-leak-heap-padding-glibc-had-other-plans.md)

* **Third post:** [Git credential-cache and suspend: an unexpected timeout behavior](https://github.com/unlinkedbyte/unlinkedbyte.github.io/blob/main/_posts/2026-07-25-Git-credential-cache-and-suspend-an-unexpected-timeout-behaviour.md)

### First Project
* **[Fstab Protection Tool](https://github.com/unlinkedbyte/guardian-fstab-project)** - A utility written in C designed to safeguard the `fstab` file configuration against potential system boot failures (caused by human error, unexpected update behaviors...)

### Current Projects
* **[flcarve (Forensic Log Recovery)](https://github.com/unlinkedbyte/flcarve_project)** - A low-level DFIR (Digital Forensics and Incident Response) utility designed to recover deleted data during post-exploitation analysis or incident investigations. This tool was conceived to solve a critical real-world scenario: when a genuine attack is mistaken for a false positive, causing automated `logrotate` policies to unlink and discard critical compressed logs (`.gz`). Since standard file system structures lose track of data once unlinked, this utility performs raw file carving directly on a disk image (`dd`), bypassing traditional file system metadata. By scanning raw storage blocks for gzip magic signatures (`0x1F 0x8B`), it reconstructs and extracts deleted evidence, demonstrating how data persists on disk after deletion. *(Planned purely as an educational exercise to guide my low-level learning journey).*

* **[Reversing](https://github.com/unlinkedbyte/Reversing)** - Documenting my reverse engineering learning journey: binary analysis, firmware analysis and crackmes writeups. If you're just starting out, could be a good starting point.

### Upcoming Projects

* **Slack space scanner**

Conceptualized to scan the slack space of the last allocated block with sliding entropy, looking for fragmented malware.

<details>
<summary><b>How I got to this idea</b></summary>
<br>
I recently researched how Linux blocks work for the flcarve tool, and a few days ago I opened a blog to upload a post and break the ice. Thinking about new research to do for the blog, I was torn between investigating the possible vulnerabilities that exist or existed in chunk headers, and the other option, about slack space, which I learned about precisely when reading about blocks. Simply, for the post, I wanted to create a tool that optimized the analysis of inode metadata (listing all the used ones, calculating the space they occupy, how many blocks, where they point...) to subsequently analyze the slack space of the last allocated block. So, eventually, this idea came up to analyze obfuscated malware. The tool would do what I mentioned before, and then analyze the slack space of all the last collected blocks using sliding entropy (about 64 bytes, for example), to later create a temporary directory (e.g., /tmp/analysis_slack/) to save all the reports that match. Then, through a call to a local AI via an API, analyze all the available reports after converting them to hexadecimal (having passed a prompt that we can modify in a script created to call the API). The analysis using sliding entropy is designed to theoretically identify malware that is also fragmented. The ideal setup would be for the AI (alongside the human eye) to warn us about which ones are suspicious, which ones are assembly instructions that shouldn't be there... etc.
</details>

<details>
<summary><b>Click here to check another idea for a future project</b></summary>
<br>

* **UEFI Boot Auditor** - A low-level firmware and partition integrity utility conceptualized to inspect raw disk images, parse GPT layouts, and analyze bootloader binaries against potential bootkit persistence.


  While studying bootloaders in 'How Linux Works', I realized they must ingest instructions from specific configuration paths to function. This triggered a question: if they process external parameters before the OS is even loaded, how vulnerable are they? And what is the real-world danger of a compromised bootloader? Although my initial instinct was to build an offensive PoC, I chose a defensive path. This tool will allow me to understand better how modern bootloaders initialize, manipulate storage tables, and hand over control before the Linux Kernel is safely loaded into RAM (Like with my other projects, I still have a lot of research left to do. This is a purely educational project).
</details>

### Currently Learning
* Reverse engineering
* Linux Internals & Kernel Concepts
* C Programming

### Tools & Languages
* **C** (Core language)
* **Assembly** - x86, x86-64
* **Debugger** - GDB
* **Disassembler** - Ghidra

### Reading List 

#### Currently Reading
* 📖 *[The C Programming Language](https://github.com/unlinkedbyte/the-c-programming-language-solutions)* — Brian W. Kernighan & Dennis M. Ritchie
* 📖 *Computer Systems: A Programmer's Perspective (CS:APP)* — Randal E. Bryant & David R. O'Hallaron
* 📖 *Practical Binary Analysis* — Dennis Andriesse (referencia / en curso)

#### Essential Backlog
* 🎯 *Computer Systems: A Programmer's Perspective* (CS:APP) — Randal E. Bryant & David R. O'Hallaron
* 🎯 *The Linux Programming Interface* — Michael Kerrisk
* 🎯 *TCP/IP Illustrated, Volume 1: The Protocols* — Kevin R. Fall & W. Richard Stevens


### Pioneers & Researchers I Like
* **Kris Kaspersky** - *special mention*. A true legend of reverse engineering and the low level scene
* **Dennis Ritchie, Brian Kernighan & Ken Thompson**
* **Richard Stallman & Linus Torvalds**
* **PortSwigger Security Research Team**
* **Jann Horn**
* **Gynvael Coldwind**
* **0vercl0k (Axel Souchet)**
* **j00ru (Mateusz Jurczyk)**
* **Rana Khalil**

