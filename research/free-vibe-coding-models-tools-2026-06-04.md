# Бесплатные модели и инструменты для вайб-кодинга

Дата исследования: 2026-06-04  
Фокус: бесплатные или условно бесплатные модели, CLI/IDE-агенты и локальные стеки для вайб-кодинга.  
Ограничение источников: русскоязычные источники использованы для контекста и практических гайдов; актуальные лимиты и статус бесплатности проверены по официальным GitHub, Google, OpenRouter, Ollama и GitHub Docs. Маркетинговые лендинги и продающие страницы не засчитывались как доказательная база.

## Короткий вывод

Главная ставка на 4 июня 2026: лучший бесплатный старт для вайб-кодинга - Gemini CLI, GitHub Copilot Free, OpenRouter free models, Ollama + локальные code-модели, а также open-source оболочки Cline, Kilo Code, Continue, Aider, OpenCode, Tabby.

Самый важный риск: бесплатные cloud-квоты быстро меняются. Qwen Code в русских гайдах часто описан как бесплатный, но официальный репозиторий QwenLM/qwen-code сообщает, что OAuth free tier закрыт 15 апреля 2026. Gemini CLI остается сильным бесплатным вариантом сейчас, но Google объявил переход потребителей на Antigravity CLI и остановку бесплатного обслуживания Gemini CLI 18 июня 2026.

## Что сейчас реально бесплатно

| Вариант | Статус на 2026-06-04 | Для чего годится | Ограничение |
|---|---:|---|---|
| Gemini CLI | бесплатно для личного Google-аккаунта до announced cutoff 2026-06-18 | быстрый terminal-first вайб-кодинг, правки файлов, команды, ресерч, планирование | миграция на Antigravity CLI уже объявлена |
| GitHub Copilot Free | 2,000 completions + 50 chat/agent requests в месяц | IDE-автодополнение, легкий chat/agent mode | мало для плотного агентного кодинга |
| OpenRouter free models | бесплатные `:free` варианты, 20 RPM и ограничение по дневным запросам | тесты агентов, fallback, дешевые эксперименты | нестабильная доступность, rate limits, слабее для продакшена |
| Ollama + Qwen2.5-Coder / DeepSeek-Coder-V2 / StarCoder2 / CodeGemma | бесплатно локально после скачивания модели | приватный локальный вайб-кодинг, офлайн, эксперименты | нужны RAM/GPU/терпение, качество ниже frontier-моделей |
| Cline / Kilo Code / Continue / Aider / OpenCode / Tabby | open-source оболочки; стоимость зависит от выбранной модели | агентный coding loop, IDE/CLI workflow, BYOK, локальные модели | free получается через локальную модель или free provider |
| Qwen Code | сам инструмент open-source; старый free OAuth закрыт | хорош как CLI-агент с API key, Coding Plan или локальным совместимым backend | текущий бесплатный OAuth-путь закрыт |

## Рекомендуемые связки

### 1. Быстрый бесплатный старт

Использовать Gemini CLI сейчас, параллельно смотреть Antigravity CLI. Причина: по официальному анонсу Gemini CLI давал 60 requests/min и 1,000 requests/day, а Habr и VC фиксировали его как главный бесплатный terminal agent. Риск: Google Developers Blog от 19 мая 2026 объявил, что 18 июня 2026 Gemini CLI и Gemini Code Assist IDE extensions перестанут обслуживать free/consumer users.

Подходит для:

- создать прототип;
- прочитать проект;
- спланировать фичу;
- поправить несколько файлов;
- прогнать команды и диагностику.

### 2. Бесплатный IDE-слой

Использовать GitHub Copilot Free в VS Code/JetBrains/Neovim как базовое автодополнение и редкий chat/agent. Официальные GitHub Docs и Copilot plans указывают 2,000 completions и 50 chat/agent requests в месяц.

Подходит для:

- небольших задач;
- знакомства с AI coding;
- автодополнения;
- проверки гипотез перед переходом на платный план.

### 3. Локальный стек без API-чеков

Использовать Ollama как runtime и подключать его к Cline, Kilo Code, Roo Code, OpenCode, Continue или Aider. По официальному репозиторию Ollama поддерживает запуск open models и интеграции с coding agents. На страницах Ollama доступны code-модели:

- `qwen2.5-coder` - 0.5B, 1.5B, 3B, 7B, 14B, 32B; 32K context;
- `deepseek-coder-v2` - 16B/236B, до 160K context у 16B-варианта;
- `starcoder2` - 3B, 7B, 15B;
- `codegemma` - компактная code-модель семейства Gemma.

Подходит для:

- приватного кода;
- обучения;
- офлайн-экспериментов;
- дешевого long-running refactor loop;
- задач, где скорость и качество frontier-модели не критичны.

### 4. OpenRouter как бесплатный gateway

Использовать OpenRouter `:free` варианты для экспериментов в Cline/Kilo/OpenCode/Continue. Официальные docs описывают `:free` suffix, а FAQ предупреждает: free models имеют низкие лимиты и обычно плохо подходят для production. Документация по limits фиксирует 20 requests/min для free variants; Zendesk-статья OpenRouter указывает 50 requests/day для нового free-tier пользователя.

Подходит для:

- теста разных моделей;
- обучения tool calling;
- дешевого сравнения промптов;
- fallback при локальном слабом железе.

### 5. Open-source оболочки для вайб-кодинга

Практичная карта:

- Cline: VS Code agent, умеет читать/править файлы, запускать команды, подключать Ollama/LM Studio/OpenAI-compatible providers.
- Kilo Code: IDE/CLI agentic platform, MIT, 500+ models, поддерживает autocomplete, browser automation, modes.
- Continue: open-source CLI/checks и IDE ecosystem; полезен для AI checks и source-controlled workflows.
- Aider: terminal pair programming, Git-first workflow, подходит для аккуратных patch/diff итераций.
- OpenCode: open-source terminal coding agent с multi-provider подходом.
- Tabby: self-hosted AI coding assistant, уместен как локальная Copilot-alternative для автодополнения.
- Roo Code: функционально сильный Cline-family агент, но официальный README содержит предупреждение, что Roo Code Extension был shut down 15 мая 2026; для новых установок лучше смотреть Cline, Kilo, ZooCode или актуальный fork.

## Модели

### Лучший бесплатный cloud-кандидат

Gemini через Gemini CLI остается самым сильным бесплатным вариантом на дату исследования. Причина: большая квота, сильная модель, 1M context, file/shell tools, web grounding, MCP. Риск миграции высокий из-за announced cutoff 18 июня 2026.

### Лучшие локальные модели

Для локального вайб-кодинга через Ollama:

- `qwen2.5-coder:7b` - стартовый минимум для слабого железа;
- `qwen2.5-coder:14b` - более стабильный вариант, если хватает памяти;
- `qwen2.5-coder:32b` - лучший локальный выбор из этой линейки при достаточном железе;
- `deepseek-coder-v2:16b` - сильный вариант с большим контекстом;
- `starcoder2:7b/15b` - прозрачная open-code линейка для экспериментов;
- `codegemma` - компактный fallback для легких задач.

### Qwen Code

Qwen Code как агент остается полезным, но текущий free-cloud тезис из старых Habr/VC-гайдов устарел. Официальный QwenLM/qwen-code сообщает:

- 13 апреля 2026 free OAuth quota был снижен до 100 requests/day;
- 15 апреля 2026 Qwen OAuth free tier discontinued;
- дальше нужны Alibaba Cloud Coding Plan, OpenRouter, Fireworks AI или собственный API key.

## Практические сценарии

### Учебный вайб-кодинг

Связка: Gemini CLI или GitHub Copilot Free + VS Code.  
Результат: быстро собрать маленький сайт, Telegram-бота, CLI-утилиту, прототип API.

### Приватный код

Связка: Ollama + Cline/Kilo/Aider + `qwen2.5-coder:14b` или `deepseek-coder-v2:16b`.  
Результат: код остается локально, стоимость нулевая после настройки железа.

### Агентные эксперименты

Связка: OpenCode/Kilo/Cline + OpenRouter free models + локальный fallback через Ollama.  
Результат: можно тестировать tool use, MCP, browser/file operations, prompts и agent modes.

### Ревью и проверки PR

Связка: Continue checks или GitHub Copilot Free для малых PR; локальная модель для предварительного ревью.  
Результат: дешевый pre-review перед платным агентом или человеком.

## Ограничения и риски

- Бесплатные облачные лимиты нестабильны. Qwen Code уже потерял free OAuth, Gemini CLI уходит в Antigravity CLI для consumers 18 июня 2026.
- Локальные модели требуют железа. 7B годится для простых задач, 14B/32B заметно лучше, но дороже по RAM/VRAM.
- Free OpenRouter часто rate-limited. Документация прямо предупреждает, что free models обычно не подходят для production.
- Агентам нельзя сразу давать полный доступ к shell, browser, secrets и production repo. Нужны git diff review, sandbox, allowlist команд.
- VC/Habr-гайды быстро устаревают по лимитам. Их полезно читать для практических шагов, а лимиты проверять по официальным docs в день внедрения.

## Практические рекомендации

1. Для старта сегодня: Gemini CLI + GitHub Copilot Free.
2. Для устойчивого бесплатного контура: Ollama + Cline или Kilo Code + `qwen2.5-coder:14b/32b`.
3. Для agentic CLI: Aider или OpenCode; для VS Code workflow: Cline или Kilo Code.
4. Для экспериментов с cloud-моделями: OpenRouter `:free`, с ожиданием rate limits.
5. Qwen Code держать в списке инструментов, но планировать API key/Coding Plan/local backend.
6. Перед каждым новым исследованием free-tier обновлять статусы Gemini, Qwen, OpenRouter и Copilot по официальным источникам.

## Источники

1. Habr, "Google выпустила Gemini CLI - бесплатный open source ИИ-ассистент для командной строки": https://habr.com/en/news/921842/
2. Habr, "Бесплатный вайбкодинг с Qwen Code - установка, возможности": https://habr.com/ru/companies/studyai/articles/1022332/
3. Habr, "Как использовать Cline и Roo Code в качестве AI-ассистента для кода?": https://habr.com/ru/companies/bothub/articles/881248/
4. VC.ru, "Терминальные ИИ агенты - CLAUDE, CODEX, GEMINI": https://vc.ru/ai/2890293-terminalnye-ii-agenty-claude-codex-gemini
5. VC.ru, "Руководство по Использованию Cline и Roo Code как AI-Кодинг Ассистентов": https://vc.ru/ai/1888477-cline-i-roo-code-ai-assistenty-dlya-razrabotki
6. Google Blog, "Gemini CLI: your open-source AI agent", 25.06.2025: https://blog.google/technology/developers/introducing-gemini-cli-open-source-ai-agent
7. Google Developers Blog, "Transitioning Gemini CLI to Antigravity CLI", 19.05.2026: https://developers.googleblog.com/en/an-important-update-transitioning-gemini-cli-to-antigravity-cli/
8. Google Developers Blog, "Plan mode is now available in Gemini CLI", 11.03.2026: https://developers.googleblog.com/plan-mode-now-available-in-gemini-cli/
9. GitHub, google-gemini/gemini-cli: https://github.com/google-gemini/gemini-cli
10. GitHub, QwenLM/qwen-code: https://github.com/QwenLM/qwen-code
11. Qwen Code Docs, Authentication: https://qwenlm.github.io/qwen-code-docs/en/users/configuration/auth/
12. GitHub, cline/cline: https://github.com/cline/cline
13. GitHub, Kilo-Org/kilocode: https://github.com/Kilo-Org/kilocode
14. GitHub, continuedev/continue: https://github.com/continuedev/continue
15. GitHub, Aider-AI/aider: https://github.com/Aider-AI/aider
16. GitHub, ollama/ollama: https://github.com/ollama/ollama
17. Ollama docs, Roo Code integration: https://docs.ollama.com/integrations/roo-code
18. Ollama library, qwen2.5-coder: https://ollama.com/library/qwen2.5-coder
19. Ollama library, deepseek-coder-v2: https://ollama.com/library/deepseek-coder-v2
20. Ollama library, starcoder2: https://ollama.com/library/starcoder2
21. Ollama library, codegemma: https://ollama.com/library/codegemma
22. OpenRouter Docs, Free Variant: https://openrouter.ai/docs/guides/routing/model-variants/free
23. OpenRouter Docs, API Rate Limits: https://openrouter.ai/docs/api-reference/limits
24. OpenRouter FAQ: https://openrouter.ai/docs/faq
25. GitHub Docs, GitHub Copilot Free: https://docs.github.com/en/copilot/managing-copilot/managing-copilot-as-an-individual-subscriber/about-github-copilot-free
26. GitHub, TabbyML/tabby: https://github.com/TabbyML/tabby

## Оценка уверенности

Уверенность: 84/100.

Сильные стороны: free-tier факты проверены по официальным источникам; Habr/VC использованы как русскоязычный контекст; источников больше 10; Qwen/Gemini drift явно зафиксирован.

Слабые стороны: бесплатные квоты cloud-инструментов меняются быстро; часть сильных практических материалов по vibe coding живет в англоязычных docs, GitHub и Reddit, поэтому русскоязычная база полезна для гайдов, но слабее для актуального статуса лимитов.
