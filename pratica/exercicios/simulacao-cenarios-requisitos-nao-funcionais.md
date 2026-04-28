# Simulação de Cenários - Requisitos Não Funcionais

> Tema: criação de casos de teste para requisitos não funcionais, com foco em segurança e usabilidade.

## Objetivo

Praticar a identificação e escrita de cenários de teste para requisitos não funcionais, avaliando como o sistema se comporta em relação à segurança, usabilidade e qualidade da experiência do usuário.

## Contexto

Sistema simulado: plataforma de estudos QAStudy.

A plataforma permite que estudantes acessem materiais de estudo, consultem conteúdos por módulo e acompanhem exercícios práticos. Para esta simulação, o foco será a tela de login e a área de consulta de conteúdos.

Funcionalidades consideradas:

- Login com e-mail e senha.
- Recuperação de senha.
- Listagem de conteúdos por módulo.
- Busca por título ou palavra-chave.
- Acesso a materiais de estudo.

Requisitos não funcionais avaliados:

- Segurança.
- Usabilidade.
- Acessibilidade básica.
- Clareza de mensagens.
- Prevenção de erro humano.

---

## Requisitos não funcionais simulados

### Segurança

| Código | Requisito |
|---|---|
| RNF-SEG-01 | O sistema não deve informar se o e-mail ou a senha está incorreto separadamente. |
| RNF-SEG-02 | O campo de senha deve ocultar os caracteres digitados. |
| RNF-SEG-03 | Após várias tentativas inválidas de login, o sistema deve aplicar algum controle de proteção. |
| RNF-SEG-04 | A recuperação de senha não deve expor se um e-mail está cadastrado ou não. |
| RNF-SEG-05 | Páginas internas não devem ser acessadas sem autenticação. |

### Usabilidade

| Código | Requisito |
|---|---|
| RNF-USA-01 | O usuário deve entender facilmente quais campos são obrigatórios. |
| RNF-USA-02 | Mensagens de erro devem ser claras, objetivas e próximas ao campo relacionado. |
| RNF-USA-03 | O sistema deve permitir navegação por teclado nos campos e botões principais. |
| RNF-USA-04 | A busca deve retornar feedback quando não encontrar resultados. |
| RNF-USA-05 | O conteúdo deve ser legível em tela desktop e mobile. |

---

## Cenários de teste - Segurança

### Tela de login

| Cenário | Passos | Resultado esperado |
|---|---|---|
| Login com e-mail válido e senha incorreta | Informar e-mail cadastrado, digitar senha incorreta e clicar em "Entrar" | Sistema deve negar acesso e exibir mensagem genérica, sem revelar qual dado está errado |
| Login com e-mail inexistente | Informar e-mail não cadastrado, digitar qualquer senha e clicar em "Entrar" | Sistema deve exibir a mesma mensagem usada para credenciais inválidas |
| Campo senha protegido | Digitar uma senha no campo "Senha" | Caracteres devem aparecer mascarados |
| Várias tentativas inválidas | Errar login várias vezes seguidas | Sistema deve aplicar proteção, como bloqueio temporário, captcha ou limite de tentativas |
| Acesso direto a página interna | Tentar abrir a URL de conteúdos sem estar logado | Sistema deve redirecionar para login ou bloquear o acesso |

### Recuperação de senha

| Cenário | Passos | Resultado esperado |
|---|---|---|
| Recuperar senha com e-mail cadastrado | Informar e-mail válido na tela de recuperação | Sistema deve exibir mensagem neutra, como "Se o e-mail existir, enviaremos instruções" |
| Recuperar senha com e-mail não cadastrado | Informar e-mail inexistente | Sistema deve exibir a mesma mensagem neutra |
| Link de recuperação expirado | Tentar acessar link antigo de redefinição | Sistema deve bloquear a ação e orientar solicitar novo link |
| Nova senha fraca | Informar senha muito curta ou previsível | Sistema deve impedir alteração e explicar os critérios mínimos |

---

## Cenários de teste - Usabilidade

### Formulário de login

| Cenário | Passos | Resultado esperado |
|---|---|---|
| Campos obrigatórios vazios | Clicar em "Entrar" sem preencher e-mail e senha | Sistema deve indicar quais campos precisam ser preenchidos |
| E-mail em formato inválido | Digitar texto sem formato de e-mail e tentar entrar | Sistema deve informar que o formato do e-mail é inválido |
| Erro próximo ao campo | Deixar senha vazia e tentar entrar | Mensagem deve aparecer próxima ao campo de senha |
| Navegação por teclado | Usar Tab para navegar entre e-mail, senha, recuperação e botão entrar | Foco deve seguir ordem lógica e todos os controles devem ser acessíveis |
| Botão de mostrar senha | Acionar opção de visualizar senha, se existir | Usuário deve conseguir conferir a senha e ocultá-la novamente |

### Busca de conteúdos

| Cenário | Passos | Resultado esperado |
|---|---|---|
| Buscar conteúdo existente | Pesquisar por "teste funcional" | Sistema deve retornar conteúdos relacionados |
| Buscar termo inexistente | Pesquisar por termo sem resultado | Sistema deve informar que nenhum conteúdo foi encontrado |
| Busca com campo vazio | Clicar em buscar sem digitar nada | Sistema deve orientar o usuário ou manter a lista completa de forma previsível |
| Busca com letras maiúsculas e minúsculas | Pesquisar o mesmo termo com variações de capitalização | Resultado deve ser consistente |
| Limpar busca | Apagar o termo pesquisado | Lista deve voltar ao estado inicial ou exibir todos os conteúdos disponíveis |

### Leitura e adaptação de tela

| Cenário | Passos | Resultado esperado |
|---|---|---|
| Acessar conteúdo em desktop | Abrir uma nota teórica em tela grande | Texto deve ser legível, organizado e sem quebras estranhas |
| Acessar conteúdo em mobile | Abrir uma nota teórica em tela pequena | Conteúdo deve se adaptar sem corte horizontal |
| Títulos e seções | Navegar por uma página longa | Títulos devem ajudar o usuário a entender a estrutura do conteúdo |
| Links e botões | Passar pelos links principais | Elementos clicáveis devem ser fáceis de identificar |
| Contraste visual | Ler mensagens e botões importantes | Texto deve ter contraste suficiente em relação ao fundo |

---

## Casos de teste detalhados

### CT-SEG-01 - Mensagem genérica no login inválido

**Objetivo:** verificar se o sistema evita exposição de informação sensível durante falha de login.

**Pré-condição:** tela de login disponível.

**Dados de teste:**

- E-mail cadastrado com senha incorreta.
- E-mail inexistente com qualquer senha.

**Passos:**

1. Acessar a tela de login.
2. Informar um e-mail cadastrado e senha incorreta.
3. Clicar em "Entrar".
4. Registrar a mensagem exibida.
5. Repetir o teste com um e-mail inexistente.
6. Comparar as mensagens.

**Resultado esperado:** as mensagens devem ser iguais ou igualmente genéricas, sem indicar se o e-mail existe ou se apenas a senha está errada.

**Risco coberto:** enumeração de usuários.

---

### CT-SEG-02 - Bloqueio de página interna sem autenticação

**Objetivo:** validar se conteúdos internos não ficam acessíveis sem login.

**Pré-condição:** usuário não autenticado.

**Passos:**

1. Abrir o navegador em janela anônima.
2. Informar diretamente a URL de uma página interna.
3. Pressionar Enter.

**Resultado esperado:** sistema deve bloquear o acesso e redirecionar para login ou exibir mensagem de acesso não autorizado.

**Risco coberto:** acesso indevido a conteúdo restrito.

---

### CT-USA-01 - Clareza de campos obrigatórios

**Objetivo:** verificar se o usuário entende o que precisa preencher.

**Pré-condição:** tela de login disponível.

**Passos:**

1. Acessar a tela de login.
2. Observar os campos disponíveis.
3. Clicar em "Entrar" sem preencher nenhum campo.

**Resultado esperado:** o sistema deve indicar claramente que e-mail e senha são obrigatórios.

**Risco coberto:** erro humano por falta de orientação.

---

### CT-USA-02 - Busca sem resultados

**Objetivo:** verificar se a busca oferece feedback útil quando não encontra conteúdos.

**Pré-condição:** área de conteúdos disponível.

**Passos:**

1. Acessar a área de conteúdos.
2. Pesquisar um termo inexistente, como "xyzconteudoinvalido".
3. Observar o retorno da interface.

**Resultado esperado:** o sistema deve informar que nenhum resultado foi encontrado e permitir nova busca sem confundir o usuário.

**Risco coberto:** frustração do usuário e abandono da tarefa.

---

## Registro de evidências

Durante a execução dos testes, registrar:

- Tela ou fluxo testado.
- Dados utilizados.
- Resultado esperado.
- Resultado obtido.
- Captura de tela, quando aplicável.
- Observações sobre dificuldade, ambiguidade ou risco encontrado.

Modelo de registro:

```text
Caso de teste:
Data da execução:
Ambiente:
Dados usados:
Resultado esperado:
Resultado obtido:
Status:
Evidência:
Observações:
```

---

## Aprendizados

- Requisitos não funcionais também precisam virar cenários testáveis.
- Segurança deve evitar exposição de informações, mesmo em mensagens simples.
- Usabilidade reduz erro humano e melhora a experiência real do usuário.
- Um sistema pode funcionar corretamente e ainda assim ter baixa qualidade se for inseguro, confuso ou difícil de usar.
- Testes não funcionais ajudam a validar como o produto se comporta, não apenas o que ele faz.

## Relação com QA

Esta prática reforça que qualidade de software vai além de validar funcionalidades. O trabalho de QA também envolve observar riscos de segurança, clareza da interface, acessibilidade, prevenção de erros e adequação ao uso.

