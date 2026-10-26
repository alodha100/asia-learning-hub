# Asia Learning Hub
This repo stores the reusable assets for continuous learning, knowledge sharing, and professional growth across the Asia MTT community.

How we are supposed to create the agents

Build the use case in Copilot Studio

The deliverable is a Copilot Studio Agent use case.

Before building, read Section 6.5 of the V-team / Industry Readiness page

Ning Wei specifically asked everyone to follow Section 6.5, the Copilot Studio Agent Guideline, before starting.

Put the Agent artifacts into a Power Apps Solution

This is important. They do not want every MTT to manually recreate the agent.
The agent artifacts should be packaged in a solution and then exported so other MTTs can import that solution into their demo environment.

Follow the defined Solution naming convention

Ning Wei explicitly mentioned that the defined naming convention must be followed to prevent naming conflicts during import.

The deliverable needs peer verification

The team is expected to use pairing/peer verification so that what goes into the repository actually works. Ning Wei specifically called out validating that the README demo prompts work with the accompanying data and asked for pairing to test deliverables.

Final reusable artifacts go into the GitHub repository

Ning Wei shared the repo containing the reusable industry use cases and reminded people to provide their GitHub account if they need access.
So think of the flow like this

Industry use case → Build Copilot Studio Agent → Put agent into Power Apps Solution → Peer-test/verify → Export Solution → Add reusable package/documentation to GitHub → Other MTTs import rather than rebuild

One additional point: the chat says the PL-7008 Copilot Studio use case should now be planned around the new GitHub Copilot Harness MOC.

So if you're about to build your industry agent, I would not start by creating an agent from scratch yet. The most important thing is to first check Section 6.5, because that contains the team's prescribed guideline and naming convention. The chat itself doesn't expose the exact naming convention.

=============================== ======================

Package the Copilot Studio agent artifacts inside a solution and export it, so other MTTs can import the solution instead of recreating the agent.
More specifically, the deliverable is a Power Apps solution export, intended for importing into an MTT demo tenant.
Follow the defined solution naming convention to prevent naming conflicts when people import solutions. The search results, however, do not expose the actual naming format, so I can't accurately give you that string yet.
The deliverable must be tested/verified. Ning Wei says the README demo-step prompts must work with the accompanying data, and each team should use pairing to test the deliverables.
Team leads should ensure members are paired and all deliverables are verified.
Ning Wei also says Sections 6.2 through 6.5 should be followed together to maintain consistency and avoid rework.
In practical terms

Build Agent → include artifacts in Power Apps Solution → use prescribed solution naming → export solution → peer tests it → verify README prompts against accompanying data → commit reusable deliverables to repo.

One important correction to my previous answer: I cannot yet give you the exact naming convention or claim a complete exact summary of Section 6.5, because the search is finding Ning Wei's references to Section 6.5 rather than returning the actual notebook section itself.
