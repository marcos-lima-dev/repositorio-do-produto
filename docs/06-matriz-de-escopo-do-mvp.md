# Documento 06 — Matriz de Escopo do MVP

**Produto:** Plataforma de Atendimento Inteligente  
**Versão:** 0.2 — Consolidação das decisões  
**Data:** 18 de novembro de 2026  
**Status:** Em revisão

## 1. Princípio orientador

Construir um produto pequeno, viável e altamente necessário.

O MVP deverá resolver uma missão comercial específica com confiabilidade, sem incorporar funcionalidades que possam ser desenvolvidas em etapas posteriores.

A visão de longo prazo do produto não deve ser confundida com os requisitos da primeira versão.

## 2. Missão do MVP

Receber solicitações comerciais, compreender o que o cliente deseja, consultar as informações oficiais da empresa, conduzir o atendimento e a negociação até o registro do pedido e sua aprovação interna, preservando o contexto, as condições comerciais e o histórico da operação.

O atendimento inicial deverá permitir que o interessado converse livremente com a plataforma. A identificação será solicitada quando necessária para acessar preços e condições comerciais.

## 3. Escopo funcional

| Capacidade | Classificação |
|---|---|
| Atendimento inicial sem cadastro obrigatório | MVP obrigatório |
| Identificação da empresa por CNPJ | MVP obrigatório |
| Consulta e validação dos dados cadastrais | MVP obrigatório |
| Confirmação dos dados pelo interessado | MVP obrigatório |
| Cadastro de empresas clientes | MVP obrigatório |
| Associação de vários contatos a uma empresa | MVP obrigatório |
| Controle de autorização dos contatos | MVP obrigatório |
| Definição de permissões individuais para cada contato autorizado | MVP obrigatório |
| Verificação das permissões antes de liberar informações e operações protegidas | MVP obrigatório |
| Catálogo de produtos | MVP obrigatório |
| Características e identificação dos produtos | MVP simplificado |
| Nomes alternativos de produtos | MVP simplificado |
| Importação e validação inicial do catálogo | MVP obrigatório |
| Consulta de preços | MVP obrigatório |
| Tabelas e condições comerciais | MVP simplificado |
| Consulta de disponibilidade | MVP obrigatório |
| Interpretação de solicitações | MVP obrigatório |
| Atendimento com vários produtos | MVP obrigatório |
| Esclarecimento de ambiguidades | MVP obrigatório |
| Comunicação durante consultas e pendências | MVP obrigatório |
| Apresentação de marcas e alternativas disponíveis | MVP obrigatório |
| Elaboração e apresentação de propostas | MVP obrigatório |
| Controle da validade das propostas | MVP obrigatório |
| Aceite ou rejeição do cliente | MVP obrigatório |
| Aprovação interna por pessoa autorizada | MVP obrigatório |
| Registro de pedidos | MVP obrigatório |
| Histórico de atendimentos e operações | MVP obrigatório |
| Registro de ocorrências e intervenções relacionadas ao atendimento comercial | MVP obrigatório |
| Acompanhamento de pendências comerciais necessárias à continuidade da operação | MVP obrigatório |
| Supervisão operacional básica | MVP obrigatório |

A lista representa o escopo funcional pretendido. Os comportamentos, as regras específicas e os critérios de aceitação serão detalhados nos documentos funcionais correspondentes.

## 4. Supervisão operacional básica

Conforme a decisão DEC-001, a empresa deverá conseguir:

- Visualizar a lista de atendimentos e seus estados.
- Identificar atendimentos com pendências.
- Consultar propostas e decisões.
- Consultar o histórico de intervenções.
- Visualizar solicitações que aguardam decisão humana.

A supervisão deverá garantir visibilidade e controle da operação, sem exigir um painel analítico complexo.

Relatórios avançados, indicadores sofisticados e análises avançadas de desempenho não fazem parte desse escopo básico.

## 5. Funcionalidades fora do MVP

| Capacidade | Destino |
|---|---|
| Gestão logística de entregas | Pós-MVP |
| Planejamento de rotas e veículos | Pós-MVP |
| Gestão de capacidade diária de entrega | Pós-MVP |
| Integrações logísticas complexas | Pós-MVP |
| Integrações complexas com ERPs | Pós-MVP |
| Sincronização automática com múltiplos sistemas externos | Pós-MVP |
| Atendimento pós-venda completo | Pós-MVP — escopo a definir |
| Aprendizado coletivo entre empresas | Pós-MVP |
| Publicação compartilhada de conhecimento | Pós-MVP |
| LoRA e fine-tuning especializado | Pesquisa futura |
| Análise avançada de padrões | Pós-MVP |
| Previsão inteligente de demanda | Pós-MVP |
| Relatórios e indicadores avançados | Pós-MVP |

A localização de pedidos anteriores e a consulta a estados conhecidos poderão ocorrer quando essas informações estiverem disponíveis, sem representar a inclusão de uma operação completa de pós-venda ou gestão logística no MVP.

## 6. Princípios técnicos e operacionais

- A solução será especializada por vertical de negócio.
- O conhecimento especializado de cada vertical poderá ser compartilhado entre empresas do mesmo segmento.
- Os dados comerciais e particulares permanecerão isolados por empresa.
- O primeiro MVP deverá atender a um único vertical, ainda a ser definido.
- O MVP utilizará conhecimento especializado inicial, sem exigir treinamento personalizado de modelos para cada empresa.
- A IA não inventará preços, disponibilidade ou características dos produtos.
- Informações comerciais deverão ter origem em fontes confiáveis e validadas.
- Alterações comerciais relevantes serão registradas.
- O sistema preservará o histórico das operações e decisões.
- O atendimento deverá conduzir o cliente com perguntas objetivas e naturais.
- O cliente deverá ser informado sobre consultas e pendências, evitando períodos de silêncio.
- A empresa manterá controle sobre suas informações, permissões e decisões comerciais.
- A supervisão operacional deverá permitir acompanhar o trabalho realizado pela plataforma.

## 7. Critério de entrada de funcionalidades

Uma funcionalidade somente deverá entrar no MVP se for necessária para:

1. Cumprir a missão comercial principal.
2. Garantir a confiabilidade das informações e das operações.
3. Preservar o controle da empresa sobre o processo comercial.
4. Permitir a conclusão e a supervisão do ciclo comercial.

A existência de uma possibilidade técnica ou comercial não é justificativa suficiente para sua implementação.

Quando uma capacidade for necessária, deverá ser implementada da forma mais simples que preserve sua confiabilidade.

## 8. Critério de encerramento do MVP

O MVP estará apto à validação quando conseguir executar um ciclo comercial completo:

1. Receber uma solicitação sem exigir cadastro imediato.
2. Compreender a necessidade do interessado.
3. Solicitar identificação quando necessário para acessar condições comerciais.
4. Validar os dados da empresa e registrar a confirmação do interessado.
5. Identificar os contatos e suas autorizações, verificando as permissões individuais correspondentes.
6. Consultar catálogo, preços e disponibilidade.
7. Apresentar opções confiáveis.
8. Conduzir a negociação, inclusive com vários produtos.
9. Elaborar e apresentar uma proposta.
10. Registrar o aceite ou a rejeição do cliente.
11. Submeter propostas aceitas à aprovação interna.
12. Registrar a decisão e seu responsável.
13. Comunicar o resultado ao cliente.
14. Preservar o histórico e acompanhar eventuais pendências comerciais.
15. Permitir que a empresa supervisione a operação.

A expansão funcional deverá ocorrer após a validação do produto em operação real.

## 9. Decisões relacionadas

As seguintes decisões aprovadas orientam a definição e a manutenção do escopo do MVP:

- [DEC-001 — Supervisão operacional básica no MVP](decisions/DEC-001-supervisao-operacional.md).
- [DEC-002 — Escopo do atendimento pós-venda](decisions/DEC-002-escopo-atendimento-pos-venda.md).
- [DEC-003 — Princípios de condução do atendimento comercial](decisions/DEC-003-principios-atendimento-comercial.md).
- [DEC-004 — Permissões individuais dos contatos autorizados](decisions/DEC-004-permissoes-individuais-contatos.md).

As decisões aprovadas devem ser consultadas antes da revisão ou inclusão de requisitos relacionados. Os documentos funcionais devem refletir as decisões vigentes, respeitando a finalidade de cada documento.