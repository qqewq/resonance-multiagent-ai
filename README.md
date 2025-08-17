
# Resonance Multi‑Agent AI

Учебный репозиторий мультиагентной системы, реализующей идеи **гибридного резонансного алгоритма**:
порождаем гипотезы, измеряем резонанс (в частотной области), регулируем динамику через взаимодействие агентов
(attention/внимание) и этические пороги. 

> Это минимальный стартовый код: простой оркестратор, базовые агенты, спектральные метрики (FFT), этическая фильтрация,
> демо-приложение и тест.

## Быстрый старт
```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt

# Демка (медицинский пример)
python applications/medical_research/run_demo.py --steps 150 --agents 4 --freq 3.0
```

Ожидаемый вывод: средняя метрика резонанса по агентам, финальные параметры генераторов и статус прохождения этического фильтра.

## Структура
```
.
├── core/
│   ├── orchestrator.py
│   ├── interaction.py
│   ├── math/
│   │   ├── resonance_math.py
│   │   └── ethics.py
│   └── agents/
│       ├── base_agent.py
│       ├── resonance_agent.py
│       └── subagent_manager.py
├── applications/
│   └── medical_research/
│       ├── target_function.py
│       └── run_demo.py
├── docs/
│   ├── algorithm.md
│   └── multiagent.md
└── tests/
    └── test_resonance.py
```

## Как выложить в GitHub
```bash
git init
git add .
git commit -m "Initial commit: resonance multi-agent AI"
git branch -M main
git remote add origin <URL_твоего_репозитория>
git push -u origin main
```

## Дисклеймер
Код предназначен для исследовательских целей и иллюстрации концепций. Это не готовая AGI/ASI система.


## Дополнения
- **README_EN.md** — англоязычное описание.
- **REST API** (`api/app.py`) — запуск: `uvicorn api.app:app --reload --port 8000`, эндпоинты: `/health`, `POST /resonance`.
- **notebooks/demo.ipynb** — интерактивная демка.
- **CI** — GitHub Actions `.github/workflows/tests.yml` для автозапуска `pytest`.
