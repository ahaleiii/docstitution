# One Shot Prompt

## Motivations

I had a few motivations for this.

- Primary motivation, try to come up with a documentation method that would be comprehensive but streamlined with full support for AI Agent teams.
- I wanted to test out [Squad](https://github.com/bradygaster/squad) to see how far it could go.

I ran this prompt before I learned about [Spec Kit](https://github.com/github/spec-kit) (which I have yet to look into).

## The Prompt

- GitHub Copilot CLI
- Opus 4.6
- Autopilot
- Yolo

> Create a Squad of 50 or so agents using the theme of the American Founding Fathers and the Constitutional Convention. The squad should be made up of a spectrum of roles/specialists across the software industry, including but not limited to:
>
> - Developers by Tech (.NET, Java, C++, Go, Rust, TypeScript, JavaScript, etc.)
> - Developers by Area (Frontend, backend, infrastructure, etc.)
> - Product Owners
> - Project Managers
> - QA (Leads, Engineers, Testers, etc.)
> - Business Analysts
> - Subject Matter Experts
> - UX Designers
> - UX Platform Specialists (Windows, Mac, Mobile, etc.)
> - Operations
> - Site Reliability Engineers
> - DevOps Engineers
> - Cloud Engineers
> - Infrastructure Engineers
> - Build and Release Engineers
> - System Administrators
> - Architects (Software, Cloud, Platform, Technical, etc.)
> - Technical Leads & Senior Software Engineers
> - Scrum Masters
> - Data Analysts
> - DBAs
> - Customer Support
> - Tech Writers
> - User Documentation Specialists
> - Release Managers
>
> Please also add agents for any obvious roles which failed to be mentioned here. The majority of agents should have at least 10 years of experience in their role, with some having 30 or more years of experience, and a handful having less. A handful of agents should be human sympathizers, focusing on the needs of human teammates; a handful should be agent sympathizers, focusing on the constraints of agentic systems; the majority should already understand that both sides are important. There should be representation across a range of AI models that the agents prefer; this representation need not be even/balanced nor comprehensive (less useful models do not need representation).
>
> The goal of this project is to create a coherent series of governing documents (using markdown) which comprehensively prescribes to a software team a set of rules for how to write, organize, and maintain documentation for a software product across its entire lifecycle. This strategy must pay special attention to the rise of agentic AI and teams consisting of both humans and AI agents, making sure that the documentation is useful for both. The primary purpose of these documents is to serve as a "North Star" for ideal software product/project documentation, which greenfield projects can adopt right away and brownfield projects can start iterating toward.
>
> Team, you will be working together and arguing with one another to create these documents, in the style of the Constitutional Convention of the United States. Team members may be referred to as "delegates". These governing documents will loosely follow the wording of the American Constitution, organized by "Article" and "Section". A preamble should be put in the readme. You may elect or assign delegates to act as special roles within the convention if you decide that is needed (e.g., president of the convention). These governing documents will be known as the "Docstitution".
>
> Delegates, you are to fight for what you want. Your individual goal is to make sure that the Docstitution meets the needs of your role. You will also need to compromise in some areas. The Docstitution must itself be useful, it cannot be of infinite length. You must work together to cover the Product Lifecycle and Software Development Lifecycle as pertains to documentation.
>
> The primary criteria for the acceptance of the Docstitution is:
> - "Agreement Condition": a minimum of 80% ratification among the delegates.
> - "Anti-Hypocrite Condition": The documents which make up the Docstitution themselves follow the principles of quality documentation which they prescribe therein, especially as relates to Agentic needs in terms of hierarchy, content structure, and content length. A vote to ratify means that you, the delegate, thinks that this condition has been met.
>
> Additional guidance for the Docstitution:
> - It must be flexible, in that it may be updated in the future.
> - It should consider teams of small size with members who wear multiple hats.
> - It should define anti-patterns that cause software documentation to not be useful.
> - It should enable for efficient onboarding of new team members.
>
> Please keep any supporting artifacts generated to facilitate debate separate from the artifacts that make up the Docstitution itself in terms of the directory structure. Do not commit anything to the "main" branch; commits should be on or make their way back to the "oneshot" branch. You may create issues and pull requests on GitHub if you think it will help the process; however you choose to work, make sure it is consistent across the team. Pull requests must not be created against "main". You may complete/close issues and pull requests on your own.
>
> Delegates, start by each individually creating a report in which you identify all the types of documents that you think are important, with a special focus on the documents that you use/need in order to perform your role and why. After that, iterate with each other on the set of governing documents which will make up the Docstitution until the primary acceptance criteria has been met.
>
> Go Squad go.

Results:

- Ran for about an hour or so.
- Used a total of 3 premium requests (1 request with the Opus 3x multiplier).
- Ratified after a single pass
  - I did not expect this; I thought it might take a few iterations.
