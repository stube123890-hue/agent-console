# AgentLink console

A minimal black & white web console for the owner's self-hosted agent.
Static page (GitHub Pages) that talks **directly to the OpenCode agent
over its ngrok tunnel** — no Firebase, no accounts, no relay.

- Agent endpoint: `https://douglas-unflawed-doyle.ngrok-free.dev`
  (ngrok static domain → Kaggle notebook → OpenCode serve → llama.cpp
  running Magistral-Small-2506-abliterated).
- Chat flow: `POST /session` once per tab, then blocking
  `POST /session/:id/message`; reasoning and tool activity stream in
  via history polling while a run is live; the header lamps track
  `/session/status`.
- The agent sleeps with the Kaggle session — if the lamps are red,
  re-run the `agent-rebuild` notebook to wake it.
- Chat lives in the browser tab only; Clear chat wipes the tab view.
- The previous Firebase build is preserved at
  `console-index-backup-firebase.html` in the rebuild folder.
