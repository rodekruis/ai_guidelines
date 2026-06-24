# How to use AI

Using AI, specifically LLMs (Large Language Models), productively is a whole skill by itself. Both the models and products around the models have been changing quickly. This page lists some advice and further reading on AI.

## LLM terminology and usage

### Prompts

A prompt is basically an instruction to an LLM. This can be as simple a question as ["how many 'r' in strawberry?"](https://community.openai.com/t/incorrect-count-of-r-characters-in-the-word-strawberry/829618).

If you give a prompt with little information then the answer you will get can often be less specific than you want. You can give an LLM more context in various ways:

- the intended audience: "I'm an experienced TypeScript developer working in a Python codebase, I don't have a lot of experience with Python"
- the tech stack relevant to your question: "I'm building a web application using NestJS, Angular, PostgreSQL and Redis"
- telling it what _not_ to do: "don't suggest workarounds or ways to bend the rules, I want to solve the problem properly within the current constraints"
- ... and many more (use a search engine "LLM prompt best practices")

### Context/Context Window

An LLM's "context" is basically "the things it's currently keeping in it's head" while it's working. There's a limit to this context called the "context window". Technically it's the maximum number of tokens it can hold while working.

When you're having a conversation (prompt-reply-prompt-reply) or you're using an agent all of the previous input and output will be part of the context for the LLM. When an LLM stops being helpful try starting a new conversation or new agentic loop.

See [Wikipedia for the full explainer](https://en.wikipedia.org/wiki/Context_window).

### MCP - Model Context Protocol

Model Context Protocol is an open standard a lot of LLMs use to talk with external "tools". These external tools can be things like:

- reading/writing files
- viewing websites and searching the web
- GitHub and other version control websites
- browser devtools
- designer tools like Figma
- databases
- APIs
- ... and [many more](https://mcpmarket.com/leaderboards)

Agents (see below) can be instructed to use (or not use) specific MCP servers.

### Agent

An "Agent" (AI Agent, LLM Agent) is a system that pursues goals, most of them use LLMs. They can be instructed to pursue a specific goal in specific ways. They generally loop through steps like understanding the request, doing research and taking actions (via MCP). When they receive new input this is sent to back to the LLM which then evaluates whether the goal is attained and if not what a logical next step is.

When people say LLMs get "stuck in a loop" they're generally referring to agents repeating the same steps over and over again without progressing towards the stated goal.

https://www.ibm.com/think/topics/ai-agents

## Specific ways of working

This section will go into some tooling and best practices when it comes to working with LLMs. As the field is changeable this can get outdated soon.

### Custom instructions/configuration at different levels (user, repository, org)

It is possible to instruct an LLM with specific prompts before sending a prompt during a working session. This prevents you from having to repeatedly give the same context to an LLM.

An example of this is configuring the LLM (actually the system around the LLM) with the following "I'm an experienced TypeScript developer working in a Python codebase, I don't have a lot of experience with Python". Every conversation you start with the LLM will first get that prompt and then the prompt you provide in the moment.

There are different methods of doing this and there are various strategies.

#### User level custom instructions

Depending on the LLM and surrounding software you use (Claude Code, CoPilot etc) you can provide user level custom instructions. These instructions will/should be applied to all interactions with the LLM from that computer or user account. VS Code on macOS will read `$HOME/.copilot/copilot-instructions.md` for any user level custom instructions.

The custom instructions there should be specific to the _user_ of the computer, not specific to any project.

Some examples:

- state the skillset of the user, amount of experience with certain programming languages
- state whether the user prefers shorter answer or longer ones with more elaboration
- state whether the user prefers the LLM/agent to ask clarifying questions

#### Repository level custom instructions

When using an LLM/agent for coding it's very useful to add (git) repository level instructions to the repository. These will provide context to the LLM that's specific to the repository. These instructions can describe things like:

- the tech stack of the project: which libraries, which subsystems
- the architecture of the project
- where to find which part of the project
- how to run tests
- which tools to use for formatting and linting
- what needs to be true for a coding task to be "done"

The standards on how these repository level custom instructions are written are in flux. Some LLM providers will have their own standard but a relatively new standard is using a root level `AGENTS.md` file. See [AGENTS.md](https://agents.md/) for more information.

👨‍🚀👨‍🚀👨‍🚀👨‍🚀👨‍🚀👨‍🚀 For an example see 121

Another way of doing this is using "skills". Each skill gets its own Markdown file in the repository, usually all skills files live together in a folder. An LLM can inspect these skills and decide to or be instructed to use a specific skill or skills for certain tasks. See [AgentSkills.io](https://agentskills.io/) for a lot of examples.

#### Organization level configuration

? is org level custom instruction possible?

For certain AI products, like CoPilot, it's possible to configure an LLM organization wide. One example where this is helpful is in configuring the LLM from _not_ reading files with environment variables in them as this can be a potential security risk.

### Supplying images instead of text

\_stub

## Resources

- [Simon Willison's - How I Use LLMs and ChatGPT](https://simonwillison.net/series/using-llms/)
-
