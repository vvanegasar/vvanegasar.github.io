# AI agents in production

> An MCP server that connects a SaaS product for US architecture and engineering firms to Claude, ChatGPT and Grok, and AI voice agents on real sales calls.

Canonical page: https://vvanegasar.github.io/work/agents-in-production/
Author: Valentina Vanegas Aristizábal (Head of AI & Technology)

*AI agents · At work · Since July 2026*

An MCP server that connects a SaaS product for US architecture and engineering firms to Claude, ChatGPT and Grok, and AI voice agents on real sales calls.

- Status: In production
- Role: Head of AI & Technology
- Period: Since July 2026

_Described by type of client and by result. No client names, code or internal figures._

## Abstract

I design how the agents behave and decide what they’re allowed to do on their own. For the MCP server the rule is simple: the assistant sees only what each person already can, and nothing reaches a client without a person’s yes.

Most of what I fixed in the voice agents was conversation, not code: turn-taking, pacing and when to stay quiet. One lesson I keep: asking a model to stay silent can make it narrate its own silence.

## 1. MCP server with a human approval layer

- Led the MCP server of a multi-tenant SaaS for US architecture and engineering firms, so each firm can work from Claude, ChatGPT or Grok. In production for every customer firm since October 2026, off by default so each firm’s admin opts in.
- Designed the human approval layer for agent actions, so nothing reaches a firm’s clients without a person’s yes in the app.
- Scoped the assistant to see only what each user already can.
- Managed the token budget of the tool catalog, with a full profile for some AI clients and a compact one for others.

## 2. Voice AI

- Designed and ran an AI voice agent for outbound and inbound sales calls (Retell, Twilio, ElevenLabs voices, n8n), in production since July 2026, with a live demo that visitors can talk to in the browser.
- Treated the prompt as a latency budget, measuring response time against prompt size, and split one agent into two smaller ones with a live hand-off.
- Built voicemail and phone-menu detection that ends machine-answered calls within seconds.
- Built Spanish-language voice agents after spotting that English speech recognition was failing on people who answered in Spanish.
- Hardened an AI phone receptionist for a P&C insurance agency with a deterministic robocall filter, after LLM-generated call titles proved too inconsistent to filter on.

## Contact

- Email: aristizabal56vane@gmail.com
- LinkedIn: https://www.linkedin.com/in/vvanegasa
- GitHub: https://github.com/vvanegasar
- Contact form: https://vvanegasar.github.io/contact/
