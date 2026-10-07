# APM incident triage — offline demo

Python 3.10+; standard library only. No installation or API key required.

```sh
python demo.py --self-test
python demo.py --output demo_output.json
```

Read APM_Triage_Proposal_EN.pdf (or DOCX) for design and limits.
All data are synthetic. The simulation time is fixed. No external actions are executed.
The model stage is an explicitly labelled deterministic mock, not a live LLM.
The test double exercises the integration boundary and evidence-reference validation.
Source connectors, persistent incident state, real approvals, recovery detection and
an approved model adapter are design proposals, not implemented capabilities.

For the mock, inspect PROMPT, model_payload(), mock_ai(), validate_draft().
For deterministic decisions, inspect triage(). scenarios() contains the examples.

Changing the thresholds requires calibration. The rules do not handle all incident
classes: low-volume financial-integrity issues need a separate human escalation path.

Prepare before presenting: run both commands, inspect the JSON, and explain why
recent pending payments are excluded and why a provider warning is not proof of cause.
