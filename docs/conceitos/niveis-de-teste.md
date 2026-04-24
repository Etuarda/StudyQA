# Níveis de Teste

> Fonte: Fundamentos em Testes de Software - Módulo 2 (TIC em Trilhas)

## Contexto

Os níveis de teste são um conjunto de atividades organizadas e gerenciadas que visam testar cada fase do software dentro do ciclo de vida de desenvolvimento. Cada nível tem responsabilidade e objetivos específicos, e eles são planejados para encontrar diferentes tipos de bugs em diferentes ambientes.

Os níveis seguem uma sequência: normalmente o nível anterior precisa ter sido executado antes de avançar para o próximo. Isso permite detectar e corrigir problemas o mais cedo possível.

## Pirâmide de teste

Da base ao topo, os cinco níveis principais são:

1. Teste de componente ou unitário.
2. Teste de integração de componentes.
3. Teste de integração de sistema.
4. Teste de sistema.
5. Teste de aceitação.

## Características comuns de cada nível

Cada nível é categorizado e distinguido por:

- **Objeto de teste**: o que está sendo testado naquele nível.
- **Objetivo**: o que se deseja alcançar.
- **Base de teste**: especificações, documentos ou elementos usados para criar cenários e casos de teste.
- **Defeitos e falhas**: principais bugs encontrados em cada nível.
- **Abordagem e responsabilidades**: como os testes são realizados e quem é responsável.

---

## 1. Teste de componente ou unidade

Testa cada elemento do código individualmente, sem integração com outras unidades.

**Quem executa**: o próprio desenvolvedor.

**Como funciona**: cada módulo, função ou componente é testado de forma isolada. É rápido de executar e normalmente automatizado.

### Principais objetivos

- Detectar erros precocemente para evitar que persistam nos níveis seguintes.
- Obter alta cobertura de código.
- Validar funcionalidades isoladas.
- Antecipar problemas de integração.

### Benefícios

- Melhoria da qualidade do código.
- Facilidade de identificação de defeitos.
- Facilidade de manutenção.
- Aumento da confiabilidade e eficiência do software.

### Características

| Elemento | Descrição |
|---|---|
| Objeto de teste | Funções, módulos, estruturas de código e dados |
| Objetivo do teste | Garantir que cada função ou componente funcione corretamente |
| Base de teste | Código-fonte, dados e especificações de componentes |
| Defeitos e falhas | Código e lógica incorretos, problemas no fluxo de dados e funcionalidade implementada errada |
| Abordagem | Testes automatizados, realizados pelos desenvolvedores |

---

## 2. Teste de integração

Verifica como as interfaces entre unidades, componentes ou sistemas se comunicam quando interligadas. Garante que a junção das partes não introduz erros novos.

Existem dois tipos de integração:

- **Integração de componentes**: testa a interligação de componentes entre si. Normalmente é realizada pelos desenvolvedores.
- **Integração de sistema**: verifica a interface do sistema com serviços externos, identificando falhas de comunicação ou incompatibilidades. Normalmente é realizada pela equipe de teste.

### Principais objetivos

- Identificar problemas de integração.
- Evitar custos de correção em fases posteriores.
- Reduzir riscos de falhas no sistema.
- Garantir que componentes e sistemas se integrem de forma eficiente e confiável.

### Benefícios

- Garantia da funcionalidade integrada.
- Melhoria da estabilidade do software.
- Redução de riscos e aumento de confiança na qualidade.

### Características

| Elemento | Descrição |
|---|---|
| Objeto de teste | APIs, banco de dados, módulos ou serviços interligados e interfaces |
| Objetivos do teste | Assegurar que as partes funcionem em conjunto, verificar interfaces e evitar propagação de defeitos |
| Base de teste | Especificações de interface, diagramas de sequência, arquitetura de componente/sistema e casos de uso |
| Defeitos e falhas | Incompatibilidade de interfaces, falhas de comunicação e dados incorretos |
| Abordagem | Equipe de teste ou desenvolvedores, com possibilidade de automação |

---

## 3. Teste de sistema

Avalia o sistema como um todo. Verifica se o sistema atende aos requisitos funcionais, como comportamentos e funcionalidades, e aos requisitos não funcionais, como desempenho, segurança, usabilidade e confiabilidade.

Inclui testes **end-to-end** (ponta a ponta), que simulam todas as ações do usuário desde o início até o fim do fluxo.

É o nível em que muitos bugs são identificados, por ser criterioso e abrangente.

**Quem executa**: equipe de teste e QA.

### Principais objetivos

- Validar se todos os requisitos foram implementados.
- Identificar e corrigir falhas antes da produção.
- Avaliar desempenho, segurança e usabilidade.
- Identificar defeitos de integração não encontrados anteriormente.
- Garantir funcionamento em diferentes plataformas.

### Benefícios

- Garantia de que o sistema atende às necessidades dos usuários.
- Melhoria de segurança e confiabilidade.
- Redução de falhas no ambiente de produção.
- Aumento da qualidade do sistema.

### Características

| Elemento | Descrição |
|---|---|
| Objeto de teste | Todas as funcionalidades e integrações, sistemas operacionais, configurações e dados |
| Objetivos do teste | Certificar que o software atende todos os requisitos e oferece boa experiência ao usuário |
| Base de teste | Requisitos, histórias do usuário e casos de uso |
| Defeitos e falhas | Falhas na execução de tarefas e comportamentos funcionais/não funcionais incorretos |
| Abordagem | Equipe de teste, testes funcionais e não funcionais, automação ou execução manual |

---

## 4. Teste de aceitação

Última etapa antes de disponibilizar o software para produção. Valida se o sistema atende às expectativas dos usuários finais: se é útil, eficiente e satisfatório.

### Modalidades

| Tipo | Descrição |
|---|---|
| UAT (User Acceptance Testing) | Realizado pelos usuários finais para verificar se o sistema atende suas necessidades |
| OAT (Operational Acceptance Testing) | Realizado por equipes de operações para verificar facilidade de operação e manutenção |
| CAT (Contract Acceptance Testing) | Realizado por terceiro independente para verificar conformidade com contrato |
| Teste Alfa | Grupo pequeno e restrito, normalmente pessoas da própria empresa |
| Teste Beta | Usuários externos em ambiente real, com coleta de feedback |

### Principais objetivos

- Garantir um software interativo e fácil de usar.
- Evitar falhas em produção.
- Aumentar a confiança dos usuários.

### Benefícios

- Identificação de problemas de usabilidade.
- Redução de riscos em produção.
- Feedback de clientes e usuários reais.
- Melhoria da experiência do usuário.

### Características

| Elemento | Descrição |
|---|---|
| Objeto de teste | Sistema sob teste, processos de negócio, formulários e relatórios |
| Objetivos do teste | Atender expectativas dos usuários, verificar se o software é útil, eficaz, confiável e seguro |
| Base de teste | Processos de negócio, casos de uso, documentação e procedimentos de instalação |
| Defeitos e falhas | Falhas de usabilidade, desempenho, compatibilidade ou erros funcionais |
| Abordagem | Testes manuais, por usuários reais ou grupos simulando uso real |

---

## 5. Testes complementares

Além dos cinco níveis principais, existem três testes complementares importantes.

### Teste de confirmação

Executado após a correção de um bug. O testador reproduz o passo a passo que gerou o defeito para confirmar se a correção foi eficiente. Se os casos de teste passarem sem erro, o bug é fechado. Caso a falha persista, o bug é reaberto.

### Teste de regressão

Executado após uma correção, nova funcionalidade ou mudança no código. Garante que a alteração feita pelo desenvolvedor não introduziu novos defeitos e não impactou funcionalidades existentes. Geralmente pode ser automatizado devido ao grande volume de casos de teste.

### Teste de manutenção

Executado quando o software já está em produção e precisa de alteração, como correção de falhas, melhorias ou novas versões. Antes de ser executado, é necessário analisar o grau de risco da mudança e o tamanho do sistema para preparar testes que cubram o impacto potencial.

---

## Relações com QA

- Cada nível tem um foco diferente: do código isolado até a experiência do usuário final.
- Detectar defeitos cedo, nos níveis mais baixos, custa menos do que encontrá-los em níveis avançados.
- O QA atua principalmente no teste de sistema e aceitação, mas precisa entender o contexto de todos os níveis.
- Testes de confirmação e regressão fazem parte da rotina diária de trabalho em QA.

## Revisão rápida

- **Unitário**: testa o código isolado, feito pelo dev, rápido e automatizado.
- **Integração**: testa se os componentes e sistemas se comunicam corretamente.
- **Sistema**: testa o software completo, com foco funcional, não funcional e ponta a ponta.
- **Aceitação**: validação final pelo usuário, incluindo UAT, OAT, CAT, Alfa e Beta.
- **Confirmação**: verifica se o bug foi realmente corrigido.
- **Regressão**: garante que a correção ou mudança não quebrou nada existente.
- **Manutenção**: testa alterações em sistemas que já estão em produção.
