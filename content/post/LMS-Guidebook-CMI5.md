---
# Common-Defined
title: "CMI5 In a Nutshell"
date: 2025-05-22T21:20:23+08:00
lastmod: 2025-05-22T21:29:20+00:00
draft: false
tags: ["LMS","CMI5"]
categories: ["index", "LMS", "CMI5"]
author: "hongxing"

# User-Defined
# You can close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
# You can also define another contentCopyright
contentCopyright: '<a rel="license noopener" href="https://creativecommons.org/licenses/by-nc-nd/4.0/" target="_blank">CC BY-NC-ND 4.0</a>'
reward: false
mathjax: true
---

# Concept Model
## Synopsis
- An LMS imports a course structure which contains at least one AU. Optionally, the course structure can include one or more blocks, which consist of 1 or more AUs or nested blocks.
- An LMS administrative user assigns a course to a learner.
- A learner authenticates with an LMS or a related system.
- A learner launches an AU from the LMS or an associated launching system, using an interface.
- The LMS writes launch data to the integrated LRS.
- The AU sends a message to the LMS requesting launch parameters and previous state information.
- Once the AU is fully initialized for learner viewing, it issues an "initialized" statement.
- The learner views the AU content and performs the learning. During this time, the AU MAY request data from, and store data to, the LMS.
- The learner exits the AU.
- The AU reports the final tracking data to the LMS and issues a "terminated" statement.
- Administrative users create and view reports of the tracking data recorded by the AUs for individual learners


## Responsibilities of the Assignable Unit:

- Parse the parameters from the launching environment to determine where the LMS location is and initiate communication with the LMS.
- Send an "initialized" statement indicating the AU is ready for learner viewing.
- Acting as a client, send and receive messages using the defined transport mechanism(s) and associated commands as prescribed in this specification.
- Format all data according to the defined data types and vocabularies that are defined in this specification.
- Send a "terminated" statement prior to terminating the AU's execution.

## Responsibilities of the LMS:
- Create and maintain course structures.
- Acting as a server, receive and reply to messages using the defined transport mechanism(s) and associated commands as prescribed in this specification.
- Format all data according to the defined data types and vocabularies that are defined in this specification.
- Launch the specified AU contained in the courses within the defined environment(s).

# References

1. [cmi5 Specification Profile for xAPI](https://github.com/AICC/CMI-5_Spec_Current/blob/quartz/cmi5_spec.md)
2. [cmi5 project](https://aicc.github.io/CMI-5_Spec_Current/)


# Definitions
- Administrator: The administrative user who manages the LMS and related systems. This user performs tasks such as learner enrollment, course structure definition, and report management.
- Activity: In this specification it is representative of an AU or the Object of a statement with objectType of “Activity”. Thus the granularity can be anything from a single AU course down to a specific interaction.
- Assignable Unit (AU): A learning content presentation launched from an LMS. The AU is the unit of tracking and management. The AU collects data on the learner and sends it to the LMS.
- Block: A grouping of AU's and other Blocks (nesting).
- Course: A collection of assignable units, in a logical grouping, of learning content. A course is typically an internal data structure. Courses are often assigned to learners and tracked by the LMS.
- Course Structure: A list of assignable units and launch parameters, with an implied sequence, representing a course.
- Experience API (xAPI): A runtime data communication specification for learning content (AU) to send and receive data to a Learning Record Store (LRS). xAPI is used to define the data transport and the data model.
- Internationalized Resource Identifier (IRI): A unique identifier according to RFC 3987. The IRI might be an IRL. IRLs SHOULD be defined within a domain controlled by the person creating the IRL. Note that IRI’s in this spec MUST be fully qualified and not IRI References.
- Internationalized Resource Locator (IRL): According to xAPI, an IRL is an IRI that, when translated into a URI (according to the IRI to URI rules), is a URL.
- Learner: The end user viewing/using the learning content (AUs).
- Learning Management System (LMS): A computer system that could include the capabilities to register learners, launch learning presentations, analyze and report learner performance, and track learners' progress. LMS launching, reporting, and tracking roles are the focus of the cmi5 specification. The LMS is integrated with an LRS. In the remainder of this document the term “LMS” refers to an integrated entity of LMS and LRS.
- Learning Records Store (LRS): As defined in xAPI.
- Registration: An enrollment instance of a learner in a course. (a registration ID uniquely identifies this). The registration ID persists throughout the course progress to completion and during review of a completed course. A new registration is created for new enrollment instances (such as recurrent courses or re-taking courses).
- Publisher ID: A unique identifier for each AU and Block, and for the course instance in the Course Structure that is the identifier provided by the publisher to identify the course elements. The purpose of this ID is to identify the course elements not the publisher itself.
- Session: A period of time marked by the launch of an AU until its termination (or abandonment).

# Abbreviations and Acronyms
- ADL: Advanced Distributed Learning
- AICC: Aviation Industry Computer-Based Training Committee
- API: Application Programming Interface
- CMI: Computer Managed Instruction
- JSON: JavaScript Object Notation
- IRI: Internationalized Resource Identifier
- IRL: Internationalized Resource Locator
- LMS: Learning Management System
- LRS: Learning Record Store
- PII: Personally Identifiable Information
- URI: Uniform Resource Identifier
- URL: Uniform Resource Locator
- URN: Uniform Resource Name
- xAPI: Experience API
- XML: Extensible Markup Language
- XSD: XML Schema Definition


