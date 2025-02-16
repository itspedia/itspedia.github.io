---
title: "Radar Trends to Watch: February 2025"
author: Mike Loukides
date: 2025-02-03T16:01:23+08:00
lastmod: 2025-02-04T16:01:23+08:00
draft: false
tags: ["digest", "trends"]
categories: ["digest", "index"]

menu:
  main:
    parent: "Knowledge"
    weight: 1
---

##### Developments in Web, Virtual Reality, Robotics, and More


Last month, DeepSeek released its R1 reasoning model (now apparently named DeepThink), with capabilities similar to OpenAI o1. What’s important about DeepSeek isn’t its benchmark results; there are a number of models on the same level as o1. What’s important is that it appears to have been trained with one-tenth the resources of comparable models. Throwing more hardware at a problem is rarely the best way to get good results.

## Artificial Intelligence

- Anthropic has added a [Citations API](https://www.anthropic.com/news/introducing-citations-api) to Claude. Citations builds RAG directly into the model. It allows users to add documents to the context. When generating an answer, Claude includes citations that show exactly which parts of the documents were used in developing the response.

- OpenAI has released a research preview of [Operator](https://openai.com/index/introducing-operator/), its competitor to Anthropic’s Computer Use. Like Computer Use, Operator is a general-purpose agent: It can use a browser to navigate the web, bring back information, and generate new actions to accomplish the user’s request.

- Berkeley has [released](https://novasky-ai.github.io/posts/sky-t1/) Sky-T1-32B-Preview, a small reasoning model that cost under $450 to train. It’s based on Alibaba’s Qwen2.5-32B-Instruct. Sky’s performance is similar to OpenAI o1-preview, and it’s fully open: Training data, weights, code, and infrastructure are all open source.

- DeepSeek has released its [R1](https://github.com/deepseek-ai/DeepSeek-R1) reasoning model, on which its V3 model was based. R1 has performance equivalent or superior to OpenAI o1 and is significantly less expensive. DeepSeek has also released several [other models derived from R1](https://simonwillison.net/2025/Jan/20/deepseek-r1/), including a number of smaller models based on Llama and Alibaba’s Qwen. All of these models have open code and weights.

- The [key to using OpenAI o1](https://www.latent.space/p/o1-skill-issue) effectively is context, not clever prompting. “Don’t write prompts, write briefs”; give it all the information it needs to solve a problem.

- OpenAI has announced a new technique for training its new reasoning models to be safe. [Deliberative alignment](https://openai.com/index/deliberative-alignment/) trains the models to reason on the safety policies themselves rather than requiring humans to grade model responses.

- Meta has introduced [SeamlessM4T](https://about.fb.com/news/2023/08/seamlessm4t-ai-translation-model/), a multimodal (speech and text) model designed for translation. It can translate speech-to-speech and text-to-speech for nearly 100 input languages and 35 output languages.

- Anthropic has received [ISO 42001 certification](https://www.anthropic.com/news/anthropic-achieves-iso-42001-certification-for-responsible-ai). This certification covers responsible AI and addresses AI design and deployment processes, transparency, testing and monitoring, and oversight.

- Google has released a paper on a new LLM architecture called [Titans](https://arxiv.org/abs/2501.00663v1) (a.k.a. Transformers 2.0). The primary advantage of Titans is its ability to scale to very large context windows. In effect, it adds persistent long-term memory to the Transformers model.

- ChatGPT can now [schedule recurring tasks](https://techcrunch.com/2025/01/14/chatgpt-now-lets-you-schedule-reminders-and-recurring-tasks/), making it more like a personal assistant. Tasks can include generating reminders, scheduling, summarizing news, and other chores.

- AI systems may “think” using [a variant of Occam’s razor](https://techxplore.com/news/2025-01-key-ai-power-inbuilt-special.html), which prioritizes simpler solutions to problems.

- Mistral has released [Codestral 25.01](https://mistral.ai/news/codestral-2501/), a language model that’s optimized for code generation. It claims proficiency in over 80 programming languages. This new release is faster, supports a larger context window, and gives better benchmark results than similarly sized models.

- Harvard’s [Institutional Data Initiative](https://institutionaldatainitiative.org/) has assembled a large dataset of digitized copyright-free works for training language models. The collection currently has roughly 1 million books; it’s significantly larger than the Books3 dataset that was used to train earlier models.

- Microsoft’s Phi-4 model is now [available on Hugging Face](https://huggingface.co/microsoft/phi-4) and [Ollama](https://ollama.com/library/phi4). It’s yet another impressive model that can run on a reasonably well-equipped laptop.

- [4M](https://techxplore.com/news/2025-01-source-framework-language-multimodal-ai.html) is an open source framework for training multimodal AI models.

- NVIDIA has

   

  announced 

  [Project DIGITS](https://www.nvidia.com/en-us/project-digits/)

  , a personal supercomputer for running AI models up to 200B parameters locally. The system comes with 128GB of RAM. They will be available in May; the starting price is $3,000.

- O2 (the company, not the skilled GPT version number) has announced [Daisy](https://news.virginmediao2.co.uk/o2-unveils-daisy-the-ai-granny-wasting-scammers-time/), a language model of its own. It answers fraudulent phone calls in real time, wasting the scammer’s time by impersonating a vulnerable elderly person.

- [Fast-LLM](https://github.com/ServiceNow/Fast-LLM) is an open source library for training large language models. It can scale to run on anything from a single GPU to large clusters and can train models up to (and exceeding) 70B parameters.

##### More from the Learning Platform

- [*Practical Retrieval Augmented Generation (RAG)*](https://learning.oreilly.com/course/practical-retrieval-augmented/9780135414378/) (video)
- [*Building Applications with AI Agents*](https://learning.oreilly.com/library/view/building-applications-with/9781098176495/) (book)

## Programming

- Puppet joins the group of former open source projects that have an open source fork: [OpenVox](https://github.com/openvoxproject). OpenVox promises to be fully Puppet-compatible. The project is looking for sponsors.
- [Stratoshark](https://wiki.wireshark.org/Stratoshark) is a new tool for [analyzing system calls on Linux](https://stratoshark.org/). It’s a companion to Wireshark, with a similar user interface that’s designed to help users capture system calls and analyze what they’re doing.
- Need to write applications for the Cray X-MP in your basement? You’ll need a [compiler](https://github.com/kej715/ack). Here’s one that runs on Linux and macOS.
- [Sigstore](https://www.sigstore.dev/) is a project that simplifies digitally signing and managing open source software components. It reduces the burden of establishing provenance for software you’ve developed, along with checking the provenance of software dependencies you use.
- If you generate more code, there will be more code to debug and review. [Two-thirds](https://thenewstack.io/more-ai-more-problems-for-software-developers-in-2025/) of developers in groups that use AI are spending more time debugging and resolving security vulnerabilities.
- Do you really need a new terminal emulator? [Ghostty](https://ghostty.org/) is getting [rave reviews](https://thenewstack.io/ghostty-will-get-you-excited-about-using-a-terminal-again/). It’s worth trying. [Forgejo](https://forgejo.org/) is an open source software forge. It’s a decentralized platform for collaborative software development that includes a self-hosted alternative to GitHub.
- A startup is building [digital twins of cities](https://thenextweb.com/news/scenexus-building-digital-twins-of-cities). These will be very useful to city planners—and possibly also for emergency response.
- [Leptos](https://leptos.dev/) is a new [web framework for Rust](https://thenewstack.io/want-a-web-framework-for-rust-not-javascript-try-leptos/). Like Sycamore, another Rust web framework, Leptos compiles Rust to WebAssembly.
- The [International Obfuscated C Code Contest](https://www.ioccc.org/) is back! (Did you miss it?) For more information, follow @ioccc on Mastodon (fosstodon.org).
- [A chess engine in 84,688 regular expressions](https://nicholas.carlini.com/writing/2025/regex-chess.html): It’s a regex masterpiece. As the author says, more people should do entirely pointless things.

##### More from the Learning Platform

- [*How Linux Works*, 3rd Edition](https://learning.oreilly.com/library/view/how-linux-works/9781098128913/) (book)
- [*The Digital Twin Opportunity*](https://learning.oreilly.com/library/view/the-digital-twin/53863MIT63126/) (article)

## Security

- Cybercriminals are distributing malware through [*Roblox* mods](https://thenewstack.io/cybercriminals-are-not-playing-games-malware-hiding-in-roblox-mods/). Discord, Reddit, GitHub, and other communications channels are used to attract users to malware-containing packages.
- Cloudflare has successfully mitigated the [largest DDOS attack ever seen](https://www.bleepingcomputer.com/news/security/cloudflare-mitigated-a-record-breaking-56-tbps-ddos-attack/): 5.6 terabits/second from the Mirai botnet. An important new twist: Attacks are very short-lived, making human response impossible.
- Phishing doesn’t always start with an email. Cybercriminals are placing [Google search advertisements](https://www.bleepingcomputer.com/news/security/hackers-use-google-search-ads-to-steal-google-ads-accounts/) that direct victims to phishing sites that steal their credentials.
- The FBI has [forced the PlugX malware to delete itself](https://arstechnica.com/tech-policy/2025/01/fbi-forces-chinese-malware-to-delete-itself-from-thousands-of-us-computers/) from over 4,200 computers. Since roughly 2014, PlugX has been used by the Chinese government to steal data from victims. One suspects that the next version of PlugX won’t have a “self-delete” command.
- A new ransomware attack called [Codefinger](https://www.bleepingcomputer.com/news/security/ransomware-abuses-amazon-aws-feature-to-encrypt-s3-buckets/) encrypts AWS S3 buckets. The attack uses AWS’s server-side encryption (SSE) to generate cryptographic keys that Amazon doesn’t store; they are only known to the attacker.
- Microsoft has [sued](https://arstechnica.com/security/2025/01/microsoft-sues-service-for-creating-illicit-content-with-its-ai-platform/) a group of unnamed (and unknown) developers for compromising legitimate user accounts and using those accounts to generate harmful content.
- An [incorrect certificate](https://www.bleepingcomputer.com/news/security/docker-desktop-blocked-on-macs-due-to-false-malware-alert/) is causing macOS to treat Docker Desktop as malware, preventing it from starting. The problem can be fixed by upgrading to Docker 4.37.2.
- An [attack against the cryptocurrency transaction simulation mechanism](https://www.bleepingcomputer.com/news/security/new-web3-attack-exploits-transaction-simulations-to-steal-crypto/) tricks victims into approving transactions that strip their wallet of cryptocurrency.
- The [Cyber Trust Mark](https://www.nextgov.com/cybersecurity/2025/01/white-house-unveils-cyber-trust-mark-program-consumer-devices/401991/) is a certification intended to ensure consumers that devices incorporating AI meet certain standards set by the US National Institute of Standards and Technology (NIST) and the Federal Communications Commission (FCC).
- Apple is discovering that errors aren’t the only problem with consumer-facing AI; the company is also having problems with email and chat summaries that [make spam and fraud messages look legitimate](https://www.crikey.com.au/2025/01/08/apple-new-artificial-intelligence-rewords-scam-messages-look-legitimate/).
- [Security products based on fear](https://techxplore.com/news/2025-01-cybersecurity-products-consumers.html), along with security sales and marketing practices, are counterproductive.

## Web

- Regardless of the future of TikTok, [Pixelfed](https://pixelfed.org/)—a decentralized application for sharing photos and videos—looks like a good alternative. Like Mastodon, Pixelfed is part of the [fediverse](https://fediverse.info/) and is built on the federated ActivityPub protocol.
- [Mercator: Extreme](https://mrgris.com/projects/merc-extreme/) allows you to put the North Pole anywhere you want, and draws the corresponding Mercator map. Aside from being a web masterpiece, it shows just how distorted the Mercator projection is. Sadly, almost all of our maps are still based on it.
- [Marimo playgrounds](https://docs.marimo.io/guides/publishing/playground/) are notebooks (like Jupyter) that run entirely in the browser using WebAssembly. They can easily be created and shared on GitHub or on [marimo.app](https://marimo.app/).
- Most online organizations have some kind of web-based API access. Now that AI is in the picture, [APIs must be usable by AI agents](https://thenewstack.io/its-time-to-start-preparing-apis-for-the-ai-agent-era/). They need to be properly documented in a machine-readable fashion (e.g., with [OpenAPI](https://www.speakeasy.com/openapi#openapi-overview)) and as uniform as possible.
- A new [fork of the Flutter project](https://thenewstack.io/flutter-fork-designed-to-give-developers-release-valve/), called [Flock](https://getflocked.dev/), intends to provide features and bug fixes that users have wanted but that have never made it into the release.
- [Streets](http://streets.gl/) is a 3D version of OpenStreetMap. It takes a long time to load and many of the labels aren’t up-to-date, but it’s impressive.
- What’s the future of the web? If the web is to be a data source for AI, it will need to get much [simpler](https://tomtunguz.com/back-to-text/), shedding megabytes of JavaScript and CSS in favor of text.
- Something new in [CAPTCHAs: Play *Doom*](https://arstechnica.com/gaming/2025/01/someone-made-a-captcha-where-you-play-doom-on-nightmare-difficulty/) and kill at least three monsters. It was built with prompt-driven AI using Vercel’s v0 and runs in the browser with Wasm. Unfortunately, I doubt it will keep bots out for long.

##### More from the Learning Platform

- [*Principles of Web API Design: Delivering Value with APIs and Microservices*](https://learning.oreilly.com/library/view/principles-of-web/9780137355754/) (book)
- [*Mastering API Architecture*](https://learning.oreilly.com/library/view/mastering-api-architecture/9781492090625/) (book)

## Virtual Reality

- Swave is a startup that is building [holographic smart glasses](https://thenextweb.com/news/swave-startup-holographic-smart-glasses-funding) that project true holograms, not just hologram-like effects.

##### More from the Learning Platform

- [*Creating Augmented and Virtual Realities*](https://learning.oreilly.com/library/view/creating-augmented-and/9781492044185/) (book)

## Quantum Computing

- A new quantum computing technology [enables trapped ions to move](https://thenextweb.com/news/zuriq-quantum-computing-startup-funding) around on a quantum computing chip. This allows the developers to build chips that support more qubits efficiently.
- A new kind of quantum refrigerator makes it possible to [cool qubits](https://phys.org/news/2025-01-cold-quantum-refrigerator-paves-reliable.html) to 22 millikelvin. At lower temperatures, they will be less vulnerable to errors from noise.

##### More from the Learning Platform

- [*Quantum Computing Fundamentals*](https://learning.oreilly.com/course/quantum-computing-fundamentals/9780137872558/) (video)

## Robotics

- A [robotic hand](https://arstechnica.com/science/2025/01/robotic-hand-helps-pianists-overcome-ceiling-effect/) has been developed that can train pianists to perform very difficult movements more effectively.

## Biology

- AI can be used to [sharpen biological images](https://phys.org/news/2025-01-ai-technique-generates-images-thick.html) that have been distorted by light passing through layers of tissue. In the past, this problem has been solved with expensive adaptive optics.