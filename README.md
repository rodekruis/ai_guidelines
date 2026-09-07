# Guidelines for using AI at the Netherlands Red Cross

## General Netherlands Red Cross guidelines

The official [(Dutch language) guidelines for AI usage within the Netherlands Red Cross](https://kruispunt.rodekruis.nl/kenniscentrum/informatievoorziening-ict/ai-co-pilot?status=all).

## AI usage guidelines for people that work with AI from a technical standpoint

The general AI usage guidelines are general. There's also a group of people within the Netherlands Red Cross that
uses AI in quite specific ways: software developers, data scientists, system administrators etcetera. This addendum to the general guidelines exists to guide their behaviour, address their concerns and questions.

### Responsible AI Guide

The [Responsible AI Guide](https://responsibleai.guide) is a framework/guide built in collaboration by the Humanitarian OpenStreetMap Team and the 510 Team of the Netherlands Red Cross. All Netherlands Red Cross employees that work with AI from a software development standpoint should familiarize themselves with the contents of this framework.

### AI Disclaimer

When using AI to help write software, please include a disclaimer with the source code. For an example see [this example AI Disclaimer](ai_disclaimer.md).

## Tools

The preferred solutions to use AI are the Claude app for office work and Github Copilot for software development / data / cloud management. Here are some tips and tricks to use them effectively.

### Inspecting GitHub Copilot usage

When using GitHub Copilot, usage can be inspected by going to the [`rodekruis` org Settings → Billing and licensing → AI Usage](https://github.com/organizations/rodekruis/settings/billing/ai_usage?period=3&group=8&customer=1191460&chart_selection=2&view=models). You need to be an owner of the GitHub organization to see it.

### Self-Hosted Models (Azure Foundry)

In Github Copilot it is possible to use models that we self-host or self-manage through Azure Foundry. This ensures an extra level of data protection, because no third-party AI provider ever processes the data, and is **the preferred solutions when using AI on external infrastructure (e.g. a VM hosted by another NS)**. To configure this in VSCode, click `Ctrl+Shift+P` > `Chat: Manage Language Models` > `Open Language Models (JSON)` (top-right page icon) then configure it as shown [here](chatLanguageModels.json).

## How to use AI

For some basic advice on how to use AI for coding see: [How to use AI](how_to_use_ai.md).

## Checklist for teams and projects

For teams and projects there's a [checklist you can follow](./checklist.md).
