
# Resonance Multi-Agent AI

Minimal research prototype of a **multi-agent system** implementing ideas of a *hybrid resonance algorithm*:
agents generate hypotheses, we score **spectral resonance** (FFT-based overlap), aggregate via a simple
attention-like mechanism, and pass the result through an **ethical filter**.

> This is an educational prototype, not a production AGI/ASI.

## Quickstart
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### Demo (synthetic medical target)
```bash
python applications/medical_research/run_demo.py --steps 150 --agents 4 --freq 3.0
```

### REST API
```bash
uvicorn api.app:app --reload --port 8000
```
Then POST a JSON body to `/resonance`:
```json
{
  "steps": 120,
  "agents": 4,
  "base_freq": 3.0
}
```

## Project layout
```
core/        # orchestrator, agents, math, interaction
api/         # FastAPI app exposing /resonance
applications/# demos
docs/        # brief notes
tests/       # pytest
```

## License
MIT
