# Fundamentos de Teste: Conceitos

> Fonte: Fundamentos em Testes de Software - Módulo 1, Aula 1 (TIC em Trilhas)

## 1.1 O que é software?

Software é um conjunto de instruções, dados e programas que fazem com que um computador ou dispositivo execute tarefas específicas. Ele não existe de forma física: é lógico, pode ser copiado e modificado, e é entregue para atender necessidades dos usuários ou do negócio.

**Exemplos**: aplicativos móveis, sistemas web, sistemas embarcados, jogos e ferramentas corporativas.

Software é desenvolvido por pessoas e, como qualquer produção humana, está sujeito a erros.

---

## 1.2 O que é teste de software?

Teste de software é o processo de avaliar e verificar se um software:

- Funciona conforme o esperado.
- Atende aos requisitos definidos.
- Está livre de defeitos que possam comprometer seu uso.

Não se trata apenas de executar o sistema e ver se ele "não quebra". Testar é um processo estruturado que envolve planejamento, criação de cenários, execução e análise de resultados.

### Por que testar é necessário?

- Softwares são criados por pessoas, e pessoas cometem erros.
- Um defeito que chega em produção tem custo altíssimo: financeiro, de reputação e de confiança.
- Ataques cibernéticos podem explorar vulnerabilidades não testadas, expondo dados de usuários e causando prejuízos, processos e perda de clientes.

### O que os testes não fazem

- Testes não garantem que o software é perfeito.
- Testes reduzem o risco e aumentam a confiança na qualidade.
- Teste exaustivo, ou seja, testar tudo, é impossível. Por isso, é preciso priorizar.

---

## 1.3 Objetivos e importância dos testes

### Objetivos dos testes

- **Encontrar defeitos**: identificar problemas antes que cheguem ao usuário final.
- **Avaliar a qualidade**: medir se o software atende aos requisitos funcionais e não funcionais.
- **Fornecer informações para decisões**: ajudar a equipe a decidir se o software está pronto para ser entregue.
- **Prevenir defeitos**: com testes antecipados, evitar que erros se propaguem para as fases seguintes.
- **Atender requisitos contratuais ou regulatórios**: em alguns contextos, os testes são exigidos por norma ou contrato.

### Por que os testes são importantes

| Impacto de não testar | Benefício de testar |
|---|---|
| Bugs em produção com custo alto de correção | Defeitos encontrados cedo custam menos para corrigir |
| Insatisfação e perda de confiança dos usuários | Software confiável e que funciona como esperado |
| Dano à reputação da empresa | Credibilidade e qualidade percebida pelo mercado |
| Riscos de segurança e exposição de dados | Vulnerabilidades identificadas antes do lançamento |
| Retrabalho e atrasos nos projetos | Processo mais previsível e controlado |

### Regra de 10 de Myers

A Regra de 10 de Myers mostra que o custo para corrigir um defeito tende a aumentar conforme ele é encontrado mais tarde no ciclo de desenvolvimento.

A ideia central é simples: um defeito encontrado ainda na fase de requisitos ou análise custa muito menos para corrigir do que um defeito encontrado em produção. A cada etapa posterior, o custo pode crescer cerca de 10 vezes.

| Momento em que o defeito é encontrado | Impacto no custo |
|---|---|
| Requisitos ou análise | Menor custo de correção |
| Desenvolvimento | Custo maior, mas ainda controlável |
| Testes | Custo mais alto, pois pode exigir retrabalho |
| Produção | Maior custo, com risco para usuários, negócio e reputação |

Essa regra reforça a importância de testar cedo, revisar requisitos, fazer análise estática e envolver QA desde o início do projeto.

### Quem testa?

Dependendo do nível de teste e do contexto:

- **Desenvolvedores**: testes de componente/unidade.
- **Testadores / QA**: testes de sistema, integração e aceitação.
- **Usuários finais**: testes beta e UAT.

## Revisão rápida

- Software é lógico, feito por pessoas e, portanto, sujeito a erros.
- Teste é um processo estruturado para verificar qualidade e reduzir risco.
- Testes não provam ausência de bugs, mas aumentam a confiança.
- Quanto mais cedo o defeito é encontrado, menor o custo de correção.
- Pela Regra de 10 de Myers, defeitos encontrados tarde podem custar muitas vezes mais para corrigir.
- Testar é responsabilidade compartilhada entre devs, QA e usuários.
