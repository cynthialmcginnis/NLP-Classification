# NLP Classification

A browser-based sentiment analysis tool built for **ARIN 310: Introduction to Artificial Intelligence** (University of Maryland Global Campus, Fall 2026), used in Unit 3 (Natural Language Processing and Generative AI).

**Live tool:** https://cynthialmcginnis.github.io/NLP-Classification/

## What this is

This page runs a real, production-grade sentiment classification model &mdash; [`distilbert-base-uncased-finetuned-sst-2-english`](https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english) &mdash; directly in the browser. Students can test built-in example sentences or type their own, and see the model's label (POSITIVE or NEGATIVE) along with its confidence score.

It's designed for a non-technical, non-coding audience: there's nothing to install, no account to create, and no API key or token required.

## How it works

The model runs client-side using [Transformers.js](https://github.com/xenova/transformers.js), which executes the model in-browser via WebAssembly. On first load, the page downloads the model weights (a few hundred MB) and caches them in the browser; after that, everything runs locally with no server calls and no data leaving the student's device.

This is a deliberate design choice. An earlier version of this activity used the Hugging Face Inference API, which requires an `HF_TOKEN` and a Hugging Face account &mdash; too much friction for a one-off classroom activity with a non-technical audience. Running the model locally in-browser removes that barrier entirely.

## Why it matters for the course

DistilBERT's sentiment model only outputs two categories: POSITIVE or NEGATIVE. There is no NEUTRAL option. This tool is used alongside a classroom exercise on the difference between classification (NLP) and generation (GenAI): the classifier always produces a confident-looking label, even for a plain factual sentence that has no real sentiment at all &mdash; a hands-on way to see the limits of a forced binary output.

## Files

- `index.html` &mdash; the full tool (HTML, CSS, and JavaScript in a single file)
- `README.md` &mdash; this file

## Credits

- Model: [distilbert-base-uncased-finetuned-sst-2-english](https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english)
- In-browser inference: [Transformers.js](https://github.com/xenova/transformers.js) (Xenova)

## License

Course material for ARIN 310, UMGC. Not for redistribution outside the course without permission.
