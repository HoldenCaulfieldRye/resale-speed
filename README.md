# Shopping Therapy

Resale advisor chat over Poshmark sell-through data, with the original report under **Stats**.
Live: https://holdencaulfieldrye.github.io/resale-speed/

The page runs the data tools in the browser; `worker/` is a Cloudflare Worker that holds the Anthropic key and pins the model, system prompt and tools.

Deploy the worker:

```bash
cd worker
npx wrangler login
npx wrangler secret put ANTHROPIC_API_KEY
npx wrangler deploy
```

Then set `PROXY` in `index.html` to the printed `*.workers.dev` URL. Test locally with `?proxy=<url>`.
