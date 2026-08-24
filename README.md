# Unitovo AI Calculator Methodology

[Unitovo](https://unitovo.online/) is a free, privacy-first collection of browser-based calculators, converters and developer tools. No signup is required and calculator inputs stay in the browser.

## AI tools

- [AI API Cost Calculator](https://unitovo.online/tools/ai-api-cost-calculator/) — compare current input, cached-input and output pricing across OpenAI, Anthropic, Google, Mistral and DeepSeek.
- [ChatGPT Token Calculator](https://unitovo.online/tools/chatgpt-token-calculator/) — estimate prompt tokens, context usage and API cost.
- [GPU VRAM Calculator](https://unitovo.online/tools/gpu-vram-calculator/) — estimate weights, KV cache, activations and runtime memory.
- [Ollama VRAM Calculator](https://unitovo.online/tools/ollama-vram-calculator/) — plan quantized local LLM deployments.

## Cost formula

`total cost = input tokens / 1M × input rate + cached tokens / 1M × cached rate + output tokens / 1M × output rate`

Request volume, billing days and batch-processing assumptions are applied after the per-request cost is calculated.

## VRAM methodology

The VRAM estimator separates:

1. packed model weights;
2. KV cache from layers, hidden size, context length and concurrent sequences;
3. activation and runtime allowances;
4. workload multipliers for inference, LoRA, QLoRA and full fine-tuning.

Results are planning estimates. GQA, MLA, mixture-of-experts routing, framework kernels, memory fragmentation and CPU offload can change real usage.

## Pricing sources

Pricing was last reviewed on 24 August 2026.

- [OpenAI API pricing](https://platform.openai.com/pricing)
- [Anthropic pricing](https://docs.anthropic.com/en/docs/about-claude/pricing)
- [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing)
- [Mistral API pricing](https://docs.mistral.ai/inference/pricing)
- [DeepSeek pricing](https://api-docs.deepseek.com/quick_start/pricing/)

## Feedback

Corrections to pricing data, architecture-specific VRAM assumptions and reproducible test results are welcome through GitHub Issues.

## Disclaimer

Unitovo is independent and is not affiliated with the model providers listed above. Verify current provider pricing before making a purchase or capacity commitment.
