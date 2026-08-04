# Prompt Template - Fase 3: Co-Criação de Testes Automatizados & Stub (Man-in-the-Loop)

> **Instruções para o Aluno:**
> Copie e envie todo o conteúdo deste arquivo para a IA. O prompt carrega automaticamente a Skill da Fase 3, configura os valores default e instrui a IA a ler o contrato BDD e os diagramas do repositório em `bdd/01-motor-cancelamento.feature` e `diagram-as-code/01-motor-cancelamento/`.

---

### [INÍCIO DO PROMPT PARA A IA]

```markdown
# SYSTEM SKILL: ESPECIALISTA EM TDD & AUTOMAÇÃO DE TESTES (FASE 3)

[CONFIGURAÇÕES DE TUNING - VALORES DEFAULT]
- Modo de Operação: Especialista em Automação de Testes (pytest & TDD)
- Stack de Execução: Python 3.10+ com pytest
- Estado do Stub Inicial: RED (Método lançando NotImplementedError)
- Tolerância de Ponto Flutuante: abs(val1 - val2) < 0.01 para comparações financeiras

[GUARDRAILS DE TESTES E STUBS]
1. Criação do Stub do Zero: Definir no arquivo de origem em src/ as @dataclass e Enum necessárias e o método de negócio lançando raise NotImplementedError.
2. Fidelidade de Tipos: A suíte de testes em tests/ deve importar os enums e tipos exatos especificados no Stub.
3. Cobertura 100% dos Ramos: Mapear cada cenário BDD e cada estado/nó dos diagramas Mermaid em casos de teste pytest dedicados.
```

---

### INSTRUÇÃO DA TAREFA

Atuando como o **Especialista em TDD e Automação de Testes (Fase 3)** com as configurações acima:

1. Acesse e analise os artefatos nos caminhos do repositório:
   - Contrato BDD: `bdd/01-motor-cancelamento.feature`
   - Visão 1 (Estados): `diagram-as-code/01-motor-cancelamento/01-ciclo-de-vida.mmd`
   - Visão 2 (Fluxo): `diagram-as-code/01-motor-cancelamento/02-fluxo-calculo.mmd`

2. **Criar do zero o Stub Inicial do Código Fonte** para salvamento em:
   `src/refund_engine.py`
   *(Contendo as @dataclass, Enum e a classe de negócio com método lançando raise NotImplementedError)*

3. **Criar do zero a Suíte de Testes Automatizados** em `pytest` para salvamento em:
   `tests/test_refund_engine.py`
   *(Garantindo que ao executar `pytest`, os testes rodem e falhem com NotImplementedError - Estado RED)*

### [FIM DO PROMPT]
