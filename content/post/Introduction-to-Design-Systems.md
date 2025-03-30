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

### Contextual Rules
Creating contextual rules may be necessary. Contextual rules occur when there is an instance that requires a deviation from the standard guidelines.

## Design Principles
Every organization has a unique set of needs and goals. The ability to communicate these needs and goals through a set of principles will allow you to shape the way your organization talks about its product.

### Defining Design Principles
Design principles combine organizational goals with user needs, creating the core values that aid us in making crucial design decisions. Effective design principles will align designers and build cohesiveness within your product and across teams. Additionally, design principles provide an anchor for teams to rally around. 

### A Practical Guide to Creating Your Own

**A Practical Guide to Creating Your Own**

- Focus on creating three to five solid design principles that reflect the goals of your organization and the needs of your user base. 
- A value hierarchy allows your team to understand which principles hold more weight. Visualizing the hierarchy by creating an ordered list, or pyramid structure, can be helpful.


Defining Your Design Principles
1. Build a team: Start by inviting your whole team to participate. The more discussion you have as a group, the better the alignment you will achieve within your team. Include engineers and product managers as part of the conversation. Gaining their buy-in and insight from the start is vital to building your shared language.
2. Set a clear purpose: Ensure the team understands the objective of the meeting. The goal should be to determine which principles best align with your organizational goals and user needs. If these are unknown to you and your team, seek out key stakeholders within your organization. You should be able to produce a list of goals and needs prior to determining your design principles. Also, understand that these goals and needs may change over time.
3. Prepare: Ask each team member to brainstorm five to ten ideas in advance. This will make the discussion more productive, as each person will bring new ideas to the table at the start of the meeting.
4. Discuss: Bring physical sticky notes or use an online platform that allows you and your team to move ideas around on a board easily. This provides a way to group similar ideas and visually see which concepts stand out. Allow some time for new ideas to form and address outliers or conflicts as they come up. When in doubt, revisit your organizational goals and user needs to better map your design principles to those values.
5. Iterate: Goals and needs change over time. Be open to adjusting your design principles as your organization shifts. Recognize when a principle is not benefiting your team and strive to keep your principles at the forefront of your design thinking.


### A Shared Language
Including other teams in the creation process of your system will lead to a better understanding of the overall language you are creating. To be fluent in a language, you must actively use it. The same can be said for your design system. The more team members you have using and contributing to it, the more cohesion your organization will experience.

Keep in mind that a design system, just like a language, can and should evolve over time. Change is a natural part of a language that allows new functions and concepts to form. As you begin to craft your own design language, be rigid with your guidelines but be open to change as your system adapts and grows.

# Implementing Your System
## Assessing Your Organization
## Gathering a Support System
Over the course of implementation, you will need a team that can:
- Research best practices.
- Make an interface inventory.
- Design and define your layout, styles, and components.
- Document guidelines.
- Review documentation.
- Build and implement components.
- Iterate and refine.
- Evangelize your efforts across your organization.

## Assessing Your Product
Creating systematic design requires a structured approach.
### Utilize an Interface Inventory
Inconsistencies within your product can lead to confusing experiences for your users. To help understand the current state of your product or application, create an interface inventory. An inventory will surface inconsistencies and lay the groundwork for correcting them.

To begin, capture and record all of the elements and components used within your UI. The easiest way to do this is to screenshot each one. You don’t need to log every instance, simply document each unique design. Include typography, inputs, radios, buttons, etc. Be meticulous. Every individual element and component used throughout your product should be recorded. Navigate page by page until you feel confident that you have grabbed each one.


## Creating a Predictable Architecture
How you organize your system is crucial to the success of your design system. Breaking your system down into predictable categories will keep your content easily discoverable. Remain open to adjusting the architecture as you build out and expand on your system.

### Categorizing to Improve Discoverability
Design sytems could be broken into the following six interlocking areas:
- Layout: Defined measures that make up your spacing and grid system.
- Styles: Core aspects of your visual language. These include colors, iconography, and typography.
- Components: Core elements of an interface. These include buttons and form fields.
- Regions: Overarching design paradigms, such as navigation or search.
- Content: Information regarding the voice and tone, as well as punctuation guidelines. Content can also include terminology if your product has a specific vocabulary.
- Usability: Rules that define accessibility and internationalization.


### Card Sorting
As your design system expands, you may not always be sure where specific content should live. When this happens, utilize a card-sorting technique to determine what should be grouped together. You may find that you need to add a new category, or change a category name, to fit new content.


## Layout
A foundational aspect included in your system is the layout, which includes guidelines for both your spacing and grid. These provide a solid base from which you can create components and build interfaces.

### Spacing
A series of spacing increments will create the foundation for the padding and margin used within your product. 

**It's funny!**

