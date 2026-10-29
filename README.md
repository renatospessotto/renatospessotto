<div align="center">

# Renato Spessotto

### IA generativa, machine learning e engenharia de dados: do notebook à produção, com avaliação, custo e deploy pensados desde o início.

Ciência da Computação no ICMC/USP (São Carlos) · IA generativa na Cognitivo.ai

[![LinkedIn](https://img.shields.io/badge/LinkedIn-renato--spessotto-2a78d6?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/renato-spessotto-b6a2232b0)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-RenatoSpessotto-eda100?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co/RenatoSpessotto)
[![Email](https://img.shields.io/badge/email-spessottorenato%40gmail.com-52514e?style=for-the-badge&logo=gmail&logoColor=white)](mailto:spessottorenato@gmail.com)

</div>

| **6** | **4** | **3** | **0,84** |
|:---:|:---:|:---:|:---:|
| projetos de ML e IA públicos, com relatório e reprodução | modelos e datasets publicados no Hugging Face | sistemas com LLM entregues em produção para clientes | F1 da cascata calibrada que supera o Claude com 20% das chamadas |

## Em destaque: Review Intelligence PT-BR

**[review-intelligence-ptbr](https://github.com/renatospessotto/review-intelligence-ptbr)**: um teste do encoder de decisão **Laya** em português. Laya, BERTimbau e Qwen3.5-2B (QLoRA) foram destilados do Claude para extrair o sentimento por aspecto de reviews de e-commerce.

- **Qualidade:** os modelos pequenos chegam a 94% do F1 do Claude, custando de 30 a 300 vezes menos.
- **Calibração:** o Laya e o BERTimbau dizem o quanto confiam em cada resposta.
- **Cascata:** o modelo pequeno responde primeiro e só manda ao Claude os casos em que está inseguro. Com 20% das chamadas, o resultado supera o próprio Claude.
- **Entrega:** conjunto ouro com kappa 0,86, modelos e dataset no Hugging Face, API e demo em Docker.

[![Laya](https://img.shields.io/badge/HF-Laya%20ajustado-2a78d6)](https://huggingface.co/RenatoSpessotto/laya-aspectos-reviews-ptbr)
[![BERTimbau](https://img.shields.io/badge/HF-BERTimbau-eb6834)](https://huggingface.co/RenatoSpessotto/bertimbau-aspectos-reviews-ptbr)
[![Qwen](https://img.shields.io/badge/HF-Qwen3.5--2B%20LoRA-1baf7a)](https://huggingface.co/RenatoSpessotto/qwen3.5-2b-aspectos-reviews-ptbr-lora)
[![Dataset](https://img.shields.io/badge/HF-dataset-eda100)](https://huggingface.co/datasets/RenatoSpessotto/olist-aspectos-reviews-ptbr)

## Projetos de ML e IA

| Projeto | Resultado | Stack |
|---|---|---|
| [**review-intelligence-ptbr**](https://github.com/renatospessotto/review-intelligence-ptbr) | Laya × BERTimbau × Qwen destilados do Claude: **F1 0,74 a 1/30 do custo**; cascata **0,84 vs 0,79** do Claude | Laya, Transformers, PEFT/TRL, FastAPI, Docker |
| [**bertimbau-mental-health-ptbr**](https://github.com/renatospessotto/bertimbau-mental-health-ptbr) | Dataset próprio de 3 mil comentários anotados; BERTimbau com TAPT, focal loss e ensemble: **F1-macro 0,60 vs 0,40** do melhor modelo pronto | Transformers, PyTorch |
| [**vit-vs-cnn-oxford-pets**](https://github.com/renatospessotto/vit-vs-cnn-oxford-pets) | ViT-B/16 com **94,1%** em 37 raças, melhor que as CNNs com McNemar p < 0,001; Grad-CAM e attention rollout | PyTorch, torchvision |
| [**copd-cough-audio-classifier**](https://github.com/renatospessotto/copd-cough-audio-classifier) | DPOC pelo áudio da tosse: **ROC-AUC 0,936**, com checagens de vazamento de dados | librosa, scikit-learn |
| [**firewall-log-genetic-programming**](https://github.com/renatospessotto/firewall-log-genetic-programming) | Programação Genética em 1,5M de logs reais com concept drift: **F1-macro 0,475 → 0,587** | DEAP, NumPy |
| [**rice-yield-automl-autogluon**](https://github.com/renatospessotto/rice-yield-automl-autogluon) | AutoGluon reproduzindo um artigo do SBSI 2026: **MAPE 7,2% vs 13,7%** do XGBoost do artigo, com ensemble inspecionado e variação entre sementes | AutoGluon, scikit-learn |

## IA generativa em produção

Projetos entregues para clientes na **Cognitivo.ai**. O código é privado; aqui fica só a descrição.

- **Mensagens de recompra:** plataforma em React com **FastAPI + LangChain** que gera mensagens personalizadas a partir do perfil de cada cliente. O deploy é em alta disponibilidade na AWS (CloudFront, ECS, Auto Scaling, Secrets Manager), com CI/CD no GitHub Actions (OIDC).
- **Chatbot para um SaaS de contabilidade:** construído em **n8n**, responde com os dados da empresa no contexto do LLM, usando Redis, RabbitMQ e Qdrant.
- **Reuniões → tarefas:** pipeline em n8n que lê transcrições do Google Meet, extrai itens de ação com um **LLM** e cria tarefas no Asana, no projeto e com o responsável certos.

<!-- TODO: acrescentar o impacto real de cada um (horas economizadas, volume de mensagens/atendimentos). -->

## Stack

**IA e ML**

![PyTorch](https://img.shields.io/badge/PyTorch-ee4c2c?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-eda100?style=flat-square&logo=huggingface&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-f7931e?style=flat-square&logo=scikitlearn&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1c3c3c?style=flat-square&logo=langchain&logoColor=white)
![Claude](https://img.shields.io/badge/Claude%20API-d97757?style=flat-square&logo=anthropic&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-dc244c?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-ea4b71?style=flat-square&logo=n8n&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-f97316?style=flat-square)

**Backend e cloud**

![Python](https://img.shields.io/badge/Python-3776ab?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Spring](https://img.shields.io/badge/Spring-6db33f?style=flat-square&logo=spring&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-dd0031?style=flat-square&logo=angular&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ed?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-ECS%20%C2%B7%20Lambda%20%C2%B7%20S3%20%C2%B7%20Athena-232f3e?style=flat-square&logo=amazonwebservices&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088ff?style=flat-square&logo=githubactions&logoColor=white)

**Dados**

![Airflow](https://img.shields.io/badge/Airflow-017cee?style=flat-square&logo=apacheairflow&logoColor=white)
![Iceberg](https://img.shields.io/badge/Apache%20Iceberg-4e8ee9?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169e1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-dc382d?style=flat-square&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6600?style=flat-square&logo=rabbitmq&logoColor=white)

---

<sub>*In English:* Computer Science student at ICMC/USP (Brazil) building generative AI projects at Cognitivo.ai, working on generative AI, machine learning and data engineering. Highlight: [review-intelligence-ptbr](https://github.com/renatospessotto/review-intelligence-ptbr), which distills Claude into small calibrated encoders whose cascade beats the teacher with 20% of the API calls.</sub>
