<div align="center">

<img src="assets/header.svg" width="100%" alt="Renato Spessotto: IA generativa, machine learning e engenharia de dados, do notebook à produção">

<br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-renato--spessotto-0b1d3a?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0a0a0a)](https://www.linkedin.com/in/renato-spessotto-b6a2232b0)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-RenatoSpessotto-0b1d3a?style=for-the-badge&logo=huggingface&logoColor=white&labelColor=0a0a0a)](https://huggingface.co/RenatoSpessotto)
[![Email](https://img.shields.io/badge/email-spessottorenato%40gmail.com-0b1d3a?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0a0a0a)](mailto:spessottorenato@gmail.com)

<br>

<img src="assets/metricas.svg" width="100%" alt="0,84 de F1 na cascata Laya→Claude; recall 5%→57% numa câmera nova; 14 padrões de algoritmos; 10x menos custo no Athena em produção">

</div>

<br>

<img src="assets/sec-destaques.svg" width="100%" alt="Projetos em destaque">

### [thermal-pv-hotspots-assimilation](https://github.com/renatospessotto/thermal-pv-hotspots-assimilation)

**Hotspots em usinas solares por drone térmico, com qualquer câmera.** Um detector treinado numa usina perde muito desempenho na seguinte: outra câmera, altitude, ângulo e paleta. A ideia foi tratar isso como a previsão do tempo trata satélites diferentes: **separar o fenômeno do jeito de observá-lo**.

- **Lê a temperatura, não a cor.** Leitores radiométricos (FLIR, DJI R-JPEG) em Python puro; o ΔT_z mede quanto cada ponto está acima dos painéis vizinhos e é pintado numa paleta fixa, reamostrado para 3 cm/px.
- **DINOv3 congelado + regressão logística**, célula a célula, somada a termos de **assimilação de dados**: correção de viés pelos metadados do voo (como o VarBC), ganho de Kalman pela qualidade da aquisição, viés de cada anotador e controle de qualidade dos rótulos.
- **Numa câmera nunca vista:** recall **5% → 57%**, AUROC **0,836 → 0,927**, recuperando **62%** da perda de desempenho. Uso indicado: triagem.
- **Entrega:** pacote Python (`analisar("foto.jpg")`) com alerta de fora-de-distribuição e pesos de ~7 MB no Hugging Face.

<details>
<summary><b>Ver o gráfico: cada etapa de assimilação numa câmera nova</b></summary>
<br>
<img src="https://raw.githubusercontent.com/renatospessotto/thermal-pv-hotspots-assimilation/main/docs/figures/01_camera_nova.png" width="100%" alt="Recall e AUROC numa câmera nova a cada etapa de assimilação">
</details>

![DINOv3](https://img.shields.io/badge/DINOv3-0b1d3a?style=flat-square&logo=meta&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-0b1d3a?style=flat-square&logo=pytorch&logoColor=white)
[![HF](https://img.shields.io/badge/HF-modelo-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)](https://huggingface.co/RenatoSpessotto/thermal-pv-hotspots-assimilation)

<img src="assets/divisor.svg" width="100%" alt="">

### [review-intelligence-ptbr](https://github.com/renatospessotto/review-intelligence-ptbr)

**Laya × BERTimbau × Qwen3.5-2B (QLoRA), destilados do Claude, lendo reviews de e-commerce em português.** O Claude Haiku rotulou 10 mil reviews da Olist em cinco aspectos (entrega, produto, atendimento, preço, embalagem); os modelos pequenos aprenderam com esses rótulos e foram avaliados num conjunto ouro independente (kappa 0,86).

- **Qualidade a uma fração do custo:** os modelos pequenos chegam a 94% do F1 do Claude (**0,74**), custando de **30 a 300 vezes menos**.
- **Calibração:** o Laya (ECE 0,014) e o BERTimbau (ECE 0,006) dizem o quanto confiam em cada resposta.
- **Cascata:** o modelo pequeno responde primeiro e só manda ao Claude os casos em que está inseguro. Com **20%** das chamadas, a cascata chega a **F1 0,84**, acima do próprio Claude (0,79).
- **Entrega:** modelos e dataset no Hugging Face, API FastAPI e demo Gradio com `docker compose up`.

<details>
<summary><b>Ver o gráfico: qualidade × custo de cada modelo</b></summary>
<br>
<img src="https://raw.githubusercontent.com/renatospessotto/review-intelligence-ptbr/main/docs/figures/01_custo_f1.png" width="100%" alt="Qualidade (F1) versus custo por review de cada modelo">
</details>

[![Laya](https://img.shields.io/badge/HF-Laya%20ajustado-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)](https://huggingface.co/RenatoSpessotto/laya-aspectos-reviews-ptbr)
[![BERTimbau](https://img.shields.io/badge/HF-BERTimbau-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)](https://huggingface.co/RenatoSpessotto/bertimbau-aspectos-reviews-ptbr)
[![Qwen](https://img.shields.io/badge/HF-Qwen3.5--2B%20LoRA-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)](https://huggingface.co/RenatoSpessotto/qwen3.5-2b-aspectos-reviews-ptbr-lora)
[![Dataset](https://img.shields.io/badge/HF-dataset-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)](https://huggingface.co/datasets/RenatoSpessotto/olist-aspectos-reviews-ptbr)

<img src="assets/divisor.svg" width="100%" alt="">

### [algorithm-patterns-trainer](https://github.com/renatospessotto/algorithm-patterns-trainer)

**Um app full-stack de repetição espaçada para padrões de algoritmos de entrevista.** Em vez de resolver problemas aleatórios, ele ensina **14 macro-padrões** (HashMap, Two Pointers, Sliding Window, …, Trie/Bits) por uma sequência curada de **46 problemas-núcleo** e mantém tudo fresco com 2 exercícios por dia: sempre os que você tem mais chance de ter esquecido.

- **Sem data de revisão, sem acúmulo.** Cada problema tem uma urgência pela curva de esquecimento, `1 − e^(−Δt/estabilidade)`, calculada na hora. A estabilidade se adapta a uma média móvel exponencial dos resultados e ao tempo gasto em relação a uma meta por dificuldade.
- **Currículo em fases.** Introdução pela sequência fixa → consolidação (só revisão, completada pelo seu padrão *mais fraco*) → fase livre, com cerca de **2.900 problemas** filtráveis por padrão.
- **Dados reproduzíveis, nenhum dado no git.** Um ETL em Python cruza dois datasets públicos fixados por commit e mapeia as tags oficiais para os 14 padrões, dentro do build do Docker.
- **Um container em produção.** O Angular vai dentro do jar do Spring Boot; o Flyway cuida do schema e do seed. Telas de hoje, explorar, estatísticas (heatmap, sequências, padrões fracos/fortes), histórico e leitura de papers.

![Java](https://img.shields.io/badge/Java%2021-0b1d3a?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot%203.3-0b1d3a?style=flat-square&logo=springboot&logoColor=white)
![Angular](https://img.shields.io/badge/Angular%2018-0b1d3a?style=flat-square&logo=angular&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL%2016-0b1d3a?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-0b1d3a?style=flat-square&logo=docker&logoColor=white)

<br>

<img src="assets/sec-producao.svg" width="100%" alt="Em produção na Cognitivo.ai">

<img src="assets/producao.svg" width="100%" alt="10x menos custo no Athena; consultas de 5s para 1s; 30–45 min poupados por reunião; 35–40% menos custo de armazenamento no S3">

Sistemas de IA generativa e dados que entreguei para clientes entre mai/2025 e abr/2026. O código é privado; aqui ficam o problema e o resultado.

| Projeto | O que faz | Resultado | Stack |
|---|---|---|---|
| **Consultas 10x mais baratas** | Para um cliente de consultoria farmacêutica, migrei o dataset de clustering para **Apache Iceberg** com **Z-Order** no S3 | Dados lidos por cliente de **1 GB para 100 MB**, custo das consultas no Athena **10x menor**, resposta de **5s para 1s** | Iceberg, S3, Athena |
| **Chatbot com RAG** | Atendimento de um SaaS de contabilidade: busca os dados da empresa num banco vetorial e responde com um LLM | Assumiu as dúvidas simples de clientes antes respondidas por um funcionário | n8n, Qdrant, Redis, RabbitMQ |
| **Reuniões → tarefas** | Lê transcrições do Google Meet, extrai os itens de ação com um LLM e cria as tarefas no Asana, no projeto e com o responsável certos | Poupa **30–45 min de organização por reunião** (estimativa de 120–360 h/ano por gerente de projeto) | n8n, LLM, Asana |
| **Mensagens de recompra** | Gera mensagens personalizadas a partir do perfil de cada cliente | Em produção na AWS com alta disponibilidade (CloudFront, ECS, Auto Scaling, Secrets Manager) e CI/CD por OIDC | FastAPI, LangChain, React, AWS |
| **Armazenamento no S3** | Políticas de ciclo de vida nos buckets do S3 | **35–40% menos** custo de armazenamento | S3 |

**Outros projetos:** [bertimbau-mental-health-ptbr](https://github.com/renatospessotto/bertimbau-mental-health-ptbr) · [vit-vs-cnn-oxford-pets](https://github.com/renatospessotto/vit-vs-cnn-oxford-pets) · [copd-cough-audio-classifier](https://github.com/renatospessotto/copd-cough-audio-classifier) · [firewall-log-genetic-programming](https://github.com/renatospessotto/firewall-log-genetic-programming) · [rice-yield-automl-autogluon](https://github.com/renatospessotto/rice-yield-automl-autogluon)

<br>

<img src="assets/sec-stack.svg" width="100%" alt="Stack">

**IA e ML**

![PyTorch](https://img.shields.io/badge/PyTorch-0b1d3a?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-0b1d3a?style=flat-square&logo=huggingface&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-0b1d3a?style=flat-square&logo=scikitlearn&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-0b1d3a?style=flat-square&logo=langchain&logoColor=white)
![Claude](https://img.shields.io/badge/Claude%20API-0b1d3a?style=flat-square&logo=anthropic&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-0b1d3a?style=flat-square&logo=qdrant&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-0b1d3a?style=flat-square&logo=n8n&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-0b1d3a?style=flat-square&logo=gradio&logoColor=white)

**Backend e cloud**

![Python](https://img.shields.io/badge/Python-0b1d3a?style=flat-square&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-0b1d3a?style=flat-square&logo=openjdk&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0b1d3a?style=flat-square&logo=fastapi&logoColor=white)
![Spring](https://img.shields.io/badge/Spring%20Boot-0b1d3a?style=flat-square&logo=springboot&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-0b1d3a?style=flat-square&logo=angular&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-0b1d3a?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-ECS%20%C2%B7%20Lambda%20%C2%B7%20S3%20%C2%B7%20Athena-0b1d3a?style=flat-square&logo=amazonwebservices&logoColor=white&labelColor=0a0a0a)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-0b1d3a?style=flat-square&logo=githubactions&logoColor=white)

**Dados**

![Airflow](https://img.shields.io/badge/Airflow-0b1d3a?style=flat-square&logo=apacheairflow&logoColor=white)
![Iceberg](https://img.shields.io/badge/Apache%20Iceberg-0b1d3a?style=flat-square&logo=apache&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0b1d3a?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-0b1d3a?style=flat-square&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-0b1d3a?style=flat-square&logo=rabbitmq&logoColor=white)

<img src="assets/divisor.svg" width="100%" alt="">

<sub>*In English:* Computer Science student at ICMC/USP (Brazil), tech intern at Embraer, previously building generative AI and data systems in production at Cognitivo.ai (e.g., Athena queries 10x cheaper with Iceberg + Z-Order, a RAG chatbot that took over routine customer questions). Highlights: [algorithm-patterns-trainer](https://github.com/renatospessotto/algorithm-patterns-trainer), a full-stack spaced-repetition trainer (Spring Boot, Angular, PostgreSQL); [thermal-pv-hotspots-assimilation](https://github.com/renatospessotto/thermal-pv-hotspots-assimilation), camera-invariant solar hotspot detection using data-assimilation ideas from weather forecasting; and [review-intelligence-ptbr](https://github.com/renatospessotto/review-intelligence-ptbr), which distills Claude into small calibrated encoders whose cascade beats the teacher with 20% of the API calls.</sub>
