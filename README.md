# AgentLink console

A minimal black & white web console for the owner's self-hosted agent
workbench. Static page (GitHub Pages) backed by Firebase Realtime
Database: messages, file uploads, live CLI activity and result files
travel through the `/agentlink` subtree, where a relay daemon on the
workbench VM picks them up and runs the agent.

Sign-in uses a dedicated Firebase Auth account for this page. The
Firebase web config embedded in `index.html` is a public client
identifier (same project as the Muse Chat room), not a secret.
