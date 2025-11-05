# Causal-Tracing-Demo

A ComfyUI reproduction of Causal Tracing, introduced in the paper [“Locating and Editing Factual Associations in GPT” (Meng et al., 2023)](https://arxiv.org/abs/2202.05262).

![workflow](./workflow/workflow_highresolution_meta.png)

[Download Workflow](./workflow/workflow.json)

## Requirements

-   [ComfyUI](https://github.com/comfyanonymous/ComfyUI): The node-based Pythonic system.

-   [ComfyUI-Notebook](https://github.com/liusida/ComfyUI-Notebook): A custom node that implements the Notebook Cell.

## Example Results

The model [Qwen3-0.6B](https://huggingface.co/Qwen/Qwen3-0.6B) with the prompt _"Michael Jordan is one of the greatest players in the game of"_:

![plot](./workflow/heatmap.png)

(Tip: you can drag the heatmap image directly to ComfyUI to load the workflow.)

## What is Causal Tracing

According to the paper [“Locating and Editing Factual Associations in GPT” (Meng et al., 2023)](https://arxiv.org/abs/2202.05262):

Causal Tracing is a method to find which parts of a language model recall a specific fact.
The process involves:

1. Running the model normally with the correct input, and again with a corrupted version (where the subject is set to noise).

2. Then, selectively restoring individual hidden activations to their clean state.

3. If restoring a specific activation fixes the output probability, that activation is causally responsible for recalling the fact.

## My Interpretation

Since the subject is replaced with noise in the corrupted version, the activations that restore the correct output probability can be thought of as carrying information about the subject — not necessarily the entire factual association (i.e., the relationship between the subject and the object).

I see Causal Tracing as analogous to [angiography](https://en.wikipedia.org/wiki/Angiography) in medicine: it reveals how the “information flow” of the subject moves through the model’s activations during a normal run.

The early site reflects the aggregation of information about the subject toward the last token of the phrase. (e.g. "Michael Jordan" -> "Jordan", or "The Space Needle" -> "le", right before the early site.)

I'm still trying to understand the MLP-recall aspect of the early site.

## Differences from the Original Paper

This implementation differs from the original paper in several ways:

1. **Corruption Method**: Instead of adding Gaussian noise of 3 times its std deviation, we simply replace all subject activations with noise.

2. **Indirect Effect(IE)**: Instead of using IE ($P_{final} - P_{corrupted}$), we simply use $P_{final}$.

3. **MLP recall**: I haven't implemented the "severed MLP" experiment.
