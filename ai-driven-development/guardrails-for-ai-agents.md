# Guardrails for AI Agents

{% hint style="info" %}
### Key Highlights <a href="#key-highlights" id="key-highlights"></a>

### **The Four Levels of AI Coding Autonomy**

Shatokhin explains why most AI coding projects fail by outlining four levels of autonomy:

* **L0**: Fully manual (humans do all work)
* **L1**: Human assisted (basic copilot features, copy-paste from ChatGPT)
* **L2**: Human monitored ("vibe coding" - AI handles most tasks, humans watch for issues)
* **L3**: Human out of the loop (agentic coding - AI handles everything, humans only review PRs)

The main problem: **People skip L0-L2 and jump straight to L3**, creating unmaintainable&#x20;
{% endhint %}

## **The Production AI Coding Workflow**

5-step methodology:

{% stepper %}
{% step %}
**Plan the Architecture**

* PRD (Product Requirements Document)
  * Project structure
* ADR (Architecture Decision Records)
  * Workflow documentation
{% endstep %}

{% step %}
**Create the Types**

**Types: The Second Most Valuable Technique**

"Types make your agents way more reliable because they add an anchor to the model. So if the agent has defined all the types for the feature correctly, including request types, response types, component, and database types, there's actually very little room for this agent to hallucinate and make a mistake."

**The Linting Connection**

Types work effectively because "almost all coding tools actually run linters after the agent runs a certain tool. So if there is a mistake, the agent is going to see it and this is exactly what increases the reliability so much."

**Specific Types to Define**

You must define:

* **Request types** - For API inputs
* **Response types** - For API outputs
* **Component types** - For frontend components
* **Database types** - For data models
{% endstep %}

{% step %}
**Generate the Tests**&#x20;

**The Context Loss Problem**

* "Most of the issues when you're coding with AI come from the fact that AI simply loses the necessary context in order to complete it reliably."
* "if your feature is really complex, the conversation history for that feature is obviously going to grow very large. And then all of the coding assistants like cursor or cloud code typically removes some of the messages in the middle or in the beginning and so then AI forgets certain details and introduces a bug."

**The Solution: Test-First Development**

"However, if you tell AI to write a test first when it still has all of the necessary context for that feature, then later it literally can't even fool itself because it's going to run the test and it's going to see that something is not right, especially if you've previously also defined the types."

**Integration Tests vs Unit Tests**

"So the difference between unit tests and the integration test is that integration tests are actually calling the real APIs rather than just using the mock data. And I personally prefer to always run integration tests until the functionality is completed. And then after the functionality is completed you can replace the integration test with the unit test."

**Testing Review Strategy**

"So also obviously when you're working with so many agents you can't review all of the changes. So what I recommend doing is actually reviewing only the tests."

"If the test is correct, then there is very little chance that AI can actually screw up the functionality. Tests do not eliminate the possibility of all the bugs in your codebase, but they definitely verify that the feature is at least working."

**Closing the Feedback Loop**

"Make sure you tell your AI to run the test. Do not run the test yourself because this essentially going to allow you to close the feedback loop. Meaning that you don't have to pass the errors back and forth between the terminal and your coding assistant. You simply tell an agent to run a test and then it's going to run it and if there are any issues it's going to see them and then it's just going to keep working until the test is passing."
{% endstep %}

{% step %}
**Build the Feature**

&#x20;With proper architecture, types, and tests, AI can run multiple agents in parallel
{% endstep %}

{% step %}
**Document the Changes**

Update ADR with key architectural decisions for future agent
{% endstep %}
{% endstepper %}

### **Best Practices and Tips**

**Information Dense Keywords**: Use clear commands like "create," "update," "delete," "add," "remove" instead of vague prompts.

**Model Selection**:

* GPT-4o1: Quick edits
* GPT-o5: Complex features and code analysis
* Claude Sonnet: General coding workflows (his preferred model)
* Claude Opus: One-shot features with background agents

**Context Management**: Always consider what your AI can and cannot see - not enough context or too much context causes hallucinations.

### **Common Production Disasters**&#x20;

1. **Database Deletion**: The Replit disaster where Simon Sherwood's production database was deleted
   * **Solution**: Use staging environments, never connect AI to production databases
2. **Accept All Trap**: 20% of AI code recommends non-existing libraries, only 55% passes security tests
   * **Solution**: Use modern tech stacks with simplified security (Firebase, Supabase)
3. **Technical Debt Explosion**: Stanford study showed only 15-20% net productivity gain despite 30-40% more code
   * **Solution**: "No broken windows" rule - fix issues immediately

### **Key Takeaways**

"When you define these three things first, the types, the tests, and the architecture, you essentially built a railroad for AI to complete this feature reliably. When you've done these three things, AI literally cannot go sideways. There is simply no way that AI can fail if these three things are correct."
