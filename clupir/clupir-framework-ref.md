# Guia Rápido: O Modelo CLUPIR na Arquitetura de Software

O **CLUPIR** (*Classification model for modeling languages*) é um modelo científico de taxonomia publicado na revista IEEE Access (Seabra & Silva, 2025). Seu objetivo é permitir a escolha objetiva e fundamentada de Linguagens de Modelagem Visual baseando-se em 4 grupos e 17 aspectos:

| Grupo | Aspecto Chave | Aplicação na Seleção de Diagramas |
| :--- | :--- | :--- |
| **Language & Resources** | **Types of Model** | Classifica a necessidade em *Informacional* (dados), *Comportamental* (fluxos/estados) ou *Estrutural* (componentes). |
| **Relationship with the User** | **Semiotic Clarity** | Avalia se a notação evita ambiguidades como *Overload* (um símbolo para múltiplas coisas) ou *Redundancy*. |
| | **Complexity Management** | Utiliza *Modularization* (pacotes) ou *Decomposition* (hierarquias) para evitar diagramas gigantescos. |
| | **Graphic Economy** | Compara a *Graphic Complexity* (vocabulário total da linguagem) com a *Practical Complexity* (número real de símbolos necessários. |
| | **Dual Coding** | Combina elementos gráficos com texto explícito para reduzir interpretações dúbias. |
| **Integration Capability** | **Executable Architecture** | Prioriza notações de *Diagram-as-Code* (Mermaid.js/PlantUML) integráveis a repositórios Git e pipelines de IA. |
| **Process Support** | **Activity of SE Process** | Conecta o diagrama diretamente às etapas de Requisitos e Construção (SWEBOK). |