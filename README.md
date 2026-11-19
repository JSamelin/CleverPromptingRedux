# JupyterLite Demo

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://jupyterlite.github.io/demo)

JupyterLite deployed as a static site to GitHub Pages, for demo purposes.

## ✨ Try it in your browser ✨

➡️ **https://jupyterlite.github.io/demo**

![github-pages](https://user-images.githubusercontent.com/591645/120649478-18258400-c47d-11eb-80e5-185e52ff2702.gif)

## Requirements

JupyterLite is being tested against modern web browsers:

- Firefox 90+
- Chromium 89+

## Deploy your JupyterLite website on GitHub Pages

Check out the guide on the JupyterLite documentation: https://jupyterlite.readthedocs.io/en/latest/quickstart/deploy.html

## Further Information and Updates

For more info, keep an eye on the JupyterLite documentation:

- How-to Guides: https://jupyterlite.readthedocs.io/en/latest/howto/index.html
- Reference: https://jupyterlite.readthedocs.io/en/latest/reference/index.html

This template provides the Pyodide kernel (`jupyterlite-pyodide-kernel`), the JavaScript kernel (`jupyterlite-javascript-kernel`), and the p5 kernel (`jupyterlite-p5-kernel`), along with other
optional utilities and extensions to make the JupyterLite experience more enjoyable. See the
[`requirements.txt` file](requirements.txt) for a list of all the dependencies provided.

For a template based on the Xeus kernel, see the [`jupyterlite/xeus-python-demo` repository](https://github.com/jupyterlite/xeus-python-demo)

## Prompting Workshop

Follow the notebooks in order:

1. [Basic API Calls](content/01_basic_calls.ipynb)
2. [LLM Judges](content/02_llm_judges.ipynb)
3. [Self-Consistency](content/03_self_consistency.ipynb)
4. [Token Probability](content/04_token_probability.ipynb)
5. [System Prompt](content/05_system_prompt.ipynb)
6. [Exercise: Entity Sentiment](content/06_entity_sentiment.ipynb)
7. [Exercise: Sentiment Uncertainty](content/07_sentiment_uncertainty.ipynb)
8. [Function Calling](content/08_function_calling.ipynb)

### Entity-Sentiment Exercises

For local execution, install the repository dependencies with `python -m pip install -r requirements.txt`, start Jupyter from this repository, and select a Python kernel in that environment. The two exercises use `openai`, `pydantic>=2`, and (for Notebook 07) `tiktoken`. Each notebook includes its own imports, configuration, article loading, and API scaffolding, so it can run from a fresh kernel. Set the `OPENAI_API_KEY` environment variable or fill in the notebook's `API_KEY` placeholder. The exercises default to `gpt-4.1`, which supports the structured outputs, log probabilities, and sampling settings used here.

The shared [fictional article](data/text/article.txt) is loaded automatically. Participants mainly edit the clearly marked `TODO` prompt cells and interpret the outputs. Notebook 07 freezes a reviewed list of 15 companies and performs exactly five parallel iterations. Each iteration samples an evidence assessment before scoring each company with verified single-token sentiment labels; one complete experiment makes 80 API requests. Missing alternative-label probabilities cause an explicit error rather than a misleading score.

The [complete instructor solution for both exercises](data/bin/06_07_entity_sentiment_solution.ipynb) includes finished prompts and result discussion. It runs from `data/bin/`, while the participant notebooks run from `content/`; all three also support a kernel started at the repository root. All three notebooks have been executed end to end against the OpenAI API from fresh local Python kernels, including both five-run experiments. Notebook outputs are cleared for distribution.

The JupyterLite build also copies the article into its served contents so that the participant notebooks use the same relative data path in the published site.
