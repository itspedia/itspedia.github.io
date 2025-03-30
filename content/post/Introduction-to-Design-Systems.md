---
# Common-Defined
title: "Introduction to Design Systems"
date: 2025-03-28T21:20:23+08:00
lastmod: 2025-03-28T21:29:20+00:00
draft: false
tags: ["Design Sytem", "UI", "UX"]
categories: ["index", "Design System"]
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

# Six interlocking areas that make up a design system
1. Layout: Defined measures that make up your spacing and grid system.
2. Styles: Core aspects of your visual language. These include colors, iconography, and typography.
3. Components: Core elements of an interface. These include buttons and form fields.
4. Regions: Overarching design paradigms, such as navigation or search.
5. Content: Information regarding the voice and tone, as well as punctuation guidelines. Content can also include terminology if your product has a specific vocabulary.
6. Usability: Rules that define accessibility and internationalization.


## Terms used for referencing different aspects within design systems:
- Elements: The lowest-level object. Elements cannot be broken down further. This can include labels and icons.
- Components : A combination of one or more elements that function as a whole, such as a form.
- Component groups: A group of components that form a larger component.

## Style Guides, Component Libraries, and Design Systems
- Style guide: Static documentation that defines how the brand is stylistically applied to interface elements. It contains high-level details about color, typography, iconography, and more.
- Component library: A set of styles and components that can be used and shared among a team. A component library consists of common core elements that are used throughout an application. If supported by a design tool, they can automatically sync across design files when a change is made. Component libraries may or may not include living code.
- Design system: A series of documented elements, components, and regions that include both design and front-end guidelines. The documentation contains live code examples, allowing cross-functional teams to easily reuse styles and components in several instances across an application. A design system also includes underlying design principles, rules, and guidelines that help a team build one or multiple products.


# Design As a Language

The basis of language is composed of two attributes,
- Lexicon: Within a language, a lexicon refers to the total number of fragments (or words) that make up that language. These fragments form the foundation of a language and can be arranged and rearranged in an infinite number of ways. When viewed in their simplest form, these fragments are meaningless. Often, it isn’t until we begin using them as building blocks that we can derive meaning and effectively communicate with one another. 
- Grammar: Language relies on a system of rules, known as a grammar. Without a shared understanding of the rules that govern a language, we are bound to experience misconceptions and communication breakdown. Once a grammar is established, we can focus on higher-level ideas, rather than form or structure. Within a design system, guidelines are introduced to form the grammar of our system. In other words, usage and technical guidelines help define when and how individual components should be used. 
 
By thinking about design as a language system, we can create a lexicon comprised of elements and document a grammar, or series of guidelines, that govern their use. Each language contains a different set of a lexicon and a grammar, making the language unique. 
 
In terms of a design system, guiding principles are used as the method to create a design language that is distinct to your organization. These principles enable you to build a relationship that addresses both user needs and organizational goals.
 
 
## Lexicon: The Elements of Your System
Language is a system comprised of interconnecting elements that work together to aid communication. Thinking about design as a system will allow you to create the lexicon, or building blocks, that can be arranged in multiple ways to make up your product.

Depending on the state of your organization, it can be helpful to approach thinking systematically from two directions:
1. Building up elements to create larger interfaces.
2. Breaking down interfaces into their simplest elements.


### Building Up Elements
Start by identifying what elements are commonly used. These include various stylistic elements, such as typography and colors, as well as interactive components, such as inputs, buttons, and so on.
 
### Breaking Down Interfaces
The most effective way of breaking down an interface is to create an inventory of the elements, components, and component groups you already use within your product.

### How a System Helps You Scale Design

Building up and breaking down your interface are two methods of thinking about design systematically. These approaches are not sequential; they can happen at the same time. Think holistically, while also considering the individual pieces that make up the whole. Considering each piece that makes up a design will ensure that you are defining components that can be used globally across your product

## Grammar: The Guidelines of Your System
A grammar is formed when you apply formal rules to govern the behavior of your elements. 

### Different Types of Guidelines
There are several types of guidelines that should be included within your design system. These include:
- A formal definition: A brief overview of what you are documenting. What is a button? This may seem straightforward to you, but being explicit strengthens your language and the overall understanding that your team shares.
-Usage guidelines: Explain the use of each component. Include behavioral rules. When should you use placeholder text within an input? How do alerts differ from toast notifications? These are questions that should be answered when reading your design system.
- Technical guidelines: Work closely with your engineering team to include any technical guidelines that will aid in the creation and use of a component within your product. This could include class names, as well as other options passed via data attributes or JavaScript.
- Related components: Link related components to help those navigating your system find what they are looking for more easily.

