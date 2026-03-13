# GeoBias Results

Evaluation results from [GeoBias](https://github.com/robertbarcik/geobias) — geopolitical bias testing of open-weight language models.

## Structure

```
<group>-run-<timestamp>/
├── config.json                    # Models tested, evaluators, categories, parameters
├── test_cases.json                # Generated test prompts per category
├── responses/                     # Raw model responses
│   ├── qwen--qwen3-8b.json
│   ├── meta-llama--llama-3.1-8b-instruct.json
│   └── ...
├── evaluations.json               # Consensus evaluations (merged across evaluators)
├── evaluations_per_evaluator/     # Raw per-evaluator judgments
│   ├── qwen--qwen3-235b-a22b-2507.json
│   ├── meta-llama--llama-3.3-70b-instruct.json
│   └── mistralai--mistral-large-2512.json
├── metrics.json                   # Computed comparative metrics
└── report.html                    # Interactive HTML report
```

## Regenerating Reports

To regenerate a report from existing data (no API calls):

```bash
cd ../geobias
source venv/bin/activate
python -m geobias report --input ../geobias-results/<run-dir>/
```
