---
title: "Advania Executive Summary Pipeline"
description: "A multi-agent pipeline that reads meeting transcripts and documents, then generates structured executive summaries via Microsoft Copilot Studio and Power Automate."
date: 2025-05-01
tags: ["Copilot Studio", "Power Automate", "Multi-agent AI", "Azure", "TypeScript"]
featured: true
---

## Overview

This project is my final thesis at Háskólinn í Reykjavík, developed in collaboration with Advania. The goal was to automate executive summary generation for business meetings, cutting the time employees spend on post-meeting documentation.

The system takes meeting recordings or transcripts as input and produces a structured, review-ready executive summary without manual effort.

## Architecture

The pipeline uses three cooperating agents, each responsible for a distinct stage:

1. **Transcript agent** - processes meeting recordings from Teams or Zoom and produces a clean, structured transcript.
2. **Analysis agent** - classifies the transcript into action items, decisions, and discussion topics.
3. **Summary agent** - composes the final executive summary using a configurable output template.

Coordination between agents runs on Power Automate flows. Each agent is implemented as a Microsoft Copilot Studio topic that calls an Azure OpenAI deployment. The user-facing interface is a Copilot Studio bot, so business users can trigger the pipeline and review output without touching any code.

## Technical details

- Power Automate handles flow orchestration and HTTP triggers between stages.
- Each agent calls a dedicated Azure OpenAI deployment (GPT-4o) with stage-specific system prompts.
- Output is posted to a SharePoint library and optionally sent by email to meeting participants.
- Custom connectors bridge the Copilot Studio environment to internal Advania APIs for identity and document access.

## Outcome

The pipeline reduces the average time to produce an executive summary from approximately 45 minutes (manual) to under 3 minutes. Tested across 20 real meeting recordings; accuracy was validated by the Advania project team.
