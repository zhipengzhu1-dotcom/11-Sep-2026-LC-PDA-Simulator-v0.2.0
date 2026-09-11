# Running the simulator

Install [uv](https://docs.astral.sh/uv/), then use a terminal:

```bash
git clone https://github.com/zhipengzhu1-dotcom/11-Sep-2026-LC-PDA-Simulator-v0.2.0.git hplcsim
cd hplcsim
uv run --locked --python 3.12 --extra app streamlit run streamlit_app.py
```

If you downloaded a ZIP, extract it and open a terminal in the extracted folder
instead of cloning. Open <http://localhost:8501>. Leave the terminal running; press
**Ctrl+C** there to stop this server. Repeat the launch command to start it again.
On the first launch, press Enter to skip Streamlit's email prompt, or append
`--server.headless true` to suppress it and open the URL yourself.

Load [the example session](../examples/README.md) for a first prediction.

## Troubleshooting

- **Missing Streamlit, pandas, or Plotly:** include `--extra app` in the command.
- **Port already in use:** append `--server.port 8765` and open
  <http://localhost:8765> instead.
- **Connecting forever:** check that the terminal server is still running.
- **Import errors after updating code:** stop this server with Ctrl+C and restart it
  so imported modules are refreshed.
- **Unexpected UI version:** run `git describe --tags --always` and
  `git status --short --branch`. Use the `v0.2.1` tag to reproduce this public release.

Stop the server before changing branches or updating code. Prototype branches under
`prototype/*` are historical experiments; their branch READMEs explain their own
setup. They are not needed for the released app.

## Development checks

See [CONTRIBUTING.md](../CONTRIBUTING.md) for the full suite. Changes to pinned rows
also require a browser check. Start a dedicated server in one terminal:

```bash
uv run --locked --extra app streamlit run streamlit_app.py --server.headless true --server.port 8767
```

In another terminal at the repository root:

```bash
uv run --with playwright playwright install chromium
uv run --with playwright python scripts/check_sticky_rows.py --port 8767
```

Stop the dedicated server with Ctrl+C when finished. This measures layout in a real
browser; Streamlit AppTest does not exercise scrolling.
