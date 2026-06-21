# The survey — full question list

This is the complete survey in plain text, so you can read, review, or share it without a LimeSurvey login. The importable version is in [`academic-ospo-readiness-survey-template.lss`](academic-ospo-readiness-survey-template.lss). For setup, see [`instructions/`](../instructions/).

Words in **[brackets]** are placeholders you replace before launch (see `instructions/10-setup.md`). Question codes (Q10, Q20, …) match the LimeSurvey template so you can find any question quickly.

Each question below is tagged **(required)** or **(optional)**, matching the template. Required questions must be answered before the page can be submitted; where a question is shown only conditionally, that applies when it appears. All of Section 5 is optional — it is gated by Q51.

**The survey shows one group per page.** Sections 3, 4, and 5 are split across several pages, each with its own `· N of N` page label; a short intro page opens Sections 3 and 4. Horizontal rules below mark page breaks, mirroring what a respondent sees.

---

## Introduction

Thank you for taking part. **[ORGANIZATION]** is working to understand and strengthen how it develops, manages, and sustains the open source software it relies on. This survey helps build a picture of current open source practices and the support that would be most valuable.

Your feedback will help build a picture of current open source practices as understood by the people who respond, highlight where support is most wanted, and give a starting point for planning how to expand it.

Participation is entirely voluntary and you may withdraw at any time. Final published results will be anonymised. **[DATA-HOSTING STATEMENT]**

For questions about this survey, please contact **[CONTACT NAME]** at **[CONTACT EMAIL]**.

Estimated time to complete: about 12 minutes.

---

## Section 1 — About you

**Q10. What is your role at [ORGANIZATION]?** *(required — you may name your unit, department, or group in the comment box)*

- Leadership / Administration
- Faculty / Academic staff
- Research staff (postdocs, research software engineers)
- Professional / Support staff (including IT and library)
- Student (graduate or undergraduate)
- Other (please specify)

---

## Section 2 — Importance of open source

**Q20. How important is open source to [ORGANIZATION]'s mission?** *(required)*

- Not important
- Somewhat important
- Important
- Critical
- I don't know

**Q21. Why is open source important to your work?** *(required — tick all that apply — shown only if open source is at least somewhat important to you)*

- Reduces vendor lock-in
- Lowers costs
- Enables collaboration across the research and education community
- Supports transparency and trust
- Accelerates innovation
- Fulfils funder or regulatory requirements
- Aligns with digital-sovereignty or institutional-autonomy goals
- None — open source is not important to my work
- Other (please specify)

---

### Your confidence with open source practices

**Q22. How confident are you in your knowledge of open source practices relevant to your role?** *(required)*

- Not confident
- Somewhat confident
- Confident
- Very confident

---

## Section 3 — Current open source practices

### Current open source practices · intro page

Over the next several pages we ask what [ORGANIZATION] already does with open source: its policies, security, contributions, and similar work. Each page covers one topic.

Answer from your own knowledge. Tick what you know is already in place, and if you haven't heard of something, leave it unticked instead of guessing. Not knowing is a fine answer.

---

### Current open source practices · 1 of 8
**Policy and open source program office**

**Q300.** Tick the ones you know are already in place. *(required — select all that apply)*

- Has an open source program office (OSPO) or equivalent function
- Has an open source use policy
- Has a defined process for using open source software
- Provides staff with guidance on the responsible use of open source AI
- None of the above

*Q301. (optional) Where is support for "policy and open source program office" activities currently available at [ORGANIZATION]? (e.g. a specific team, role, or service)*

---

### Current open source practices · 2 of 8
**Compliance and risk**

**Q310.** Tick the ones you know are already in place. *(required — select all that apply)*

- Has standardized controls around open source use
- Has an automated process for managing open source IP / license compliance
- Includes open source risk management in its compliance policy
- Engages its technology-transfer or knowledge-exchange office when releasing or licensing open source software
- Provides internal license-compliance training
- Addresses AI-generated code (licensing, attribution, and IP) in its open source or compliance policy
- None of the above

*Q311. (optional) Where is support for "compliance and risk" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 3 of 8
**Security and supply chain**

**Q320.** Tick the ones you know are already in place. *(required — select all that apply)*

- Uses code-scanning tools to audit software composition and dependencies
- Runs penetration tests and periodic threat assessments for open source software
- Provides security training for teams working on open source software
- None of the above

*Q321. (optional) Where is support for "security and supply chain" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 4 of 8
**Open source selection, use, and procurement**

**Q330.** Tick the ones you know are already in place. *(required — select all that apply)*

- Has a process to choose between open source alternatives
- Prefers open source solutions over proprietary software where appropriate
- Applies open source criteria in procurement decisions
- Has a procurement process that doesn't hinder open source use
- Maintains a software asset registry / inventory
- Provides internal training on open source usage policies and procedures
- None of the above

*Q331. (optional) Where is support for "open source selection, use, and procurement" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 5 of 8
**Open source contribution**

**Q340.** Tick the ones you know are already in place. *(required — select all that apply)*

- Has policies to govern contribution to open source ecosystems
- Has a clear policy for how staff publish or contribute to open source projects
- Has processes that support open source contribution
- Has a review process for code and non-code contributions
- Has a lifecycle process for engaging with open source projects
- None of the above

*Q341. (optional) Where is support for "open source contribution" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 6 of 8
**Community and outreach**

**Q350.** Tick the ones you know are already in place. *(required — select all that apply)*

- Promotes and rewards contribution to open source projects
- Tracks staff or members' open source contributions
- Maintains an inventory of open source projects created within [ORGANIZATION]
- Fosters outreach for the visibility of its open source projects
- Engages marketing / communications in open source publishing efforts
- None of the above

*Q351. (optional) Where is support for "community and outreach" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 7 of 8
**Hosting and maintenance**

**Q360.** Tick the ones you know are already in place. *(required — select all that apply)*

- Has a defined process for open-sourcing internal projects
- Holds maintainer status on one or more open source projects
- Measures the health of the open source projects it maintains
- Tracks the adoption and impact of its research software (downloads, citations, reuse)
- Is a member of one or more software foundations
- Tracks KPIs / metrics around its open source foundation engagement
- Provides shared development infrastructure (e.g. code hosting, CI/CD) for its open source projects
- Offers compute or storage resources to support open source development
- None of the above

*Q361. (optional) Where is support for "hosting and maintenance" activities currently available at [ORGANIZATION]?*

---

### Current open source practices · 8 of 8
**Leadership and strategy**

**Q370.** Tick the ones you know are already in place. *(required — select all that apply)*

- Management recognises the benefits of open source
- Management understands the cost savings of open source
- Defines goals and objectives in an open source strategy
- Connects its open source work to its research mission and impact
- Has a strategy for the financial sustainability of its open source projects
- Allocates dedicated budget or funding to sustain and maintain its open source projects
- Formally allocates staff time to open source maintenance and contribution
- None of the above

*Q371. (optional) Where is support for "leadership and strategy" activities currently available at [ORGANIZATION]?*

---

## Section 4 — Open source support needs

### Open source support needs · intro page

[ORGANIZATION] wants to do a better job of supporting open source work, and is working out how. The pages that follow list kinds of support it might offer, grouped by topic.

Start with your own work. Tick what would help you, and leave the rest. You don't need to weigh up what other people might want.

---

### Open source support needs · 1 of 7
**Legal, compliance, and risk**

**Q400.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Legal and open source licensing advice and support
- Advice on security management
- Advice on dependency management
- Assessing vendor open source obligations (e.g. CRA compliance, software bills of materials)
- Grant compliance with respect to open source requirements
- Policy recommendations and best practices around open source AI
- None of the above

*Q401. (optional) Is there any other "legal, compliance, and risk" support that would be valuable to you?*

---

### Open source support needs · 2 of 7
**Open source selection, use, and procurement**

**Q410.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Guidelines or policies for using open source software within [ORGANIZATION]
- Guidelines or policies for procuring open source software
- A curated catalogue or directory of open source tools relevant to [ORGANIZATION]'s community
- None of the above

*Q411. (optional) Is there any other "open source selection, use, and procurement" support that would be valuable to you?*

---

### Open source support needs · 3 of 7
**Open source project creation and maintenance**

**Q420.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Guidelines or policies on managing and maintaining an open source project
- Guidance on transitioning an internal project to open source
- Support writing documentation for open source projects
- An assessment or audit of my open source project's community health and contributor readiness
- None of the above

*Q421. (optional) Is there any other "open source project creation and maintenance" support that would be valuable to you?*

---

### Open source support needs · 4 of 7
**Community and mentoring**

**Q430.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- An open source community of practice, discussion group, or learning group
- Mentorship on open source practices for myself or my team
- Mentoring programmes to bring new people into my project
- Training, workshops, and educational materials on open source topics and tools (e.g. programming languages, popular packages)
- None of the above

*Q431. (optional) Is there any other "community and mentoring" support that would be valuable to you?*

---

### Open source support needs · 5 of 7
**Funding and sustainability**

**Q440.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Support identifying potential funding sources
- Support with grant applications and grant writing
- Dedicated grants or funding from [ORGANIZATION] to sustain and maintain my open source projects
- Help developing a sustainable business or funding model for my open source project
- None of the above

*Q441. (optional) Is there any other "funding and sustainability" support that would be valuable to you?*

---

### Open source support needs · 6 of 7
**Tools and compute resources**

**Q450.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Hosted development tools and infrastructure for open source software
- Support creating containers (e.g. Docker) for my open source software
- Access to CPU or high-performance computing resources at low or no cost
- Access to GPU resources (e.g. for AI/ML workloads) at low or no cost
- Access to data storage infrastructure at low or no cost
- Access to CI/CD pipelines and automated testing infrastructure at low or no cost
- Access to hosted test or staging environments at low or no cost
- Access to licensed software, SaaS tools, or development platforms at low or no cost
- None of the above

*Q451. (optional) Is there any other "tools and compute resources" support that would be valuable to you?*

---

### Open source support needs · 7 of 7
**Advocacy and outreach**

**Q460.** Tick the support you'd find valuable for your open source work. *(required — select all that apply)*

- Internal advocacy support to secure organisational buy-in for open source
- Marketing and promotion support for my open source projects
- Help hosting, planning, or co-sponsoring open source events (e.g. conferences and hackathons)
- Support building partnerships and collaborations with external organisations
- Support communicating or measuring the societal impact of my open source work
- None of the above

*Q461. (optional) Is there any other "advocacy and outreach" support that would be valuable to you?*

---

## Section 5 — Your background in open source

### Your background in open source · 1 of 4

*Q50. If you are willing, please tell us about your background with open source. The next questions are optional.*

**Q51. Would you be willing to answer a few optional questions about your personal experience with open source?** *(required — seven more questions about your own experience)*

- Yes
- No

*Pages 2–4 below appear only if you answered "Yes."*

---

### Your background in open source · 2 of 4

**Q52. People participate in open source in different ways. Which of the following activities do you engage in?** *(required — tick all that apply)*

- Follow updates and discussions of open source projects
- Use open source applications
- Use open source dependencies in other projects
- Participate in open source development (feature requests, filing bugs, contributing docs or code, maintenance, community management, etc.)
- Other (please specify)
- None of the above

**Q53. Which of the following activities do you take part in?** *(required — tick all that apply)*

- Contribute code
- Contribute documentation
- Maintain a project (review and merge contributions, manage releases)
- Report or document bugs and unexpected behaviours
- Offer ideas for new features
- Perform organisational / administrative functions (manage mailing lists, organise events)
- Grow a project (marketing, outreach, sales, growth, community management)
- Develop open source policy
- None of the above

---

### Your background in open source · 3 of 4

**Q54. Which of these open source contributor roles has ever applied to you?** *(required — tick all that apply)*

- Maintainer: authoring much or most of the codebase / designs for at least one open source product intended for public reuse
- Contributor: contributing smaller amounts of code or design, e.g. fixing bugs or adding features
- Bug / issue reporter: reporting bugs or issues, or requesting new features
- Supervisor: guiding the strategic vision of at least one project, and/or acquiring funding for it
- IT / systems administrator: providing technical infrastructure for open source developers
- UI / UX designer: creating user-centered interfaces and experiences
- Community manager: engaging the community, facilitating communication, encouraging contributions
- Technical support: assisting users through forums, email, or other channels
- Educator: creating documentation, tutorials, articles, or other learning materials
- Other (please specify)
- None of the above

**Q55. Why do you participate in open source projects?** *(required — tick all that apply)*

- My work duties include contributing to open source projects
- To carry out other work duties, but I am not required or expected to do so
- To improve the tools in my field
- To customise existing tools for my specific needs
- To build a network of peers
- To give back to the open source community
- To improve my skills
- Because it's fun
- Other (please specify)
- None of the above

---

### Your background in open source · 4 of 4

**Q56. What category(ies) of open source projects have you participated in?** *(required — tick all that apply)*

- Hardware: physical devices used for research (cameras, robots, behavioural rigs) and associated code
- Applications: standalone software systems designed to be used as-is
- Plug-ins or extensions: add-ons that extend existing software or platforms
- Libraries, packages, or frameworks: reusable code distributed through established community mechanisms
- Automation scripts: scripts or tools to automate workflows or repetitive tasks
- Website code: back-end or front-end website components
- Other (please specify)
- None of the above

**Q57. Which of the following challenges have you encountered while participating in open source projects?** *(required — tick all that apply)*

- Limited time for writing new code
- Limited time for writing documentation
- Managing issues and pull requests
- Attracting users and/or contributors
- Receiving recognition for my contributions
- Finding and hiring qualified personnel
- Managing security risks
- Finding a community of peers who share my interests
- Finding mentors
- Finding time to educate myself
- Identifying helpful educational resources
- Navigating licensing and other legal issues
- Identifying potential funding sources for my open source projects
- Securing funding for my open source projects
- None of the above

*Q58. (optional) Other challenges — please specify.*

---

## Section 6 — Feedback

*Q70. (optional) Is there anything important we missed, or anything you'd like to clarify?*

---

## Closing (end-of-survey message)

> Thank you for completing the survey. If you'd like to hear about the results, email **[CONTACT NAME]** at **[CONTACT EMAIL]**.
