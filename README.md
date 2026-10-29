## Olá, eu sou o Renato 👋

Estudante de **Ciência da Computação no ICMC/USP** (São Carlos). Trabalho com **IA generativa, machine learning e engenharia de dados**: gosto de levar modelos do notebook para produção, com avaliação, custo e deploy pensados desde o início.

🇬🇧 *Computer Science student at ICMC/USP (Brazil), working on generative AI, machine learning and data engineering.*

---

### 🤖 IA generativa em produção
Projetos entregues para clientes na **Cognitivo.ai** (código privado, descritos aqui):

- **Geração de mensagens de recompra:** plataforma React + **FastAPI + LangChain** que gera mensagens personalizadas a partir do perfil de cada cliente, com deploy em alta disponibilidade na AWS (CloudFront, ECS, Auto Scaling, Secrets Manager) e CI/CD com GitHub Actions (OIDC).
- **Chatbot personalizado para um SaaS de contabilidade:** chatbot em **n8n** que responde com dados da empresa no contexto do LLM, com Redis, RabbitMQ e Qdrant.
- **Reuniões → tarefas:** pipeline em n8n que lê transcrições do Google Meet, extrai itens de ação com um **LLM** e cria tarefas no Asana para o projeto e responsável certos.

<!-- TODO: acrescentar o impacto real de cada um (horas economizadas, volume de mensagens/atendimentos). -->

### 🔬 Projetos de ML e IA

| Projeto | Destaque | Stack |
|---|---|---|
| [**review-intelligence-ptbr**](https://github.com/renatospessotto/review-intelligence-ptbr) | Teste do encoder **Laya** em PT-BR contra BERTimbau e Qwen3.5-2B (QLoRA), destilados do Claude: **F1 0,74 a 1/30 do custo** e cascata calibrada que **supera o Claude (0,84 vs 0,79)** com 20% das chamadas | Laya, Transformers, PEFT/TRL, FastAPI, Docker |
| [**bertimbau-mental-health-ptbr**](https://github.com/renatospessotto/bertimbau-mental-health-ptbr) | Dataset próprio de 3 mil comentários rotulados; BERTimbau com TAPT, focal loss e ensemble: **F1-macro 0,60 vs 0,40** do melhor modelo pronto | Transformers, PyTorch |
| [**vit-vs-cnn-oxford-pets**](https://github.com/renatospessotto/vit-vs-cnn-oxford-pets) | ViT-B/16 com **94,1%** em 37 classes, McNemar, attention rollout e Grad-CAM | PyTorch, torchvision |
| [**copd-cough-audio-classifier**](https://github.com/renatospessotto/copd-cough-audio-classifier) | DPOC por áudio de tosse: **ROC-AUC 0,936**, com checagens de vazamento | librosa, scikit-learn |
| [**firewall-log-genetic-programming**](https://github.com/renatospessotto/firewall-log-genetic-programming) | Programação Genética em 1,5M de logs reais com concept drift: **F1-macro 0,475 → 0,587** | DEAP, NumPy |

### 🤗 Hugging Face
Modelos e dataset em [huggingface.co/RenatoSpessotto](https://huggingface.co/RenatoSpessotto): [Laya](https://huggingface.co/RenatoSpessotto/laya-aspectos-reviews-ptbr) e [BERTimbau](https://huggingface.co/RenatoSpessotto/bertimbau-aspectos-reviews-ptbr) ajustados para aspectos de reviews, [Qwen3.5-2B LoRA](https://huggingface.co/RenatoSpessotto/qwen3.5-2b-aspectos-reviews-ptbr-lora) e o [dataset](https://huggingface.co/datasets/RenatoSpessotto/olist-aspectos-reviews-ptbr) com ouro de consenso e 10 mil rótulos do Claude.

### 🛠️ Stack
**IA & ML:** PyTorch · Hugging Face Transformers · scikit-learn · LangChain · LLMs · embeddings e Qdrant · n8n · Gradio
**Backend & Cloud:** Python · FastAPI · Docker · AWS (ECS, Lambda, S3, Athena, CloudFront) · GitHub Actions
**Dados:** Airflow · Apache Iceberg · PostgreSQL · Redis · RabbitMQ

### 📫 Contato
[LinkedIn](https://www.linkedin.com/in/renato-spessotto-b6a2232b0) · spessottorenato@gmail.com
