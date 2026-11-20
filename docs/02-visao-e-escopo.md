# Documento 02 — Visão e Escopo do Produto

**Nome provisório:** Plataforma de Atendimento Inteligente

**Status:** Versão revisada para consolidação

**Data da revisão:** 19 de novembro de 2026

**Data de referência da versão anterior:** 18 de novembro de 2026

## 1. Visão do Produto

Construir uma plataforma de atendimento inteligente capaz de receber, compreender e conduzir solicitações de clientes, executar operações comerciais permitidas e acompanhar pendências relacionadas ao atendimento até sua resolução.

O produto deve permitir que empresas atendam vários clientes simultaneamente, reduzindo atrasos, tarefas manuais e dependência de intervenções humanas em atividades que podem ser automatizadas.

A inteligência artificial atua como parte da operação, não apenas como uma interface de perguntas e respostas.

A plataforma deverá preservar o contexto das interações, respeitar as regras e autorizações da empresa e manter a rastreabilidade das ações realizadas durante o atendimento.

## 2. Problema que o Produto Resolve

Empresas que recebem solicitações por canais digitais frequentemente enfrentam:

- Demora no primeiro atendimento.
- Sobrecarga de funcionários com conversas simultâneas.
- Dependência de consultas manuais a outros setores.
- Perda de informações entre conversas e funcionários.
- Falta de acompanhamento de solicitações pendentes.
- Dificuldade para identificar gargalos e melhorar o atendimento.

O produto busca transformar o atendimento em um processo organizado, rastreável e passível de melhoria contínua.

## 3. Proposta de Valor

Oferecer às empresas um sistema que:

- Atenda clientes de forma automatizada e contextualizada.
- Consulte informações comerciais confiáveis.
- Conduza processos de atendimento e negociação.
- Encaminhe decisões e tarefas aos funcionários responsáveis.
- Acompanhe pendências comerciais sem interromper outros atendimentos.
- Mantenha histórico das interações, intervenções e decisões.
- Permita supervisionar a operação e identificar oportunidades de melhoria.
- Respeite as permissões individuais dos contatos e as delegações comerciais configuradas pela empresa.

## 4. Público do Produto

O produto será direcionado a empresas que recebem solicitações de clientes por canais digitais e precisam organizar, automatizar e acompanhar seus atendimentos.

**Segmento inicial:** ainda não definido.

A escolha deverá considerar a frequência dos atendimentos, a complexidade das operações, a disponibilidade de dados e o potencial de automação.

## 5. Capacidades Centrais

### 5.1 Atendimento inteligente

Receber mensagens, identificar intenções, compreender solicitações e conduzir conversas, preservando o contexto e as informações relevantes de cada atendimento.

### 5.2 Consulta de informações

Consultar catálogos, preços, disponibilidade e demais informações fornecidas ou autorizadas pela empresa, respeitando as permissões de acesso e as associações comerciais aplicáveis.

A plataforma não deverá inventar informações nem utilizar produtos sem preço definido em propostas comerciais.

### 5.3 Operação comercial

Compreender e organizar solicitações, preparar propostas, apresentar condições comerciais, registrar manifestações de aceite ou recusa, gerar automaticamente o pedido após o aceite válido e encaminhá-lo para aprovação interna.

As etapas deverão respeitar as regras comerciais, as permissões dos contatos envolvidos e as delegações específicas configuradas pela empresa.

A confirmação de uma solicitação, o aceite de uma proposta, a aprovação interna e o registro de um pedido são eventos distintos e deverão permanecer separados.

### 5.4 Gestão de ocorrências e pendências comerciais

Registrar problemas relacionados ao atendimento comercial, encaminhar solicitações aos responsáveis, acompanhar pendências e informar o cliente sobre o andamento.

No MVP, essa capacidade estará limitada às necessidades do ciclo comercial. Não representa a implementação de uma gestão geral de ocorrências, tarefas administrativas ou operação completa de pós-venda.

Uma pendência restrita a determinado produto ou item não deverá bloquear automaticamente o andamento dos demais itens válidos da solicitação.

### 5.5 Gestão e supervisão

Disponibilizar à empresa uma visão operacional dos atendimentos, históricos, pendências comerciais e intervenções humanas.

A supervisão inicial deverá permitir identificar situações que aguardam providências ou decisões, consultar propostas e acompanhar o estado das operações.

Relatórios avançados e análises sofisticadas não fazem parte da supervisão básica do MVP.

### 5.6 Aprendizado e melhoria

A plataforma poderá, em sua evolução, identificar dúvidas recorrentes, padrões operacionais, problemas e oportunidades de melhoria.

Recomendações relevantes deverão passar pela validação da empresa antes de serem incorporadas ao conhecimento oficial do sistema.

Recursos avançados de aprendizado, análise de padrões e compartilhamento de conhecimento entre empresas não constituem requisitos do MVP.

## 6. Princípios de Funcionamento

1. A automação não deve inventar informações.
2. Decisões comerciais devem respeitar as permissões configuradas pela empresa para cada contato autorizado. Contatos da mesma empresa podem possuir permissões diferentes.
3. A identificação de um contato não representa autorização irrestrita para acessar informações ou realizar operações comerciais.
4. A empresa poderá delegar a funcionários específicos a negociação de condições especiais, dentro dos limites estabelecidos. Essa delegação não representa, por si só, autoridade para aprovar pedidos.
5. A autoridade para aprovação interna deverá respeitar as permissões e autorizações específicas configuradas pela empresa.
6. O cliente deve ser informado sobre o andamento de sua solicitação.
7. Pendências não devem bloquear outros atendimentos nem impedir automaticamente o andamento de itens válidos de uma mesma solicitação.
8. Toda intervenção relevante deve ser registrada.
9. A empresa deve manter controle sobre seus dados, permissões e decisões.
10. Informações aprendidas pela IA só devem ser incorporadas à base oficial após validação.
11. A tecnologia deve simplificar a operação, não criar burocracia.

## 7. Escopo Inicial — MVP

### 7.1 Objetivo do MVP

O MVP deverá ser capaz de realizar um atendimento comercial completo, desde a primeira mensagem do interessado até o aceite da proposta, o registro automático do pedido e sua aprovação interna.

Não será suficiente demonstrar apenas respostas automatizadas ou consultas isoladas. Precisamos comprovar que a plataforma consegue conduzir o processo comercial de ponta a ponta, mantendo o contexto, os registros e o acompanhamento das etapas.

O atendimento inicial não deverá exigir cadastro obrigatório. A identificação e a confirmação do vínculo com a empresa serão necessárias antes de liberar informações e operações comerciais protegidas.

A execução de cada ação protegida deverá respeitar as permissões individuais do contato e, quando aplicável, as delegações específicas e autorizações internas existentes.

### 7.2 Jornada comercial que deverá ser demonstrada

1. **Primeiro contato:** receber a mensagem, compreender a solicitação e, quando necessário, iniciar a identificação e o cadastro do interessado durante a própria conversa.

2. **Compreensão da necessidade:** interpretar o que o cliente procura, identificar produtos, quantidades e especificações, organizar os itens solicitados e conduzir a conversa até a confirmação expressa da solicitação.

3. **Identificação e autorização:** verificar a empresa, o vínculo do contato e suas permissões antes de acessar informações ou realizar operações protegidas. A identificação não deverá ser tratada como autorização irrestrita.

4. **Consulta comercial:** consultar catálogo, preços, disponibilidade, tabelas aplicáveis e condições válidas, respeitando as informações oficiais e as associações comerciais definidas pela empresa.

5. **Tratamento de pendências:** identificar informações ausentes, inconsistências e itens que não possam prosseguir. A ausência de preço definido impedirá a inclusão do produto afetado em uma proposta e deverá gerar comunicação à gerência para correção. Outros itens válidos poderão continuar.

6. **Confirmação da solicitação:** apresentar ao cliente um resumo organizado do que foi compreendido e aguardar sua concordância expressa. Essa confirmação registra a solicitação, mas não representa aceite de proposta, aprovação interna ou registro de pedido.

7. **Preparação da proposta:** elaborar a proposta com os produtos, quantidades, preços e condições comerciais válidos. Quando houver pendência isolada em determinado item, os demais itens válidos poderão compor uma proposta parcial, conforme as regras aplicáveis.

8. **Apresentação da proposta:** apresentar efetivamente as condições ao cliente, registrar a versão apresentada e iniciar o controle de sua validade.

9. **Decisão do cliente:** registrar o aceite ou a recusa expressa da proposta, sempre vinculando a manifestação à versão e às condições apresentadas. A validade geral da proposta será de 72 horas corridas, contadas a partir de sua apresentação efetiva ao cliente. A ausência de aceite até o vencimento resultará em expiração, não em recusa.

10. **Condições especiais:** quando uma nova versão apresentar condição especial negociada, essa condição terá validade própria de três dias corridos, contados da emissão da nova versão. Esse prazo será independente da validade geral da proposta. A condição especial somente poderá ser aceita enquanto ambos os prazos aplicáveis estiverem vigentes. O vencimento da condição especial não invalida automaticamente a proposta original, caso ela ainda esteja válida.

11. **Registro e encaminhamento do pedido:** após o aceite válido do cliente, registrar automaticamente o pedido, integral ou parcial, sem exigir uma segunda confirmação. Encaminhar o pedido para aprovação interna no M07 e informar ao cliente que ele aguarda essa aprovação. A delegação para negociar condições especiais não deverá ser confundida com autorização para aprovar pedidos.

12. **Registro da decisão:** registrar quem aprovou ou rejeitou internamente e quando ocorreu a decisão, preservando o histórico e as condições comerciais envolvidas.

13. **Tratamento de pedidos não aprovados:** registrar o motivo da decisão, preservar o pedido e as condições comerciais aceitas e comunicar o resultado ao cliente.

14. **Comunicação e acompanhamento:** informar o cliente, atualizar o histórico e acompanhar eventuais pendências relacionadas à operação comercial.

**Regra fundamental:** a confirmação da solicitação, a apresentação da proposta, o aceite do cliente, a aprovação interna e o registro do pedido são etapas distintas. O sistema deverá preservar essa separação, os responsáveis por cada ação, as versões e as condições comerciais correspondentes.

### 7.3 Capacidades necessárias

Para viabilizar essa jornada, o MVP deverá contemplar:

- Cadastro e configuração inicial de uma empresa.
- Cadastro e identificação de clientes e contatos autorizados.
- Verificação do vínculo entre contato e empresa.
- Controle de permissões individuais dos contatos.
- Configuração de delegações específicas para negociações comerciais.
- Controle de autoridade para aprovação interna.
- Importação e validação de catálogo comercial.
- Consulta de produtos, preços e disponibilidade.
- Associação de tabelas comerciais aos clientes ou grupos autorizados.
- Verificação de vigência e aplicabilidade das condições comerciais.
- Bloqueio de produtos sem preço definido em propostas e comunicação à gerência.
- Controle das informações comerciais utilizadas em cada proposta.
- Atendimento automatizado por um canal inicial.
- Recuperação do histórico de relacionamento com o cliente, respeitando as permissões.
- Compreensão, organização e confirmação expressa das solicitações.
- Preparação, apresentação e registro de propostas.
- Controle da validade geral das propostas.
- Controle independente da validade de condições especiais.
- Registro de aceite, recusa expressa e expiração.
- Aprovação interna com controle de permissões.
- Registro de ocorrências relacionadas ao atendimento comercial.
- Encaminhamento e acompanhamento de pendências comerciais.
- Comunicação com o cliente durante o processo.
- Painel de supervisão operacional básica dos atendimentos.
- Histórico de conversas, intervenções, versões e decisões.
- Rastreabilidade das etapas comerciais e dos responsáveis por cada ação.

**Observação:** a lista representa o escopo funcional pretendido. A especificação detalhada, as regras de negócio, a priorização técnica e os critérios de aceitação serão desenvolvidos nos documentos correspondentes.

## 8. Fora do Escopo Inicial

Possíveis funcionalidades para versões futuras, sujeitas à validação:

- Integração com múltiplos canais simultaneamente.
- Integrações complexas com ERPs.
- Sincronização automática com múltiplos sistemas externos.
- Treinamento ou ajuste personalizado de modelos de IA.
- Inteligência coletiva entre empresas.
- Automações avançadas de processos administrativos.
- Gestão logística de entregas.
- Gestão completa de pós-venda.
- Análise avançada de padrões e indicadores operacionais.

Esses itens não estão descartados; apenas não devem ser assumidos como requisitos obrigatórios do primeiro MVP.

A consulta a pedidos anteriores e a comunicação de estados conhecidos poderão ocorrer quando essas informações estiverem disponíveis, sem representar a inclusão de uma operação completa de pós-venda.

## 9. Diferencial do Produto

O diferencial não está apenas em responder mensagens automaticamente.

Está em conectar atendimento, execução de tarefas comerciais, decisões, acompanhamento de pendências e histórico operacional em um único fluxo.

O sistema deve acompanhar o ciclo comercial até sua conclusão, e não simplesmente encerrar sua participação depois de responder ao cliente.

A plataforma deverá combinar autonomia operacional com limites claros de autorização, rastreabilidade e supervisão humana.

A evolução para outras áreas operacionais, como pós-venda completo e gestão logística, poderá ocorrer posteriormente, conforme as necessidades identificadas na utilização real do produto.

## 10. Questões Estratégicas em Aberto

Permanecem como questões estratégicas a serem avaliadas no momento adequado:

- Qual será o primeiro segmento de mercado?
- Qual canal será utilizado no MVP?
- Quais integrações externas serão indispensáveis?
- Qual será o nível de autonomia permitido à IA em cada etapa da operação?
- Quais fontes serão utilizadas para identificação e validação dos dados de empresas e contatos?
- Como será estruturada tecnicamente a sincronização de preços e disponibilidade?
- Qual será a lista detalhada de permissões individuais e como será administrada pela empresa?
- Como serão configurados e administrados os limites das delegações comerciais?
- Como será estruturado o modelo de contratação?

A existência dessas questões não significa que todas precisem ser respondidas imediatamente. O momento de definição deverá considerar sua necessidade para a descoberta, especificação, implementação ou validação do MVP.

As decisões e regras já aprovadas permanecem registradas nos documentos de governança e não deverão ser reabertas apenas por estarem relacionadas a essas questões estratégicas.

## 11. Próxima Etapa

O PRD — Documento de Requisitos do Produto — detalhará as funcionalidades, jornadas, comportamentos esperados, regras e critérios de aceitação.

A descoberta funcional do Módulo 06 já foi realizada e suas decisões e regras estão registradas na matriz de rastreabilidade. Sua consolidação e formalização no PRD deverão respeitar as decisões aprovadas e as relações com os demais módulos.

Os documentos de decisões e demais documentos complementares deverão manter suas finalidades próprias, evitando duplicação de conteúdo e divergências entre fontes de informação.

A matriz de rastreabilidade continuará sendo utilizada para relacionar perguntas, decisões, regras derivadas, pendências e módulos afetados.

A documentação deverá evoluir de forma integrada, preservando a coerência entre visão do produto, escopo, requisitos, decisões e regras de negócio.
