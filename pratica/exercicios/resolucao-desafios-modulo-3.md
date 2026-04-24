# Resolução dos Desafios - Módulo 3

> Tema: tipos de teste, testes funcionais e testes caixa preta.

## Pergunta 6 - App Coliseu: cenários funcionais da tela de cadastro

### Contexto

A academia de lutas Coliseu solicitou o desenvolvimento inicial da sessão de cadastro do App Coliseu.

Campos previstos:

- Nome.
- Data de nascimento.
- CPF.
- Celular.
- Botão "Voltar".
- Botão "Próximo".

Regras de negócio:

- Todos os campos são obrigatórios.
- O campo "Nome" aceita até 40 caracteres.
- O campo "Data de nascimento" não pode aceitar alunos com menos de 6 anos.
- O campo "Celular" deve conter DDD válido, primeiro dígito `9` e os 9 números que compõem o telefone.
- Clicar em "Voltar" leva o usuário para a tela de login.
- O botão "Avançar/Próximo" só fica habilitado após todos os campos serem preenchidos.
- Clicar em "Avançar/Próximo" leva o usuário para a tela de criação de apelido e senha.

---

## Etapa 1 - Cenários de teste

### Validação de campos obrigatórios

| Cenário | Resultado esperado |
|---|---|
| Acessar a tela de cadastro sem preencher nenhum campo | Botão "Próximo" deve permanecer desabilitado |
| Preencher apenas o nome | Botão "Próximo" deve permanecer desabilitado |
| Preencher apenas a data de nascimento | Botão "Próximo" deve permanecer desabilitado |
| Preencher apenas o CPF | Botão "Próximo" deve permanecer desabilitado |
| Preencher apenas o celular | Botão "Próximo" deve permanecer desabilitado |
| Preencher nome, data e CPF, deixando celular vazio | Botão "Próximo" deve permanecer desabilitado |
| Preencher todos os campos com dados válidos | Botão "Próximo" deve ficar habilitado |
| Apagar um campo obrigatório após todos estarem preenchidos | Botão "Próximo" deve voltar a ficar desabilitado |

### Campo Nome

| Cenário | Resultado esperado |
|---|---|
| Preencher nome com 1 caractere | Campo deve aceitar, se não houver regra mínima definida |
| Preencher nome com 40 caracteres | Campo deve aceitar |
| Preencher nome com 41 caracteres | Sistema deve impedir o 41º caractere ou exibir validação |
| Preencher nome com letras e espaços | Campo deve aceitar |
| Preencher nome com números | Deve haver validação definida; se aceitar, a regra está incompleta |
| Preencher nome com caracteres especiais | Deve haver validação definida; se aceitar, a regra está incompleta |
| Preencher nome apenas com espaços | Sistema deve considerar inválido |

### Campo Data de nascimento

| Cenário | Resultado esperado |
|---|---|
| Informar aluno com 6 anos completos | Cadastro deve ser permitido |
| Informar aluno com 5 anos | Cadastro não deve ser permitido |
| Informar aluno que fará 6 anos amanhã | Cadastro não deve ser permitido |
| Informar aluno que fez 6 anos hoje | Cadastro deve ser permitido |
| Informar data futura | Sistema deve bloquear |
| Informar data inválida, como 31/02/2020 | Sistema deve bloquear |
| Deixar data vazia | Botão "Próximo" deve permanecer desabilitado |
| Informar data em formato diferente do esperado | Sistema deve bloquear ou aplicar máscara |

### Campo CPF

| Cenário | Resultado esperado |
|---|---|
| Deixar CPF vazio | Botão "Próximo" deve permanecer desabilitado |
| Informar CPF com 11 dígitos | Sistema deve aceitar, se não houver outra validação definida |
| Informar CPF com menos de 11 dígitos | Sistema deve bloquear |
| Informar CPF com mais de 11 dígitos | Sistema deve bloquear |
| Informar CPF com letras | Sistema deve bloquear |
| Informar CPF com caracteres especiais fora da máscara | Sistema deve bloquear ou aplicar máscara |
| Informar CPF inválido pelos dígitos verificadores | Regra não foi definida; deve ser esclarecida com o cliente |
| Informar CPF já cadastrado | Regra não foi definida; deve ser esclarecida com o cliente |

### Campo Celular

| Cenário | Resultado esperado |
|---|---|
| Deixar celular vazio | Botão "Próximo" deve permanecer desabilitado |
| Informar DDD válido e número com 9 dígitos iniciando em 9 | Sistema deve aceitar |
| Informar DDD inválido | Sistema deve bloquear |
| Informar número sem DDD | Sistema deve bloquear |
| Informar número com DDD válido, mas sem iniciar com 9 | Sistema deve bloquear |
| Informar número com menos de 9 dígitos após o DDD | Sistema deve bloquear |
| Informar número com mais de 9 dígitos após o DDD | Sistema deve bloquear |
| Informar letras no celular | Sistema deve bloquear |
| Informar caracteres especiais fora da máscara | Sistema deve bloquear ou aplicar máscara |

### Botão Voltar

| Cenário | Resultado esperado |
|---|---|
| Clicar em "Voltar" com campos vazios | Usuário deve ser levado para a tela de login |
| Clicar em "Voltar" com campos preenchidos | Usuário deve ser levado para a tela de login |
| Clicar em "Voltar" após preencher parcialmente o cadastro | Usuário deve ser levado para a tela de login |

### Botão Próximo / Avançar

| Cenário | Resultado esperado |
|---|---|
| Todos os campos vazios | Botão deve ficar desabilitado |
| Pelo menos um campo obrigatório vazio | Botão deve ficar desabilitado |
| Todos os campos preenchidos com dados válidos | Botão deve ficar habilitado |
| Clicar em "Próximo" com dados válidos | Usuário deve ir para a tela de criação de apelido e senha |
| Clicar em "Próximo" com algum dado inválido | Sistema deve impedir avanço e indicar o campo inválido |

---

## Etapa 2 - Por que os cenários ajudam os desenvolvedores

A identificação dos cenários antes do desenvolvimento ajuda os desenvolvedores porque transforma as regras de negócio em comportamentos esperados e testáveis.

Com os cenários, a equipe de desenvolvimento consegue:

- Entender melhor o que cada campo deve aceitar ou bloquear.
- Implementar validações com menos ambiguidade.
- Prever mensagens de erro e estados de tela.
- Evitar retrabalho, pois problemas de regra são identificados antes da implementação.
- Criar testes unitários e validações de front-end/back-end com base nos cenários.
- Alinhar o comportamento esperado com QA, produto e cliente.

Isso reforça a ideia de teste antecipado: quanto mais cedo uma dúvida ou defeito é identificado, menor tende a ser o custo de correção.

---

## Etapa 3 - Importância de levantar cenários funcionais antes do desenvolvimento

Levantar cenários funcionais antes do desenvolvimento é importante porque permite validar se as regras fazem sentido antes de o código ser criado.

Essa prática ajuda a:

- Reduzir falhas de interpretação dos requisitos.
- Identificar regras incompletas, contraditórias ou ambíguas.
- Melhorar a comunicação entre QA, desenvolvimento e cliente.
- Orientar a implementação de campos, máscaras, mensagens e validações.
- Aumentar a cobertura dos testes.
- Evitar que bugs simples cheguem às fases finais do projeto.

Em resumo, os cenários funcionais servem como uma ponte entre o requisito escrito e o comportamento esperado do sistema.

---

## Etapa 4 - Erros ou ambiguidades encontrados na documentação

Foram identificados pontos que podem gerar bugs ou dúvidas durante o desenvolvimento:

| Ponto identificado | Risco |
|---|---|
| A documentação cita o botão "Próximo", mas depois usa "Avançar" | Pode gerar inconsistência no nome do botão na interface |
| A frase "não pode aceitar alunos com menos 6 anos" está incompleta | O correto seria "menos de 6 anos" |
| O campo CPF não tem regra de formato, máscara, validação de dígitos ou unicidade | O sistema pode aceitar CPFs inválidos ou duplicados |
| O campo Nome só define limite máximo, mas não define caracteres permitidos | O sistema pode aceitar números, símbolos ou apenas espaços |
| O campo Celular fala em DDD válido, mas não informa quais DDDs devem ser aceitos | Pode haver divergência na validação |
| Não há definição de mensagens de erro | Usuário pode não entender por que o cadastro não avança |

### Resposta da atividade

Você realizou essa atividade?

**SIM**

---

# Pergunta 7 - Sistema de inscrições de handebol

## Contexto

A Federação Internacional de Handebol solicitou um sistema para classificar pessoas inscritas em categorias de acordo com idade e gênero.

Campos do sistema:

- Título.
- Campo idade.
- Campo gênero.
- Botão "Verificar categoria".
- Informação da categoria.

Regra principal:

- A idade mínima para inscrição é de 8 anos.
- A categoria depende da faixa etária e do gênero informado.

---

## Etapa 1 - Cenários de testes caixa preta

### Validações gerais

| Cenário | Resultado esperado |
|---|---|
| Informar idade menor que 8 anos | Sistema deve informar que a inscrição não é permitida |
| Informar idade igual a 8 anos | Sistema deve classificar como Mini |
| Deixar idade vazia | Sistema deve solicitar preenchimento da idade |
| Informar letras no campo idade | Sistema deve bloquear ou exibir erro |
| Informar idade negativa | Sistema deve bloquear |
| Informar idade decimal | Sistema deve bloquear ou solicitar idade inteira |
| Deixar gênero vazio | Sistema deve solicitar seleção/preenchimento do gênero |
| Informar idade válida e gênero válido | Sistema deve exibir a categoria correta |

### Categorias sem separação por gênero

| Cenário | Resultado esperado |
|---|---|
| Idade 8 | Categoria Mini |
| Idade 9 | Categoria Mini |
| Idade 10 | Categoria Mini |
| Idade 11 | Categoria Mirim |
| Idade 12 | Categoria Mirim |
| Idade 13 | Categoria Infantil |
| Idade 14 | Categoria Infantil |
| Idade 15 | Categoria Cadete |
| Idade 16 | Categoria Cadete |
| Idade 17 | Categoria Juvenil |
| Idade 18 | Categoria Juvenil |

### Categorias femininas

| Cenário | Resultado esperado |
|---|---|
| Idade 19 e gênero feminino | Categoria Júnior Feminino |
| Idade 20 e gênero feminino | Categoria Júnior Feminino |
| Idade 21 e gênero feminino | Categoria Adulto Feminino |
| Idade maior que 21 e gênero feminino | Categoria Adulto Feminino |

### Categorias masculinas

| Cenário | Resultado esperado |
|---|---|
| Idade 19 e gênero masculino | Categoria Júnior Masculino |
| Idade 20 e gênero masculino | Categoria Júnior Masculino |
| Idade 21 e gênero masculino | Categoria Júnior Masculino |
| Idade 22 e gênero masculino | Categoria Adulto Masculino |
| Idade maior que 22 e gênero masculino | Categoria Adulto Masculino |

### Testes de borda

| Cenário | Resultado esperado |
|---|---|
| Idade 7 | Inscrição não permitida |
| Idade 8 | Mini |
| Idade 10 | Mini |
| Idade 11 | Mirim |
| Idade 12 | Mirim |
| Idade 13 | Infantil |
| Idade 14 | Infantil |
| Idade 15 | Cadete |
| Idade 16 | Cadete |
| Idade 17 | Juvenil |
| Idade 18 | Juvenil |
| Idade 19 feminino | Júnior Feminino |
| Idade 19 masculino | Júnior Masculino |
| Idade 20 feminino | Júnior Feminino |
| Idade 20 masculino | Júnior Masculino |
| Idade 21 feminino | Adulto Feminino |
| Idade 21 masculino | Júnior Masculino |
| Idade 22 feminino | Adulto Feminino |
| Idade 22 masculino | Adulto Masculino |

---

## Etapa 2 - Testes funcionais

Sistema indicado na atividade:

<https://testecaixapreta.w3spaces.com/TIC-FTS.html>

Como resolução do desafio, os testes funcionais devem ser executados informando idade e gênero, clicando em "Verificar categoria" e comparando a categoria exibida com o resultado esperado.

### Casos principais para execução

| Teste | Dados de entrada | Resultado esperado |
|---|---|---|
| Idade abaixo da mínima | 7 anos, qualquer gênero | Inscrição não permitida |
| Limite mínimo | 8 anos, qualquer gênero | Mini |
| Transição Mini -> Mirim | 10 e 11 anos | 10 = Mini; 11 = Mirim |
| Transição Mirim -> Infantil | 12 e 13 anos | 12 = Mirim; 13 = Infantil |
| Transição Infantil -> Cadete | 14 e 15 anos | 14 = Infantil; 15 = Cadete |
| Transição Cadete -> Juvenil | 16 e 17 anos | 16 = Cadete; 17 = Juvenil |
| Transição Juvenil -> Júnior | 18 e 19 anos | 18 = Juvenil; 19 = Júnior conforme gênero |
| Feminino 20 anos | 20 anos, feminino | Júnior Feminino |
| Feminino 21 anos | 21 anos, feminino | Adulto Feminino |
| Masculino 21 anos | 21 anos, masculino | Júnior Masculino |
| Masculino 22 anos | 22 anos, masculino | Adulto Masculino |

### Registro de bugs

Durante a execução dos testes, caso o sistema retorne uma categoria diferente da esperada, o bug deve ser registrado neste formato:

```text
Cenário:
Dados usados:
Resultado esperado:
Resultado obtido:
Bug:
```

### Possível ponto de atenção na regra

A documentação informa as categorias:

- Júnior Feminino: 19 a 20 anos.
- Júnior Masculino: 19 a 21 anos.
- Adulto Feminino: 21 anos em diante.
- Adulto Masculino: 22 anos em diante.

Isso significa que a idade de 21 anos muda de categoria conforme o gênero:

- 21 anos feminino: Adulto Feminino.
- 21 anos masculino: Júnior Masculino.

Esse é um caso de borda importante e deve ser testado com atenção.

### Resposta da atividade

Você realizou essa atividade?

**SIM**
