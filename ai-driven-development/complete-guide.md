# Complete Guide

{% hint style="info" %}
**Human Oversight**: While AI handles the bulk of the coding, human expertise remains essential. The engineering team or an individual is responsible to manage the CI/CD pipeline, deployment to production, and provides the architectural oversight necessary for a successful product. **The process is a collaboration, not a complete abstraction from human developers.**
{% endhint %}

{% stepper %}
{% step %}
### Ideate a Vision

* Brainstorm your Idea and Capture It
* You will not gain a complete dot connection at the beginning, You will eventually reach that place while building it and iterating over it. Hence take notes and capture everything that you can possibly think about it. A vague description, a curious venture or anything.
{% endstep %}

{% step %}
### Draft a PRD

* Using the Vision Raw Document you'll create a Products Requirement Docs which outlines the complete application architecture with a technical writing agent.
* You'll need to use a systematic method like BMAD (Breakthrough Method for Agile Development) to create sub agents with roles who will help you create a complete picture of first phase of your MVP development.
* **VERIFY:** You'll verify the completeness of the PRD using another specialised agent whose task is to identify gaps and find out potential areas of improvement.&#x20;
* The idea is to using one AI to create the initial PRD and then feeding it to another AI to get a report on its clarity and completeness. This iterative refinement ensures the requirements are solid before development begins.
{% endstep %}

{% step %}
### Tasks Breakdown

* Once the PRD is finalized, AI tools are used to break the project down into smaller, manageable tasks and sub-tasks.&#x20;
* You'll use a tool called TaskMaster, which can analyze a PRD, break it into a task hierarchy, and even evaluate the difficulty and dependencies of each task
*   Use your AI assistant to:

    * Parse requirements: `Can you parse my PRD at scripts/prd.txt?`
    * Plan next step: `What's the next task I should work on?`
    * Implement a task: `Can you help me implement task 3?`
    * View multiple tasks: `Can you show me tasks 1, 3, and 5?`
    * Expand a task: `Can you help me expand task 4?`

    Details: [task-breakdown.md](task-breakdown.md "mention")
{% endstep %}

{% step %}
### Iterative Development

**IMPLEMENTATION:** Step by Step Feature Implementation with a verify then proceed analogy.

**CHECKPOINTS (VERSION CONTROL):**&#x20;

* BRANCH: For Separation of Concerns and use them to later merge into master/main after testing of feature implementation.
* COMMITS: As a milestone or checkpoint to rollback if things go wrong.

Details:[version-control.md](../software-development/version-control.md "mention")

**VERIFICATION:** At each step of Iterative Development

1. **Code Formatter**
2. **Code Lint Checker**
3. **Build Verifier**

**AI MEMORY LAYER:** A significant challenge in large, multi-session AI projects is the model's limited context memory. we shall overcame this by:

* Using a "context handover" feature that automatically passes knowledge to a new thread when the context limit is reached. Eg: Manus AI
* Actively saving crucial information to the AI's "memories" or knowledge base.
* Having the AI **write its own documentation**. When the AI struggled with a specific feature, like a custom API, we'll have it document the solution and save it to a file. The AI could then be directed to read this file to refresh its memory, significantly improving consistency.
{% endstep %}

{% step %}
### Testing


{% endstep %}

{% step %}
### Deployment


{% endstep %}
{% endstepper %}
