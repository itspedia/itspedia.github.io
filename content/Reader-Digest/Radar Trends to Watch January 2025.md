---
title: "Radar Trends to Watch: January 2025"
author: Mike Loukides
date: 2025-01-05T16:01:23+08:00
lastmod: 2025-01-05T16:01:23+08:00
draft: false
tags: ["digest", "trends"]
categories: ["digest", "index"]

menu:
  main:
    parent: "Knowledge"
    weight: 1
---

Despite its 31 days, December is a short month. It’s hard for announcements and happenings other than office parties to get attention. Fighting this trend, OpenAI made a series of announcements: their “12 Days of OpenAI.” Not to be upstaged, Google responded with a flurry of announcements, including their Gemini 2.0 Flash Thinking model. Models appeared that could use streaming audio and video for both input and output. But perhaps the most important announcement was DeepSeek-V3, a very large mixture-of-experts model (671B parameters) that has performance on a par with the other top models—but cost roughly 1/10th as much to train.

Artificial Intelligence
-----------------------

*   [DeepSeek-V3](https://huggingface.co/deepseek-ai/DeepSeek-V3-Base) is another LLM to watch. Its performance is on a par with Llama 3.1, GPT-4o, and Claude Sonnet. While training was not inexpensive, the [cost of training](https://buttondown.com/ainews/archive/ainews-deepseek-v3-671b-finegrained-moe-trained/) was estimated to be roughly 10% of the bigger models.
*   Not to be outdone by Google, OpenAI [previewed](https://arstechnica.com/information-technology/2024/12/openai-announces-o3-and-o3-mini-its-next-simulated-reasoning-models/) its next models: o3 and o3-mini. These are both “reasoning models” that have been trained to solve logical problems. They may be released in late January; OpenAI is looking for [safety and security researchers](https://openai.com/index/early-access-for-safety-testing/) for testing.
*   Not to be outdone by 12 Days of OpenAI, Google has released a new experimental model that has been trained to solve logical problems: [Gemini 2.0 Flash Thinking](https://ai.google.dev/gemini-api/docs/thinking-mode). Unlike OpenAI’s GPT models that support reasoning, Flash Thinking shows its chain of thought explicitly.
*   Jeremy Howard and his team have [released ModernBERT](https://huggingface.co/blog/modernbert), a major [upgrade](https://bdtechtalks.com/2024/12/27/modernbert-llm-encoder/?utm_source=feedly&utm_medium=rss&utm_campaign=modernbert-llm-encoder) to the BERT model they released six years ago. It comes in two sizes: 139M and 395M parameters. It’s ideal for retrieval, classification, and entity extraction, and other components of a data pipeline.
*   AWS’s Bedrock service has the ability to [check the output of other models](https://thenewstack.io/amazons-bedrock-can-now-check-ai-for-hallucinations/) for hallucinations.
*   To make sure they aren’t outdone by 12 Days of OpenAI, Google has [announced Android XR](https://blog.google/products/android/android-xr/), an operating system for extended reality headsets and glasses. Google doesn’t plan to build their own hardware; they’re partnering with Samsung, Qualcomm, and other manufacturers.
*   Also not to be outdone by 12 Days of OpenAI, Anthropic has announced [Clio](https://www.anthropic.com/research/clio), a privacy- preserving approach to finding out [how people use their models](https://x.com/AnthropicAI/status/1867325190352576780). That information will be used to improve Anthropic’s understanding of safety issues and to build more helpful models.
*   Not to be outdone by 12 Days of OpenAI, Google has [announced](https://blog.google/technology/google-deepmind/google-gemini-ai-update-december-2024/#ceo-message) Gemini 2.0 Flash, a multimodal model that supports streaming for both input and output. The announcement also showcased [Astra](https://www.technologyreview.com/2024/12/11/1108493/googles-new-project-astra-could-be-generative-ais-killer-app/), an AI agent for smartphones. Neither is generally available yet.
*   OpenAI has released [canvas](https://openai.com/index/introducing-canvas/), a new feature that combines programming with writing. Changes to the canvas (code or text) immediately become part of the context. Python code is executed in the browser using Pyodide (Wasm), rather than in a container (as with Code Interpreter).
*   Stripe has [announced](https://stripe.dev/blog/adding-payments-to-your-agentic-workflows) an [agent toolkit](https://github.com/stripe/agent-toolkit) that lets you build payments into agentic workflows. Stripe recommends using the toolkit in test mode until the application has been thoroughly validated.
*   Simon Willison [shows](https://simonwillison.net/2024/Dec/9/llama-33-70b/#atom-everything) how to run a GPT-4 class model (Llama 3.3 70B) on a reasonably well-equipped laptop (64GB MacBook Pro M2).
*   As part of their 12 Days of OpenAI series, OpenAI finally released their video generation model, [Sora](https://openai.com/sora/). It’s free to ChatGPT Plus subscribers, though limited to 50 five-second video clips per month; a ChatGPT Pro account relaxes many of the limitations.
*   Researchers have shown that advanced AI models, including Claude 3 Opus and OpenAI o1, are capable of “[scheming](https://www.apolloresearch.ai/research/scheming-reasoning-evaluations)”: working against the interests of their users to achieve their goals. Scheming includes subverting oversight mechanisms, intentionally delivering subpar results, and even taking steps to prevent shutdown or replacement. Hello, HAL?
*   [Roaming RAG](https://arcturus-labs.com/blog/2024/11/21/roaming-rag--make-_the-model_-find-the-answers/) is a new technique for retrieval augmented generation that finds relevant content by searching through headings to navigate documents—like a human might. It requires well-structured documents. A surprisingly simple idea, really.
*   Google has announced [PaliGemma 2](https://developers.googleblog.com/en/introducing-paligemma-2-powerful-vision-language-models-simple-fine-tuning/), a new version of its Gemma models that incorporates vision.
*   GPT-4-o1-preview is no more; the preview is now the real thing, [OpenAI o1](https://openai.com/o1/). In addition to advanced reasoning skills, the production release claims to be faster and to deliver more consistent results.
*   A group of AI agents in _Minecraft_ [behaved surprisingly like humans](https://www.technologyreview.com/2024/11/27/1107377/a-minecraft-town-of-ai-characters-made-friends-invented-jobs-and-spread-religion/)—even developing jobs and religions. Is this a way to model how human groups collaborate?
*   One thing the AI industry needs desperately (aside from more power) is [better benchmarks](https://www.technologyreview.com/2024/11/26/1107346/the-way-we-measure-progress-in-ai-is-terrible/). Current benchmarks are closed, easily gamed (that’s what AI does), and unreproducible, and they may not test anything meaningful. [Better Bench](https://betterbench.stanford.edu/) is a framework for assessing benchmark quality.
*   [Palmyra Creative, a new language model from Writer](https://venturebeat.com/ai/writer-new-ai-model-aims-to-fix-the-sameness-problem-in-generative-content/), promises the ability to develop “style” so that all AI-generated output won’t sound boringly the same.
*   During training AI picks up biases from human data. When humans interact with the AI, there’s a [feedback loop](https://techxplore.com/news/2024-12-bias-ai-amplifies-biases.html) that amplifies those biases.

##### More from the Learning Platform

*   [_Hands-On Large Language Models_](https://learning.oreilly.com/library/view/hands-on-large-language/9781098150952/) (book)
*   [_Build a Large Language Model (From Scratch)_](https://learning.oreilly.com/library/view/build-a-large/9781633437166/) (book)

Programming
-----------

*   [Unicon](https://btiffin.users.sourceforge.net/up/unicon.html) may never become one of the top 20 (or top 100) programming languages, but it’s a descendant of [Icon](https://www2.cs.arizona.edu/icon/), which was always my favorite language for string processing.
*   What do CAPTCHAs mean [when LLM-equipped bots can successfully complete tasks set for humans](https://techxplore.com/news/2024-12-human-bot-longer-ai-agents.html)?
*   [egui](https://github.com/emilk/egui), together with [eframe](https://github.com/emilk/egui/tree/master/crates/eframe), is a GUI library and framework for Rust. It’s portable and runs natively (on macOS, Windows, Linux, and Android), on the web (using Wasm), and in many game engines.
*   For the archivist in us: The [Manx](https://manx-docs.org/about.php) project isn’t about an island in the Irish Sea or about cats. It’s a catalog of manuals for old computers.
*   [Cerbrec](https://cerbrec.com/) is a graphical Python [framework for deep learning](https://thenewstack.io/cerbrec-a-framework-for-python-devs-without-ai-experience/). It’s aimed at Python programmers who don’t have sufficient expertise to build applications with PyTorch or other AI libraries.
*   GitHub has [announced](https://github.blog/news-insights/product-news/github-copilot-in-vscode-free/) free access to GitHub Copilot for all current and new users. Free access gives you 2,000 code completions and 50 chat messages per month. They’ve also added the ability to use Claude 3.5 Sonnet in addition to GPT-4o.
*   [Devin](https://www.cognition.ai/), the AI assisted coding tool that claims to support software development from beginning to end, including design and debugging, has reached [general availability](https://www.cognition.ai/blog/devin-generally-available).
*   JSON5, also known as “[JSON for humans](https://json5.org/),” is a variant of JSON that has been designed for human readability so that it can be written and maintained by hand—for example, in configuration files.
*   AWS has [announced](https://thenewstack.io/aws-debuts-a-distributed-sql-database-s3-tables-for-iceberg/) two significant new services: [Aurora DSQL](https://aws.amazon.com/rds/aurora/dsql/), which is a distributed SQL database, and [S3 Tables](https://aws.amazon.com/s3/features/tables/), which supports data lakehouses through Apache Iceberg.
*   [Autoflow](https://github.com/pingcap/autoflow?tab=readme-ov-file) is an open source tool for creating a knowledge graph. It’s based on TiDB (a vector database), LlamaIndex, and DSPy.

##### More from the Learning Platform

*   [_The Rust Programming Language_, 2nd Edition](https://learning.oreilly.com/library/view/the-rust-programming/9781098156817/) (book)
*   [_Learning GitHub Copilot_](https://learning.oreilly.com/library/view/learning-github-copilot/9781098164645/) (book)

Security
--------

*   [Portspoof](https://drk1wi.github.io/portspoof/) is a security tool that causes all 65,535 TCP ports to appear open for valid services. It emulates a valid service on every port. It makes it difficult for an attacker to determine which ports are actually open without probing each port.
*   [Let’s Encrypt](https://letsencrypt.org/), which issues the certificates that websites (and other applications) use to prove their identities, has announced [short-lived certificates](https://letsencrypt.org/2024/12/11/eoy-letter-2024/) that expire after six days. Short-lived certificates increase security by minimizing exposure if a private key is compromised.
*   Because of the continued presence of attackers within telecommunications networks, the US FBI and CISA have [recommended](https://www.bleepingcomputer.com/news/security/white-house-salt-typhoon-hacked-telcos-in-dozens-of-countries/) the use of encrypted communications protocols. (Though they still want backdoors into encryption systems, which would make them vulnerable to attack.)
*   A [new phishing attack](https://www.bleepingcomputer.com/news/security/novel-phising-campaign-uses-corrupted-word-documents-to-evade-security/) uses corrupted Word documents to bypass security checks. While the documents are corrupt, Word is able to recover them.
*   [LLM Flowbreaking](https://www.knostic.ai/blog/introducing-a-new-class-of-ai-attacks-flowbreaking) is a new class of attack against language models that prevent guardrails from stopping objectionable output from reaching the user. These attacks take advantage of race conditions in the application’s interaction with users.
*   [Bootkitty](https://arstechnica.com/security/2024/11/found-in-the-wild-the-worlds-first-unkillable-uefi-bootkit-for-linux/) is a [UEFI rootkit](https://www.bleepingcomputer.com/news/security/researchers-discover-bootkitty-first-uefi-bootkit-malware-for-linux/) that targets secure boot on Ubuntu systems. It appears to have been developed by [cybersecurity students in Korea](https://www.bleepingcomputer.com/news/security/bootkitty-uefi-malware-exploits-logofail-to-infect-linux-systems/), then leaked (possibly accidentally). It hasn’t yet been found in the wild, but when it is, it will be a dangerous threat.
*   DEF CON has started a project to [improve cybersecurity for water infrastructure](https://www.theregister.com/2024/11/24/water_defcon_hacker/) in the US. They’re starting with six water companies serving rural communities.

##### More from the Learning Platform

*   [_CompTIA Security+ SY0-701_](https://learning.oreilly.com/course/comptia-security-sy0-701/9780138251062/) (video)
*   [_Fighting Phishing_](https://learning.oreilly.com/library/view/fighting-phishing/9781394249206/) (book)

Quantum Computing
-----------------

*   Google has [built](https://arstechnica.com/science/2024/12/google-gets-an-error-corrected-quantum-bit-to-be-stable-for-an-hour/) a [quantum computing chip](https://blog.google/technology/research/google-willow-quantum-chip/) in which an [error-corrected logical qubit](https://arxiv.org/abs/2408.13687v1) can remain stable for an hour. It passes the “below threshold”: the error rate decreases as physical qubits are added for error correction. The chip was built in Google’s new fabrication facility.

Web
---

*   Google is adding “[store reviews](https://www.bleepingcomputer.com/news/google/google-chromes-ai-feature-lets-you-quickly-check-website-trustworthiness/)” to Chrome. Reviews are AI-generated summaries of reports from well-known sources that report scams and other issues.
*   Here’s a how-to on [building streaming text user interfaces](https://www.phpied.com/ai-streaming-text-ui-how-to/) on the web. Streaming text is almost a necessity for building AI-driven chatbots.

Biology
-------

*   Yes, we can have virtual taste. A research group has developed a [lollipop interface](https://techxplore.com/news/2024-11-lollipop-interface-simulating-virtual-environments.html) so that people can experience taste in virtual worlds.