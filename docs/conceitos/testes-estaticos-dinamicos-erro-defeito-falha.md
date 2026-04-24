# Testes Dinâmicos e Estáticos, Erro, Defeito, Falha e Causa Raiz

> Fonte: Fundamentos em Testes de Software - Módulo 1, Aula 2 (TIC em Trilhas)

## 2.1 Testes dinâmicos versus testes estáticos

### Teste dinâmico

É o teste que **executa o software**. O código é rodado com entradas específicas para observar se o comportamento está correto.

- Requer que o software esteja em um estado executável.
- Exemplos: testes de componente, integração, sistema e aceitação.

### Teste estático

É o teste que **não executa o software**. O código, os documentos ou os artefatos são analisados sem rodar a aplicação.

- Pode ser feito desde as fases iniciais do projeto.
- Exemplos: revisão de requisitos, inspeção de código, análise de documentos e revisão de design.

### Comparação

| Aspecto | Dinâmico | Estático |
|---|---|---|
| Executa o software? | Sim | Não |
| Quando pode ser feito? | Com o software funcionando | Desde o início do projeto |
| O que analisa? | Comportamento em execução | Código, documentos e artefatos |
| Exemplos | Testes funcionais e de regressão | Revisão de código e inspeção |
| Quem realiza? | Testadores e desenvolvedores | Desenvolvedores, QA e revisores |

---

## 2.2 Diferença entre conceitos: erro, defeito e falha

Esses três conceitos são frequentemente confundidos. Cada um representa um momento diferente no ciclo de introdução de um problema no software.

### Erro (engano humano)

**Definição**: ação humana que produz um resultado incorreto.

- É a causa inicial de tudo que vem depois.
- Acontece quando uma pessoa comete um equívoco: interpreta mal um requisito, escreve lógica errada ou digita algo incorreto.
- O erro existe na **intenção ou no raciocínio** de quem produziu o artefato.

**Exemplos**:

- Desenvolvedor interpreta errado um requisito e implementa a lógica invertida.
- Analista escreve um requisito ambíguo que será mal interpretado.

---

### Defeito (bug)

**Definição**: resultado de um erro humano inserido em um artefato do software, como código, documentação ou caso de teste.

- O defeito existe no **artefato**.
- Pode estar presente no código e nunca ser ativado se o fluxo que o contém nunca for executado.
- Também chamado de *bug*, falha latente ou não conformidade.

**Exemplos**:

- Linha de código com lógica invertida (`if >` em vez de `if <`).
- Campo de formulário que aceita valores negativos quando não deveria.

---

### Falha

**Definição**: comportamento incorreto **observado** quando o software é executado e o defeito é ativado.

- A falha é o **efeito visível** de um defeito em execução.
- Nem todo defeito causa falha imediatamente, pois depende de quando o código é exercitado.

**Exemplos**:

- Aplicativo trava ao tentar salvar um registro com valor negativo.
- Cálculo de desconto retorna valor errado para o usuário.

---

### Resumo da relação

```text
Erro (pessoa) -> gera -> Defeito (código/documento) -> quando executado -> Falha (comportamento)
```

| Conceito | Origem | Onde está | Quando é percebido |
|---|---|---|---|
| Erro | Ser humano | Na mente / intenção | No momento do engano |
| Defeito | Resultado do erro | No artefato, como código ou documento | Quando analisado ou testado |
| Falha | Defeito ativado | No comportamento do sistema | Durante a execução |

---

## 2.3 Causa raiz e seus efeitos

### O que é causa raiz?

Causa raiz é a origem fundamental de um defeito. Identificar a causa raiz é essencial para **prevenir** que o mesmo tipo de problema se repita, não apenas corrigir o sintoma imediato.

### Por que identificar a causa raiz?

- Corrigir apenas o sintoma, ou seja, a falha visível, não impede que o problema volte.
- Entender a causa raiz orienta melhorias no processo, nas ferramentas e na comunicação da equipe.

### Exemplos de causas raiz comuns

| Causa raiz | Efeito no produto |
|---|---|
| Requisito mal escrito ou ambíguo | Funcionalidade implementada diferente do esperado |
| Comunicação falha entre dev e analista | Comportamento errado em casos de uso específicos |
| Falta de revisão de código | Defeitos que poderiam ter sido pegos antes dos testes |
| Pressão de prazo | Código produzido com menos cuidado, mais propenso a erros |
| Falta de testes em um fluxo específico | Defeito permanece latente até chegar ao usuário |

### Causa raiz no contexto de QA

O QA contribui para a análise de causa raiz ao:

- Documentar detalhadamente os bugs encontrados.
- Identificar padrões de defeitos recorrentes.
- Participar de retrospectivas e análises pós-incidente.
- Sugerir melhorias no processo de desenvolvimento com base nos dados de teste.

## Revisão rápida

- **Estático**: analisa sem executar; pode começar antes do código existir.
- **Dinâmico**: executa o software e observa o comportamento.
- **Erro**: engano humano, na mente ou intenção de quem produziu.
- **Defeito**: o erro inserido no artefato, como código ou documento; pode nunca causar falha se não for exercitado.
- **Falha**: o defeito sendo ativado em execução, visível ao usuário ou ao testador.
- **Causa raiz**: origem real do problema; identificar e corrigir a causa raiz previne recorrência.
