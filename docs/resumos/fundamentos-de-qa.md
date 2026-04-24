# Fundamentos de QA

## Visão geral

QA envolve mais do que encontrar bugs. O objetivo é contribuir para que o software entregue valor com qualidade, considerando funcionamento, risco, experiência do usuário e capacidade de evolução.

## 7 princípios do teste

1. Testes mostram a presença de defeitos, mas não provam ausência total deles.
2. Teste exaustivo é impossível, então é preciso priorizar.
3. Testar cedo reduz custo e retrabalho.
4. Defeitos tendem a se concentrar em poucos pontos.
5. Repetir sempre os mesmos testes reduz a chance de encontrar novos defeitos.
6. A estratégia de teste depende do contexto.
7. Poucos bugs não significam sucesso se o produto não atende à necessidade real.

## Características de qualidade do software

Um software de qualidade deve ser:

- **Funcional**: entrega corretamente o que foi especificado.
- **Confiável**: mantém comportamento estável e previsível.
- **Eficiente**: usa bem tempo, memória, processamento e rede.
- **Compatível**: funciona nos ambientes e integrações esperadas.
- **Seguro**: protege dados, acessos e operações.
- **Usável**: é fácil de entender, aprender e utilizar.
- **Flexível**: permite adaptações e evolução.
- **De fácil manutenção**: pode ser corrigido, testado e melhorado com menor esforço.

## O que isso significa na prática

- QA não valida apenas se a funcionalidade existe, mas se ela atende bem ao uso esperado.
- O teste deve ser guiado por risco, contexto e prioridade.
- Desempenho, segurança, compatibilidade e usabilidade também fazem parte da qualidade.
- Um sistema fácil de manter tende a evoluir melhor e acumular menos problemas no tempo.

## Regra de 10 de Myers

A Regra de 10 de Myers explica que o custo de corrigir um defeito aumenta conforme ele é descoberto mais tarde no ciclo de desenvolvimento.

Em termos práticos:

- Corrigir um problema nos requisitos custa menos.
- Corrigir durante o desenvolvimento já custa mais.
- Corrigir durante os testes pode exigir retrabalho.
- Corrigir em produção é o cenário mais caro, pois pode afetar usuários, reputação e negócio.

Resumo da ideia: quanto mais cedo o defeito é encontrado, menor tende a ser o custo de correção.

## Tipos de teste

Tipos de teste são grupos de atividades relacionadas a características específicas de qualidade. Eles podem ser aplicados em diferentes níveis de teste.

- **Funcional**: verifica se o sistema faz o que deveria fazer.
- **Não funcional**: verifica como o sistema se comporta em desempenho, segurança, usabilidade, confiabilidade e outros atributos.
- **Caixa preta**: testa entradas, saídas e comportamento externo sem olhar o código.
- **Caixa branca**: testa a estrutura interna, lógica, caminhos e condições do código.

## Checklist de cobertura dos módulos

### Módulo 1 - Fundamentos, níveis e tipos de teste

| Aula / seção | Status | Arquivo |
|---|---|---|
| 1.1 O que é software? | Feito | `docs/conceitos/fundamentos-de-teste-conceitos.md` |
| 1.2 O que é teste de software? | Feito | `docs/conceitos/fundamentos-de-teste-conceitos.md` |
| 1.3 Objetivos, importância dos testes e Regra de 10 de Myers | Feito | `docs/conceitos/fundamentos-de-teste-conceitos.md` |
| 2.1 Testes dinâmicos versus testes estáticos | Feito | `docs/conceitos/testes-estaticos-dinamicos-erro-defeito-falha.md` |
| 2.2 Diferença entre erro, defeito e falha | Feito | `docs/conceitos/testes-estaticos-dinamicos-erro-defeito-falha.md` |
| 2.3 Causa raiz e seus efeitos | Feito | `docs/conceitos/testes-estaticos-dinamicos-erro-defeito-falha.md` |
| 3.1 Qualidade de software | Feito | `docs/conceitos/caracteristicas-de-qualidade-do-software.md` |
| 3.2 Os 7 princípios do teste | Feito | `docs/conceitos/7-principios-do-teste.md` |

### Módulo 2 - Níveis de teste

| Aula / seção | Status | Arquivo |
|---|---|---|
| 1.1 O que são testes e quais são os níveis de teste? | Feito | `docs/conceitos/niveis-de-teste.md` |
| 2.1 Teste de componente ou unidade | Feito | `docs/conceitos/niveis-de-teste.md` |
| 2.2 Teste de integração | Feito | `docs/conceitos/niveis-de-teste.md` |
| 3.1 Teste de sistema | Feito | `docs/conceitos/niveis-de-teste.md` |
| 3.2 Teste de aceitação | Feito | `docs/conceitos/niveis-de-teste.md` |
| 3.3 Teste de confirmação, regressão e manutenção | Feito | `docs/conceitos/niveis-de-teste.md` |

### Módulo 3 - Tipos de teste e suas aplicações

| Aula / seção | Status | Arquivo |
|---|---|---|
| 1.1 Testes funcionais | Feito | `docs/conceitos/tipos-de-teste.md` |
| 1.2 Testes não funcionais | Feito | `docs/conceitos/tipos-de-teste.md` |
| 2.1 Teste caixa preta | Feito | `docs/conceitos/tipos-de-teste.md` |
| 2.2 Teste caixa branca | Feito | `docs/conceitos/tipos-de-teste.md` |

## Revisão rápida

- Testar não é provar perfeição; é reduzir risco.
- Nem tudo pode ser testado, então priorização é essencial.
- A Regra de 10 de Myers reforça que encontrar defeitos cedo reduz custo e retrabalho.
- Qualidade envolve funcionamento, experiência, proteção, desempenho e manutenção.
- Tipos de teste indicam o foco da validação; níveis de teste indicam onde ela acontece no ciclo.
- O produto precisa funcionar e ainda fazer sentido para o negócio e para o usuário.
- Os Módulos 1, 2 e 3 estão cobertos nas notas de `docs/conceitos/`.
