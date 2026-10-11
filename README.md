# Sagar Mishra

Software engineer in Melbourne. I got into inventory software by losing stock.

I used to run a small anime-apparel business. Stock kept going missing because I counted quantities instead of recording each movement. I didn't know that was the difference until it had happened a few times. Nexus, Aroma and now e-warehouse all come out of that.

At work I spent two years at Programiz, a coding-education platform with over 100,000 paid learners, and led four engineers at Jobss.ai. Outside work I'm learning to build with agents in Claude Code.

I'm looking for a permanent software engineer role, full-stack, backend or frontend. I have full working rights in Australia.

---

## Right now

### e-warehouse

A minimal rebuild of Nexus, my warehouse platform, for clothing. TypeScript, Express and PostgreSQL. Private for now.

It starts from age-based items, so every item in stock carries its age. Clothes have no expiry date printed on them, but they still go stale. So I'm working out a market-level expiry date. That means building a timeline of each product's life, with evidence attached to every date on it. Pricing by how much shelf life an item has left comes after that.

Adding a product and counting stock is the easy part, and plenty of warehouse tools already do it well. Most of my time on e-warehouse goes into spikes and rough workflows, not code. It might be a real idea, or it might be me overthinking. The spikes will tell me.

### Agent skills

I write my own agent skills and keep updating them as my workflow changes. The repo is private until the skills are mature enough to share.

---

## How I build with agents

I use Claude Code on my newer projects. I built Nexus and Aroma before I worked this way, with a team of three that I led.

Two things I've learnt so far.

**Write the spec before the prompt.** I write the spike, the reference implementation and the open questions myself. The agent plans and builds against that. I still write some of the code, and I review everything an agent writes before it merges. Each project has a brainstorms folder where I journal the problem in numbered files. Before anything gets built, I have the agent read them and grill me.

**One task at a time.** I run Claude Code with herdr and Kun Chen's [firstmate](https://github.com/kunchenguid/firstmate), where you talk to one agent and it hands work to the rest. Once I had several subagents running in parallel across terminal panels, I kept losing track of which panel was doing what. So I wrote kaizen, a skill that keeps an agent on one task at a time. The name comes from kaizen, which is where I learnt that rule.

I'm still early at this.

---

## Things I've built

### Nexus

Warehouse platform for clothing stock. I led a team of three and reviewed over 400 pull requests across Nexus and Aroma.

- Stock is a labelled tree, so every item resolves to one location and traces back to its lot.
- Every stock movement goes into a PostgreSQL ledger. A reservation takes a row lock, so two buyers can't claim the same unit.
- Product drops run as a state machine, from supplier onboarding through lot negotiation, intake and pricing.
- Refunds and exchanges resolve back to the right lot.

Not launched. `TypeScript` `Node.js` `PostgreSQL` `Redis` `Next.js`

### Aroma

A multi-tenant storefront that runs on Nexus. A lot of clothing sellers in developing markets sell only through social media. Prices change from post to post, buyers can't see stock, and someone who has paid can't check their order.

- Each seller gets an isolated storefront on one shared backend.
- Checkout reserves stock once the buyer confirms the order. An idempotency key stops a retry from creating a second order.
- Payments run as their own service, with eSewa and Khalti behind one interface.
- Orders reach Nexus through a shared Redis instance.
- Lighthouse put largest contentful paint on the product page under 2 seconds.

Not launched. `TypeScript` `Node.js` `PostgreSQL` `Redis` `Next.js`

Both repos are private. I'm happy to walk through the code on a call.

### Programiz

Two years on a coding-education platform with over 100,000 paid learners. Commercial, closed source.

- Built the course flow APIs in Node.js, TypeScript and MySQL.
- Built the Paddle payment integration, webhooks included. Programiz still takes payment through it.
- Built the certificate engine, which has issued over 100,000 completion certificates.
- Integrated sensAI, an LLM-backed tutor, into the exercise page. Learners ask it around 300 questions a day.
- Fixed the online compiler with the principal engineer. Python output arrived over the socket in pieces, and a heartbeat now joins it into one response.
- Led a team of six on Programiz Reports, from requirements to release in two weeks.

### Jobss.ai

Led four engineers on a live job and task platform built in Laravel. I owned authentication and role-based access for its four roles: job poster, job seeker, task poster and task seeker.

### Also

- A website for a Melbourne rubbish removal business, live at [melbournecheaprubbishremoval.com.au](https://melbournecheaprubbishremoval.com.au).
- An Android app in Kotlin that matches futsal players with venues and opponents. It runs on MongoDB.

---

## What I work with

| | |
|---|---|
| Languages | TypeScript, JavaScript, Python, PHP, Java, Kotlin, SQL |
| Frontend | React, Next.js, React Query, Zustand, Tailwind CSS |
| Backend | Node.js, Express, Django, Laravel |
| Data | PostgreSQL, MySQL, Redis, MongoDB |
| Testing and CI | Playwright, Cypress, Selenium, Postman, GitHub Actions |
| Agents | Claude Code, herdr, firstmate, agent skills |

I'm strongest in TypeScript, React, Node and PostgreSQL.

---

## Get in touch

[sagarcrcoc@gmail.com](mailto:sagarcrcoc@gmail.com) · [LinkedIn](https://www.linkedin.com/in/sagar-mishra-a3455121b/) · [Website](https://sagarmsraozil.github.io/) · [X](https://x.com/SagarMi31569172/)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/sagarmsraozil/sagarmsraozil/output/github-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/sagarmsraozil/sagarmsraozil/output/github-snake.svg">
  <img alt="contribution snake animation" src="https://raw.githubusercontent.com/sagarmsraozil/sagarmsraozil/output/github-snake.svg">
</picture>
