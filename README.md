# Engenharia de Contexto na Prática: Domando Alucinações de IA com BDD e Modelos Visuais

> **Workshop Hands-On | Agile Trends 2026 SP**
> **Formato:** 90 minutos | **Stack:** Python 3.10+, `pytest`, Mermaid.js, LLM (Gemini)

---

## 📌 Sobre este Repositório

Este repositório é o **material de apoio inicial (boilerplate)** para os participantes do workshop **"Engenharia de Contexto na Prática: Como domar alucinações da IA usando BDD e Modelos Visuais"** no Agile Trends 2026 SP.

O objetivo da dinâmica é demonstrar o abismo entre o **"prompting ingênuo em texto livre"** (que gera alucinações e código com falhas de lógica) e a **Engenharia de Contexto em 4 Fases**, que utiliza refinamento ágil (BDD em `bdd/`), arquitetura de software restritiva (Matriz CLUPIR Multi-Visão em `diagram-as-code/`), desenvolvimento orientado a testes com **Man-in-the-Loop** (TDD) e **Skills de Sistema com Tuning Defaults** para obter entregas determinísticas e 100% aderentes à suíte de testes automatizados.

---

## 📂 Estrutura do Repositório (Boilerplate do Aluno)

```text
agile-trends-2026-context-engineering-boilerplate/
├── .gitignore                         --> Configurado para omitir a pasta gabaritos/ local do instrutor
├── LICENSE
├── README.md                          --> Guia de onboarding e instruções do workshop
├── requirements.txt                   --> Dependências Python (pytest)
├── case/
│   ├── 01-motor-cancelamento.md       --> Requisito ambíguo do caso principal (Refund Engine)
│   └── 00-requisito-bruto-stub-template.md --> Template Stub para expansão de novos casos
├── bdd/                               --> Pasta de saída da Fase 1 (01-motor-cancelamento.feature)
├── diagram-as-code/                   --> Pasta de saída da Fase 2
│   └── 01-motor-cancelamento/         --> Diretório por Caso (01-ciclo-de-vida.mmd, 02-fluxo-calculo.mmd)
├── clupir/
│   ├── clupir-framework-ref.md        --> Guia de referência teórica da Matriz CLUPIR
│   └── prompt-skill-clupir.md         --> System Prompt da Skill CLUPIR (Fase 2)
├── skills/
│   ├── fase1-prompt-skill-analista-bdd.md   --> Skill 1: Analista BDD & Requisitos Determinísticos
│   ├── fase2-prompt-skill-clupir.md         --> Skill 2: IA Arquiteta CLUPIR (Multi-Visão Diagram-as-Code)
│   ├── fase3-prompt-skill-dev-testes.md     --> Skill 3: Especialista TDD & Automação de Testes
│   └── fase4-prompt-skill-dev-codigo.md     --> Skill 4: Engenheiro de Software Código Determinístico
├── templates/
│   ├── fase1-prompt-analista-bdd.md   --> Prompt 1: Extração de BDD (Gherkin)
│   ├── fase2-prompt-arquiteto.md      --> Prompt 2: IA Arquiteta (Multi-Visão Diagram-as-Code)
│   ├── fase3-prompt-dev-tests.md      --> Prompt 3: Co-Criação de Testes TDD & Stub (Man-in-the-Loop)
│   └── fase4-prompt-dev-codigo.md     --> Prompt 4: Geração do Código Final Determinístico
├── src/                               --> Pasta de código-fonte (inicialmente vazia, gerada na Fase 3/4)
└── tests/                             --> Pasta de testes automatizados (inicialmente vazia, gerada na Fase 3)
```

---

## 🚀 Setup do Ambiente Local

### Pré-requisitos

* **Python 3.10** ou superior instalado.
* Acesso à interface do **Google Gemini** (ou CLI/IDE de sua preferência).
* Leitor/extensão de Markdown com suporte a **Mermaid.js** (VS Code, GitHub ou editor web).

### Passo a Passo de Instalação

1. **Clone este repositório:**
```bash
git clone https://github.com/<seu-usuario>/agile-trends-2026-context-engineering-boilerplate.git
cd agile-trends-2026-context-engineering-boilerplate
```

2. **Crie e ative um ambiente virtual:**
```bash
# Linux / macOS
python3 -m venv .venv
source .venv/bin/activate

# Windows (PowerShell)
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. **Instale as dependências:**
```bash
pip install -r requirements.txt
```

---

## ⚙️ Roteiro Mão na Massa (90 Minutos)

A dinâmica nas mesas segue o método de Engenharia de Contexto com **Prompts Automatizados e Nomenclatura Padronizada por Caso**:

```
  ┌───────────────────────┐       ┌───────────────────────┐       ┌───────────────────────┐       ┌───────────────────────┐       ┌───────────────────────┐
  │ case/                 │ ───>  │  Fase 1: BDD          │ ───>  │ Fase 2: CLUPIR        │ ───>  │ Fase 3: Testes        │ ───>  │ Fase 4: Código        │
  │ 01-motor-cancelamento │       │  bdd/                 │       │ diagram-as-code/      │       │ tests/                │       │ src/                  │
  │                       │       │ 01-motor-cancelamento │       │ 01-motor-cancelamento │       │ test_refund_engine.py │       │ refund_engine.py      │
  └───────────────────────┘       └───────────────────────┘       └───────────────────────┘       └───────────────────────┘       └───────────────────────┘
```

### ⏱️ 00 - 15 min | Abertura & O Problema do "Digitador de Prompts"

* Apresentação teórica sobre carga cognitiva em LLMs, alucinações e o método de Engenharia de Contexto.

### ⏱️ 15 - 35 min | Fase 1: Inception Orientada a Comportamento (BDD)

1. Copie o conteúdo completo de `templates/fase1-prompt-analista-bdd.md`.
2. Envie para a IA. O prompt instrui a IA a ler `case/01-motor-cancelamento.md` e aplica as configurações de tuning default.
3. Analise o BDD gerado e salve o arquivo em `bdd/01-motor-cancelamento.feature`.

### ⏱️ 35 - 55 min | Fase 2: A IA como Arquiteta (Matriz CLUPIR + Multi-Visão Diagram-as-Code)

1. Copie o conteúdo completo de `templates/fase2-prompt-arquiteto.md`.
2. Envie para a IA. A IA lerá o contrato BDD em `bdd/01-motor-cancelamento.feature`.
3. Obtenha as duas visões complementares em um diretório com a mesma nomenclatura do caso (`diagram-as-code/01-motor-cancelamento/`):
   - **Visão 1 (Ciclo de Vida e Elegibilidade):** `stateDiagram-v2` $\rightarrow$ Salvar em `diagram-as-code/01-motor-cancelamento/01-ciclo-de-vida.mmd`
   - **Visão 2 (Fluxo Orquestrado do Cálculo):** `flowchart TD` $\rightarrow$ Salvar em `diagram-as-code/01-motor-cancelamento/02-fluxo-calculo.mmd`

### ⏱️ 55 - 75 min | Fase 3: Co-Criação de Testes & Stub (Man-in-the-Loop / Estado RED)

1. Copie o conteúdo completo de `templates/fase3-prompt-dev-tests.md` e envie para a IA.
2. A IA lerá os andaimes em `bdd/` e `diagram-as-code/01-motor-cancelamento/` e gerará os arquivos **do zero**:
   - Stub inicial em `src/refund_engine.py` (lançando `NotImplementedError`)
   - Suíte de testes em `tests/test_refund_engine.py`
3. Execute os testes no terminal:
```bash
pytest tests/test_refund_engine.py
```
4. Valide que os testes executam e falham por `NotImplementedError` (**Estado RED**).

### ⏱️ 75 - 85 min | Fase 4: Geração do Código Final Determinístico (Estado GREEN 100%)

1. Copie o conteúdo completo de `templates/fase4-prompt-dev-codigo.md` e envie para a IA.
2. A IA lerá os testes em `tests/` e os andaimes em `bdd/` e `diagram-as-code/01-motor-cancelamento/` e preencherá a implementação final em `src/refund_engine.py`.
3. Execute novamente os testes:
```bash
pytest tests/test_refund_engine.py
```
4. Valide que todos os cenários estão **GREEN (100% aprovados)**.

---

## 🛠️ Expansão para Novos Estudos de Caso

Para utilizar esta mesma engenharia de contexto em novos projetos ou desafios:
1. Duplique o arquivo [case/00-requisito-bruto-stub-template.md](file:///c:/Users/johnn/Github/agile-trends-2026-context-engineering-boilerplate/case/00-requisito-bruto-stub-template.md) com o nome do seu novo caso (ex: `case/02-novo-desafio.md`).
2. Escreva o seu novo requisito bruto.
3. Execute a sequência dos prompts de `templates/` apontando para o novo caso.

---

## 📚 Referências Científicas

* **Artigo Científico Base (IEEE Access 2025):**
Seabra, J., & Silva, L. F. (2025). *Classifying Software Modeling Languages: The CLUPIR Model Approach*. IEEE Access, 13, 80759-80774. DOI: `10.1109/ACCESS.2025.3567005`

---

## 📝 Licença

Este projeto é disponibilizado sob a licença MIT.