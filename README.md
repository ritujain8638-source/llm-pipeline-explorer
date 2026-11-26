# LLM Pipeline Explorer

A single-file, zero-build interactive web application for visually exploring how Large Language Models (LLMs) process a prompt and generate the next token — step by step, directly in the browser.

**Live Demo:** https://llm-pipeline-explorer-eta-five.vercel.app/

## Interactive Pipeline Stages

Enter any custom prompt or choose from the built-in presets, then step forward/backward or auto-play through all six stages:

1. **Raw Input Text** — Inspects the raw prompt entering the pipeline.
2. **Tokenization (Text to Pieces & IDs)** — Edit training sentences, rebuild the vocabulary, and inspect color-coded token chips and IDs (breaking unknown words into `##` subword/character pieces) with token and character statistics.
3. **Embeddings (Spelling vs. Meaning in 3D)** — Switch between instant 64-dimensional spelling-based vectors and 384-dimensional neural meaning-based embeddings (`Xenova/all-MiniLM-L6-v2` via Transformers.js), projected into an interactive 3D Plotly scatter plot with top-5 cosine similarity pairs and a 3D coordinates table.
4. **Self-Attention (Connecting Context)** — Click any token to visualize attention weights connecting it back to earlier tokens in the prompt.
5. **Next-Token Probabilities** — Adjust the **Temperature** slider (`0.2`–`1.5`) in real time to see how sampling creativity reshapes candidate token scores and probabilities.
6. **Picking & Appending the Next Token** — Inspect the sampled next token and probability readout, resample, or append tokens to continue generating text.

## Tech Stack

- **Single-file HTML / CSS / JavaScript** — Vanilla frontend with no build step required
- **[Plotly.js](https://plotly.com/javascript/)** — Interactive 3D embedding scatter visualization
- **[Transformers.js](https://huggingface.co/docs/transformers.js)** (`Xenova/all-MiniLM-L6-v2`) — In-browser neural sentence embeddings

## Run Locally

```bash
git clone https://github.com/ritujain8638-source/llm-pipeline-explorer.git
cd llm-pipeline-explorer
```

Open `index.html` directly in any modern browser (or serve it locally with `python3 -m http.server`).
