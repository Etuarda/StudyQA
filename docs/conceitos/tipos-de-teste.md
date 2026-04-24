# Tipos de Teste e suas Aplicações

> Fonte: Fundamentos em Testes de Software - Módulo 3 (TIC em Trilhas)

## Contexto

No módulo anterior, o foco estava nos **níveis de teste**, ou seja, em quando e em qual camada do software os testes acontecem. Neste módulo, o foco muda para os **tipos de teste**, que representam grupos de atividades relacionadas a características específicas de qualidade.

Um mesmo tipo de teste pode aparecer em diferentes níveis. Por exemplo, testes funcionais podem ser aplicados em teste de componente, integração, sistema e aceitação.

Neste módulo, os principais tipos abordados são:

1. Testes funcionais.
2. Testes não funcionais.
3. Teste caixa preta.
4. Teste caixa branca.

---

## Aula 1 - Teste funcional e não funcional

### 1.1 Testes funcionais

Testes funcionais verificam **o que o sistema faz**. Eles avaliam se as funcionalidades implementadas estão de acordo com requisitos, regras de negócio, histórias de usuário ou critérios de aceite.

O foco está no comportamento esperado do software:

- O sistema executa a ação correta?
- A regra de negócio foi respeitada?
- A entrada gera a saída esperada?
- O fluxo do usuário funciona como deveria?

### Exemplos de testes funcionais

- Validar login com usuário e senha corretos.
- Verificar se uma compra calcula o valor total corretamente.
- Confirmar se um cadastro salva os dados obrigatórios.
- Testar se uma mensagem de erro aparece quando um campo obrigatório fica vazio.

### Características

| Elemento | Descrição |
|---|---|
| Foco | Funcionalidades e regras de negócio |
| Base de teste | Requisitos, histórias de usuário, casos de uso e critérios de aceite |
| Pergunta principal | O sistema faz o que deveria fazer? |
| Resultado esperado | Comportamento correto de acordo com a especificação |

### Relação com QA

Em QA, os testes funcionais ajudam a validar se o produto atende ao que foi solicitado e se os fluxos principais do usuário funcionam corretamente.

---

### 1.2 Testes não funcionais

Testes não funcionais verificam **como o sistema se comporta**. Eles avaliam características de qualidade que vão além da funcionalidade em si.

O foco está em atributos como:

- Desempenho.
- Segurança.
- Usabilidade.
- Confiabilidade.
- Compatibilidade.
- Manutenibilidade.

### Exemplos de testes não funcionais

- Verificar se uma página carrega em tempo aceitável.
- Avaliar se o sistema suporta muitos usuários ao mesmo tempo.
- Testar se dados sensíveis estão protegidos.
- Validar se o sistema funciona em diferentes navegadores ou dispositivos.
- Avaliar se a interface é fácil de entender e utilizar.

### Características

| Elemento | Descrição |
|---|---|
| Foco | Qualidade do comportamento do sistema |
| Base de teste | Requisitos não funcionais, normas, métricas e expectativas de qualidade |
| Pergunta principal | O sistema se comporta bem nas condições esperadas? |
| Resultado esperado | Software eficiente, seguro, confiável, usável e compatível |

### Relação com QA

Testes não funcionais ampliam a visão de qualidade. Um sistema pode ter funcionalidades corretas, mas ainda falhar se for lento, inseguro, difícil de usar ou incompatível com o ambiente esperado.

---

## Aula 2 - Teste caixa preta e caixa branca

### 2.1 Teste caixa preta

Teste caixa preta é uma técnica em que o testador avalia o sistema **sem conhecer sua estrutura interna**. O foco está nas entradas, saídas e comportamento observado.

Nesse tipo de teste, o testador não precisa saber como o código foi implementado. Ele usa requisitos, regras de negócio e critérios de aceite para validar se o sistema responde corretamente.

### Exemplos de teste caixa preta

- Informar login e senha válidos e verificar se o acesso é permitido.
- Informar senha incorreta e verificar se o sistema exibe erro.
- Inserir valor inválido em um campo e validar a mensagem apresentada.
- Testar regras de cálculo sem analisar o código que faz o cálculo.

### Características

| Elemento | Descrição |
|---|---|
| Foco | Comportamento externo do sistema |
| Visão do testador | Usuário ou consumidor da funcionalidade |
| Base de teste | Requisitos, regras de negócio, casos de uso e critérios de aceite |
| Conhecimento do código | Não é necessário |
| Muito usado em | Testes funcionais, sistema e aceitação |

### Vantagens

- Aproxima o teste da experiência real do usuário.
- Ajuda a validar regras de negócio.
- Pode ser realizado mesmo sem acesso ao código.
- É útil para encontrar divergências entre requisito e comportamento entregue.

---

### 2.2 Teste caixa branca

Teste caixa branca é uma técnica em que o testador avalia o sistema **com conhecimento da estrutura interna**. O foco está no código, nos caminhos lógicos, nas condições e no fluxo interno da aplicação.

Nesse tipo de teste, é importante entender como o software foi construído.

### Exemplos de teste caixa branca

- Testar diferentes caminhos de decisão em um `if`.
- Validar se todos os ramos de uma função foram exercitados.
- Verificar tratamento de exceções.
- Medir cobertura de código.
- Criar testes unitários para funções específicas.

### Características

| Elemento | Descrição |
|---|---|
| Foco | Estrutura interna, lógica e fluxo do código |
| Visão do testador | Técnica, próxima da implementação |
| Base de teste | Código-fonte, arquitetura, lógica interna e estrutura de dados |
| Conhecimento do código | Necessário |
| Muito usado em | Testes unitários, componente e revisão técnica |

### Vantagens

- Ajuda a encontrar problemas internos que não aparecem facilmente pela interface.
- Permite medir cobertura de código.
- Fortalece testes unitários e de componente.
- Apoia a identificação de caminhos não testados.

---

## Comparação rápida

| Tipo | Pergunta principal | Foco |
|---|---|---|
| Funcional | O sistema faz o que deveria fazer? | Funcionalidades e regras de negócio |
| Não funcional | O sistema se comporta bem? | Qualidade, desempenho, segurança e usabilidade |
| Caixa preta | A entrada gera a saída esperada? | Comportamento externo |
| Caixa branca | A lógica interna foi exercitada corretamente? | Código e estrutura interna |

## Relações com QA

- Tipos de teste podem ser aplicados em diferentes níveis de teste.
- Testes funcionais validam comportamento esperado.
- Testes não funcionais avaliam atributos de qualidade.
- Caixa preta aproxima o teste da visão do usuário.
- Caixa branca aproxima o teste da visão técnica do código.

## Revisão rápida

- **Teste funcional**: verifica se a funcionalidade faz o que foi especificado.
- **Teste não funcional**: verifica como o sistema se comporta em qualidade, desempenho, segurança e usabilidade.
- **Caixa preta**: testa entradas e saídas sem olhar o código.
- **Caixa branca**: testa a estrutura interna e a lógica do código.
- Tipos de teste não substituem níveis de teste; eles se complementam.
