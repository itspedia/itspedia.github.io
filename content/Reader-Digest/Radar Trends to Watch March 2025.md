---
title: "Radar Trends to Watch: March 2025"
author: Mike Loukides
date: 2025-03-05T16:01:23+08:00
lastmod: 2025-03-05T16:01:23+08:00
draft: false
tags: ["digest", "trends"]
categories: ["digest", "index"]

menu:
  main:
    parent: "Knowledge"
    weight: 1
---


Anthropic’s announcement of Claude 3.7 Sonnet notwithstanding, the breakneck pace of major AI announcements seemed to slow down through February. That gave us some time to look at some other topics. Two important posts about programming appeared: Salvatore Sanfilippo’s “We Are Destroying Software” and Rob Pike’s slide deck “On Bloat.” They’re unsurprisingly similar. Neither mentions AI; both address the question of why our hardware is getting faster and faster but our applications aren’t. We’ve also noted the return of Pebble, the first smart watch, and an AI-driven table lamp from Apple Research that looks like it came from Pixar’s logo. Fun, perhaps, but don’t look for it in Apple Stores.

Artificial Intelligence
-----------------------

*   Anthropic has released [Claude 3.7 Sonnet,](https://www.anthropic.com/news/claude-3-7-sonnet) the company’s first reasoning model. It’s a “hybrid model”; you can tell it whether you want to enable its reasoning capability. You can also control its thinking “budget” by limiting the number of tokens it generates for the reasoning process.
*   The [Computer Agent Arena](https://arena.xlang.ai/) is a platform for crowdsourced agent testing. It allows anyone to run an agent using two different AI models, observe what the agent is doing, and rate the results. Results are summarized on a leaderboard; right now, Claude 3.5 Sonnet is at the top.
*   Google is developing a “[co-scientist](https://arstechnica.com/google/2025/02/googles-new-ai-generates-hypotheses-for-researchers/)” that suggests hypotheses for scientists to investigate. The hypotheses are based on the scientist’s goals, ideas, and past research. The company’s looking for researchers to help with testing.
*   GitHub has [upgraded](https://github.blog/news-insights/product-news/github-copilot-the-agent-awakens/) agent mode for Copilot. It will now iterate on buggy code until it delivers correct results, and can add new subtasks to the original if they’re needed to accomplish the user’s goal.
*   [Open-R1](https://huggingface.co/blog/open-r1) is a new [project](https://github.com/huggingface/open-r1) that intends to create a fully open reproduction of DeepSeek R1. In addition to code and weights, this project will release all tools and synthetic data used to train the model.
*   [Moshi](https://kyutai.org/Moshi.pdf) is a new conversational (speech-to-speech) language model that is constantly listening and can handle interjections like “uh huh” without getting confused.
*   [Codename Goose](https://github.com/block/goose) is a new open source [framework](https://block.github.io/goose/) for [developing agentic AI](https://block.xyz/inside/block-open-source-introduces-codename-goose) applications. It uses Anthropic’s Model Context Protocol for communicating with systems that have data, and can discover new data sources on the fly.
*   The University of Surrey will be building a [language model for sign language](https://www.bbc.com/news/articles/c4g9rd4g8w2o). One focus will be translating between spoken language and sign language. The goal is to ensure that the deaf community isn’t left behind by the explosion of AI tools.
*   [Galileo](https://www.galileo.ai/) is an agentic toolset for detecting when an AI model is [hallucinating](https://thenewstack.io/ai-agentic-evaluation-tools-help-devs-fight-hallucinations/). It’s particularly important for agentic systems, where an error by one agent leads to misbehavior by others downstream.
*   A group of researchers [released](https://arxiv.org/abs/2501.19393) [s1](https://github.com/simplescaling/s1), a 32B reasoning model with near state-of-the-art performance. [s1 cost only $6 to train](https://timkellogg.me/blog/2025/02/03/s1). A very small set of training data (only [1,000 reasoning samples](https://huggingface.co/datasets/simplescaling/s1K)) proved sufficient when the model was forced to take extra time for reasoning.
*   Some researchers published [_How to Scale Your Model_](https://jax-ml.github.io/scaling-book/), a book on how to scale large language models. The book is apparently internal documentation from Google DeepMind.
*   OpenAI has [released](https://openai.com/index/openai-o3-mini/) o3-mini, a small and cost-efficient language model based on its (still unreleased) o3 reasoning model.
*   Anthropic has [deployed](https://arstechnica.com/ai/2025/02/anthropic-dares-you-to-jailbreak-its-new-ai-model/) its [Constitutional Classifier](https://www.anthropic.com/research/constitutional-classifiers) for adversarial testing by the public. The classifier is a system that protects Claude models from jailbreaks and attempts to get Claude to answer questions that aren’t allowed. Early results look very good.
*   The [lesson to learn from DeepSeek R1](https://www.technologyreview.com/2025/01/31/1110740/how-deepseek-ripped-up-the-ai-playbook-and-why-everyones-going-to-follow-it/) is that, given a good foundation model, it’s less difficult than many thought to develop a reasoning model. In the coming months, expect many open alternatives.
*   OpenAI has introduced [DeepResearch](https://openai.com/index/introducing-deep-research/), an application based on its o3 model that claims the ability to synthesize large amounts of information and perform multistep research tasks.
*   Sam Altman has acknowledged that OpenAI is on the “[wrong side of history](https://www.reddit.com/r/OpenAI/comments/1ieonxv/comment/maa0dcx/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)” as far as open source AI but also said that addressing the issues was not a high priority.
*   Alibaba has [launched Qwen2.5-Max](https://techxplore.com/news/2025-01-alibaba-advanced-ai-rival-gpt.html), another large language model with performance on the same level as GPT-4 and Claude 3.5 Sonnet. It can be accessed through [Qwen Chat](https://chat.qwenlm.ai/) or Alibaba’s cloud.
*   [Transformer Lab](https://github.com/transformerlab/transformerlab-app?tab=readme-ov-file) is a tool for experimenting with, training, fine-tuning, and programming LLM models locally. It’s still installing, but it looks like Ollama on steroids.
*   [smolGPT](https://github.com/Om-Alve/smolGPT) is “a minimal PyTorch implementation for training your own small LLM from scratch.”
*   Yes, Microsoft is complaining that DeepSeek used OpenAI to generate synthetic training data. Those objections didn’t stop it from making [DeepSeek available on Azure](https://azure.microsoft.com/en-us/blog/deepseek-r1-is-now-available-on-azure-ai-foundry-and-github/).
*   Two composers [collaborated with Google’s Gemini](https://blog.google/products/gemini/google-arts-culture-gemini-orchestra/) to create _The Twin Paradox_, a work for a classical symphony orchestra.
*   Alibaba has [released](https://qwenlm.github.io/blog/qwen2.5-1m/) two “checkpoints” to its models, [Qwen2.5-7B-Instruct-1M](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct-1M) and [Qwen2.5-14B-Instruct-1M](https://huggingface.co/Qwen/Qwen2.5-14B-Instruct-1M). These models have large 1M-token context windows. Alibaba has also open-sourced its inference framework, which the company claims is three to seven times faster.
*   [TinyZero](https://github.com/Jiayi-Pan/TinyZero) reproduces DeepSeek’s R1 Zero, a reasoning model with 3B parameters. Training TinyZero cost under US$30. You could download TinyZero, but you could also make your own for less than the cost of an evening out. Do we need expensive models?

##### More from the Learning Platform

*   [_Building Applications with AI Agents_](https://learning.oreilly.com/library/view/building-applications-with/9781098176495/) (early release book)
*   [_Modern Automated AI Agents: Building Agentic AI to Perform Complex Tasks_](https://learning.oreilly.com/course/modern-automated-ai/9780135414965/) (video)

Programming
-----------

*   Tanagram is [promising](https://tanagramdev.com/) a toolset for helping developers understand and work with complex codebases. So far, there are only demos, but it sounds interesting.
*   Harper Reed [describes](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) his workflow for programming with AI. Developing a workflow is essential to using AI effectively, and Harper has given the most thorough description we’ve seen.
*   Like Linux, [Ruby on Rails can run in the browser](https://web.dev/blog/ruby-on-rails-on-webassembly). This hack uses WebAssembly.
*   [Linux booting](https://linux.doompdf.dev/linux.pdf) [inside a PDF](https://www.reddit.com/r/linux/comments/1ifwpl0/i_got_linux_running_in_a_pdf_file_via_a_riscv/) [in Chrome](https://www.zdnet.com/article/linux-running-in-a-pdf-this-hack-is-as-bizarre-as-it-is-brilliant/). PDF implementations support JavaScript; C can be compiled into a subset of JavaScript (asm.js), which means that a RISC-V emulator can be compiled to JavaScript and run in a PDF in the browser, which then runs Linux. An amazing hack.
*   [OCR4all](https://www.ocr4all.org/) provides free and open source optical character recognition software. Should you need it.
*   Why does software run no faster than it did 20 or 30 years ago, despite much faster computers? Rob Pike has some thoughts on [controlling bloat](https://docs.google.com/presentation/d/e/2PACX-1vSmIbSwh1_DXKEMU5YKgYpt5_b4yfOfpfEOKS5_cvtLdiHsX6zt-gNeisamRuCtDtCb2SbTafTI8V47/pub?start=false&loop=false&delayms=3000#slide=id.p).
*   As the name implies, [Architectural Decision Records](https://adr.github.io/) ([ADRs](https://github.com/adr)) capture a decision about software architecture and the reason for the decision. All too frequently, this information isn’t captured. It is likely to become more important in the era of AI-assisted software development.
*   [Jank](https://thenewstack.io/from-c-to-clojure-new-language-promises-best-of-both/) is a new general purpose programming language. It’s a dialect of Clojure that incorporates ideas from many other languages, including C++ and Rust, and is built on top of the LLVM.
*   Here’s a set of [patterns for building real-time](https://zknill.io/posts/patterns-for-building-realtime/) features into applications.
*   Salvatore “antirez” Sanfilippo’s post, “[We Are Destroying Software](https://antirez.com/news/145),” is a must-read. (It says nothing about AI.) It starts “We are destroying software by no longer taking complexity into account.”
*   [Script](https://github.com/bitfield/script) is a Go library that makes it possible to do shell-like programming in Go. Its biggest contribution is the ability to create pipes; it also has Go functions that are similar to grep, find, head, tail, and other common shell commands.

##### More from the Learning Platform

*   [_Software Development Hour with Sam Newman: Using AI-Assisted Tools to Learn Programming Skills with Simon Willison_](https://learning.oreilly.com/videos/software-development-hour/0636920889595/) (video)
*   [_Fundamentals of Software Architecture_, 2nd Edition](https://learning.oreilly.com/library/view/fundamentals-of-software/9781098175504/) (book)

Security
--------

*   Threat actors aligned with Russia are [targeting Signal](https://cloud.google.com/blog/topics/threat-intelligence/russia-targeting-signal-messenger/), the secure messaging application, with phishing attacks that link users’ accounts to hostile devices. One group sends QR codes that [look legitimate](https://www.darkreading.com/mobile-security/russian-groups-target-signal-messenger-in-spy-campaign) but link to a device under their control; another impersonates an application used by Ukraine’s military. The best protection is to [update](https://support.signal.org/hc/en-us/articles/360007059212-How-do-I-ensure-Signal-is-up-to-date) to the latest version of Signal.
*   [Two new vulnerabilities](https://www.bleepingcomputer.com/news/security/new-openssh-flaws-expose-ssh-servers-to-mitm-and-dos-attacks/) in OpenSSH have been found. One exposes OpenSSH servers to man-in-the-middle attacks; the other can lead to denial-of-service attacks. An update has been released; install it.
*   [DarkMind](https://techxplore.com/news/2025-02-darkmind-backdoor-leverages-capabilities-llms.html) is a new attack against reasoning language models. It’s possible to build custom applications (like those in the GPT Store) with “hidden triggers” that modify the reasoning process.
*   A new kind of supply chain attack involves obtaining [abandoned AWS S3](https://www.schneier.com/blog/archives/2025/02/delivering-malware-through-abandoned-amazon-s3-buckets.html) buckets that still hold libraries that are frequently downloaded. The new owner can insert malware into the libraries; the original owner, who abandoned the bucket, can’t patch the corrupted libraries.
*   [Security is blocking AI adoption](https://thenewstack.io/security-is-blocking-ai-adoption-is-byoc-the-answer/), particularly in heavily regulated industries. That’s understandable; many of the questions we ask of secure systems can’t be adequately answered for AI.
*   Microsoft’s AI Red Team has published [_Lessons from Red Teaming 100 Generative AI Products_](https://airedteamwhitepapers.blob.core.windows.net/lessonswhitepaper/MS_AIRT_Lessons_eBook.pdf). It’s essential reading for anyone interested in building a secure AI system.
*   AI is being used to [submit fake feature requests](https://thenewstack.io/ai-is-spamming-open-source-repos-with-fake-issues/) and bug reports on open source projects. Many of these may be inadvertent, but regardless of cause, it’s generating problems for software maintainers.
*   Linux has a number of [tools](https://thenewstack.io/linux-security-scan-your-servers-for-rootkits-with-ease/) for detecting rootkits and other malware. [Chkrootkit](https://www.chkrootkit.org/) and [LMD](https://github.com/rfxn/linux-malware-detect) (Linux Malware Detect) are worth your attention.
*   [Time Bandit](https://www.bleepingcomputer.com/news/security/time-bandit-chatgpt-jailbreak-bypasses-safeguards-on-sensitive-topics/) is a new jailbreak for the GPT models. The attack causes the model to lose track of past, present, and future. Essentially, you ask GPT how someone in the past would do something that can only be done in the present. It’s unclear whether this attack works on other models.
*   When the price of bitcoin goes up, so does the frequency of [cryptojacking](https://www.bleepingcomputer.com/news/security/whats-yours-is-mine-is-your-business-ready-for-cryptojacking-attacks/): hijacking computers to form crypto-mining botnets. It’s claimed that for every dollar of crypto that’s mined, the victim incurs $53 in cloud costs.
*   A [new backdoor to VPNs](https://arstechnica.com/security/2025/01/backdoor-infecting-vpns-used-magic-packets-for-stealth-and-security/) has been discovered in the wild, giving attackers access to corporate networks. These backdoors stay dormant until they are triggered by a specially constructed “magic packet,” making them difficult to detect.

##### More from the Learning Platform

*   [_Beyond the Algorithm: AI, Security, Privacy, and Ethics_](https://learning.oreilly.com/library/view/beyond-the-algorithm/9780138268442/) (book)
*   [_The Developer’s Playbook for Large Language Model Security_](https://learning.oreilly.com/library/view/the-developers-playbook/9781098162191/) (book)

Web
---

*   As more people ask AI for product recommendations, marketers will need to optimize product perception by language models. [Does LLMO replace SEO](https://www.technologyreview.com/2025/02/19/1112076/your-most-important-customer-may-be-ai/)? Optimizing for an LLM may be the next generation of SEO.
*   This [article](https://www.dailydot.com/debug/how-to-turn-off-gmail-ai/) tells you how to opt out of Gemini features in Gmail and other Google Workspace applications. It’s possible to disable Gemini selectively. Unfortunately, it requires you to have access to the administrator’s console.
*   JavaScript’s [Temporal](https://developer.mozilla.org/en-US/blog/javascript-temporal-is-coming/) object is starting to appear in browsers! Temporal is a replacement for the inadequate Date object. It allows programmers to work effectively with dates and times.
*   [Marginalia](https://marginalia-search.com/) is an open source search engine that prioritizes noncommercial resorts.

##### More from the Learning Platform

*   [_The Art of SEO_, 4th Edition](https://learning.oreilly.com/library/view/the-art-of/9781098102609/) (book)
*   [_Beyond the Algorithm: AI, Security, Privacy, and Ethics_](https://learning.oreilly.com/library/view/beyond-the-algorithm/9780138268442/) (book)

Quantum Computing
-----------------

*   Microsoft has created a [topological qubits](https://scottaaronson.blog/?p=8669) on a new [quantum chip](https://www.technologyreview.com/2025/02/19/1112072/a-new-microsoft-chip-could-lead-to-more-stable-quantum-computers/). While its chip currently has only 8 qubits, Microsoft claims it can scale to millions of qubits. Putting this many qubits on a chip would go a long way to solving the problem of moving quantum data between chips.
*   Canadian startup Xanadu has built a [quantum computer using photonics](https://www.technologyreview.com/2025/01/30/1110672/this-quantum-computer-built-on-server-racks-paves-the-way-to-bigger-machines/). It currently has 12 qubits, but the company believes it can scale to larger systems.

##### More from the Learning Platform

*   [_Quantum Computing Fundamentals_](https://learning.oreilly.com/course/quantum-computing-fundamentals/9780137872558/) (video)

Robotics
--------

*   [Robotic models of extinct animals](https://www.technologyreview.com/2025/02/12/1111409/paleo-robots-extinct-prehistoric-animals/) are helping paleontologists discover how those animals might have lived: how they walked, swam, and flew in their environments.

##### More from the Learning Platform

*   [_Intelligent Robots and Cobots_](https://learning.oreilly.com/library/view/intelligent-robots-and/9781394198177/) (book)

Gadgets
-------

*   [Pebble returns](https://repebble.com/)? Remember the crowdfunded Pebble smartwatch that was available long before Apple’s Watch? It’s coming back—maybe. And it will be hackable.
*   Something we all need: An engineering team at Apple developed an [AI-driven table lamp](https://techxplore.com/news/2025-02-apple-pixar-table-lamp-ai.html). Not available in an Apple Store near you.