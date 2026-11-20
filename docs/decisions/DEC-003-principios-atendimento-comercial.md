# DEC-003 — Princípios de condução do atendimento comercial

**Produto:** Plataforma de Atendimento Inteligente

**Data:** 18 de novembro de 2026

**Status:** Aprovada

## 1. Contexto

Durante a especificação do Módulo 05 — Atendimento inteligente e interpretação de solicitações, foram definidas regras para orientar a condução do atendimento comercial pela IA.

Essas regras envolvem a compreensão das necessidades do cliente, identificação e autorização dos contatos, organização das solicitações, confirmação das informações, continuidade do atendimento e encaminhamento de situações que dependam de decisão humana.

Também foi necessário estabelecer limites entre a responsabilidade do Módulo 05 e as etapas posteriores de elaboração de propostas e registro de pedidos.

## 2. Decisão

O Módulo 05 será responsável por conduzir o atendimento comercial desde o primeiro contato até a compreensão, organização e confirmação da solicitação pelo cliente.

A solicitação somente poderá ser encaminhada ao Módulo 06 após a concordância expressa do cliente com o resumo apresentado pela IA.

A condução do atendimento deverá respeitar os seguintes princípios:

### 2.1. Identificação e autorização

- Antes de acessar ou revelar informações comerciais protegidas, a plataforma deverá verificar se o cliente está cadastrado e vinculado à empresa.
- Deverá confirmar se o contato está autorizado pela empresa e verificar suas permissões específicas.
- A identificação do contato e seu vínculo com a empresa não significam autorização irrestrita para consultar informações ou tomar decisões.
- As permissões individuais deverão ser verificadas conforme a ação solicitada, respeitando as configurações definidas pela empresa.
- Contatos ainda não cadastrados poderão receber atendimento inicial para apresentação e identificação de necessidades.
- O atendimento inicial não permitirá acesso a preços particulares, condições comerciais restritas ou histórico de outros clientes.
- A coleta de dados para cadastro poderá acontecer durante a própria conversa, sem exigir formulário separado.
- Quando informado o CNPJ, a plataforma poderá consultar uma fonte oficial disponível, apresentar os dados encontrados e solicitar confirmação do interessado.
- A liberação do atendimento comercial protegido dependerá da conclusão das validações necessárias.

### 2.2. Compreensão e organização da solicitação

- A IA deverá compreender a necessidade do cliente e identificar produtos, quantidades e especificações relevantes.
- Deverá consultar as informações da empresa conforme a necessidade de cada etapa do atendimento.
- Não deverá solicitar novamente informações que já foram fornecidas ou confirmadas.
- Deverá perguntar somente o necessário para esclarecer a solicitação.
- Poderá consultar o histórico do cliente para contextualizar o atendimento e identificar preferências anteriores, sem presumir que continuam válidas.
- Solicitações com vários produtos deverão ser tratadas individualmente por item.
- Uma dúvida ou pendência em determinado produto não deverá impedir o tratamento dos demais itens.
- As informações e pendências de cada item deverão ser preservadas.
- Quando uma pendência estiver restrita a determinado item, os demais itens válidos poderão continuar seu fluxo, inclusive permitindo a elaboração de uma proposta parcial pelo Módulo 06.
- Uma pendência que comprometa a compreensão ou a suficiência da solicitação como um todo deverá ser resolvida antes do encaminhamento correspondente.

### 2.3. Confirmação da solicitação

- A IA deverá apresentar um resumo organizado da solicitação antes de encaminhá-la ao Módulo 06.
- O cliente poderá corrigir, complementar ou retirar informações enquanto o resumo não tiver sido confirmado.
- A concordância expressa do cliente será obrigatória para o encaminhamento.
- Silêncio ou ausência de resposta não poderão ser interpretados como confirmação.
- Cada confirmação deverá ficar vinculada à versão exata da solicitação aprovada.
- Alterações realizadas antes da confirmação deverão ser refletidas no resumo apresentado novamente ao cliente.
- A confirmação deverá preservar o conteúdo exato da solicitação, sua versão e o registro da manifestação do cliente.
- A confirmação da solicitação não representa aceite de proposta comercial, aprovação interna ou autorização automática para registro de pedido.

### 2.4. Continuidade e retomada do atendimento

- Quando o cliente não responder à solicitação de confirmação, a IA poderá realizar até duas tentativas de retomada.
- Após duas tentativas sem resposta, o atendimento permanecerá aberto com o status "Aguardando retorno do cliente".
- Não haverá encerramento automático por ausência de resposta.
- Quando o cliente retornar, a IA deverá recuperar o contexto e o estado anterior da negociação.
- Não deverá reiniciar desnecessariamente o atendimento nem solicitar novamente informações já registradas.
- Antes de prosseguir com etapas ainda não concluídas ou elaborar novas versões, deverá verificar novamente preços, condições comerciais e disponibilidade.
- Informações consultadas anteriormente não serão consideradas necessariamente vigentes.
- A revalidação das informações comerciais não poderá alterar retroativamente propostas já apresentadas ao cliente.
- Propostas apresentadas deverão respeitar suas versões, condições e prazos de validade, conforme as regras do Módulo 06.

### 2.5. Histórico e pedidos anteriores

- A IA poderá utilizar o histórico para facilitar o atendimento e identificar preferências.
- Preferências anteriores deverão ser confirmadas com o cliente antes de serem utilizadas como escolha atual.
- Quando o cliente solicitar a repetição de um pedido, a IA deverá recuperar o pedido mais recente efetivamente registrado.
- Propostas não aceitas e negociações não concluídas não poderão ser tratadas como pedidos realizados.
- O pedido anterior servirá como referência, não como autorização automática para uma nova compra.
- Se houver dúvida sobre qual pedido deverá ser recuperado, a IA deverá solicitar esclarecimento.
- O acesso ao histórico dependerá da validação da identidade e das permissões do contato.

### 2.6. Produtos, informações e disponibilidade

- A IA deverá utilizar informações provenientes de fontes confiáveis da empresa.
- Não poderá inventar marcas, embalagens, unidades comerciais, características, preços ou disponibilidade.
- Quando não possuir informações suficientes, deverá apresentar somente os dados conhecidos e confiáveis.
- Se não conseguir identificar um produto com segurança, deverá solicitar esclarecimento.
- Persistindo a dúvida, deverá encaminhar a pendência ao gerente.
- Produtos que não façam parte do catálogo deverão ser identificados como não comercializados pela empresa.
- A IA não poderá incluir esses produtos em propostas nem oferecer substitutos automaticamente.
- Demandas por produtos não comercializados poderão ser registradas para avaliação futura, sem inclusão automática no catálogo.
- Quando um produto estiver indisponível, a IA deverá informar o cliente e consultar alternativas autorizadas pela empresa.
- A decisão de aceitar uma alternativa será sempre do cliente.
- Nenhum produto poderá ser removido ou substituído automaticamente.
- Nenhum produto poderá ser utilizado em uma proposta sem preço definido.
- A ausência de preço deverá bloquear a utilização do produto afetado e gerar comunicação à gerência para correção do cadastro.
- A ausência de preço em um produto não deverá impedir automaticamente o andamento dos demais itens que possuam informações comerciais válidas.
- A IA deverá distinguir ausência de preço, ausência de tabela comercial válida, conflito entre tabelas e indisponibilidade do produto, respeitando o tratamento específico de cada situação.

### 2.7. Encaminhamento humano e pendências

- O cliente poderá solicitar atendimento humano a qualquer momento.
- A IA também deverá encaminhar situações que não consiga resolver com segurança.
- O registro da pendência deverá ser mantido para acompanhamento.
- Quando uma pendência exigir decisão humana, o contexto, o histórico e a pendência deverão ser encaminhados ao gerente, que decidirá quem deverá tratá-la, respeitando as delegações válidas e os limites autorizados.
- A plataforma não deverá transferir automaticamente o atendimento para qualquer funcionário.
- Situações que exijam decisão humana deverão ser encaminhadas ao gerente, incluindo negociações de preço ou condições especiais quando não houver delegação válida ou quando a solicitação ultrapassar os limites autorizados.
- Funcionários que possuam delegação específica poderão atuar dentro dos limites definidos pela empresa, respeitando suas permissões e autorizações.
- O encaminhamento ao gerente não deverá ocorrer automaticamente em situações que já estejam cobertas por uma delegação válida e dentro dos limites autorizados.
- Enquanto aguarda avaliação, o cliente deverá receber informações claras sobre a pendência.
- A IA não poderá prometer prazos que não tenham sido definidos pela empresa.
- Uma pendência não deverá bloquear os demais atendimentos da operação.

## 3. Consequências e limites

- O Módulo 05 será responsável pela compreensão, organização e confirmação da solicitação comercial.
- A elaboração formal da proposta e a condução das etapas posteriores de negociação serão responsabilidades do Módulo 06.
- A confirmação da solicitação pelo cliente será uma condição obrigatória para a passagem entre os módulos.
- A confirmação da solicitação não deverá ser confundida com aceite da proposta, aprovação interna ou registro de pedido.
- O aceite da proposta comercial será uma manifestação posterior e específica do cliente, vinculada à versão e às condições apresentadas pelo Módulo 06.
- A aprovação interna será uma etapa distinta do aceite da proposta comercial, sujeita às regras de autoridade e aprovação estabelecidas pela empresa.
- O atendimento deverá preservar histórico, contexto, versões e confirmações.
- A IA poderá facilitar decisões, mas não poderá assumir decisões comerciais que dependam do cliente ou da empresa.
- O histórico e as permissões dos contatos deverão ser respeitados durante toda a interação.
- O encaminhamento humano permanecerá sob controle do gerente, respeitando as delegações específicas e os limites de atuação previamente autorizados.
- As regras aqui registradas deverão orientar os requisitos funcionais e os critérios de validação do Módulo 05.

Esta decisão não altera as responsabilidades já definidas para os Módulos 01, 02 e 06, nem amplia o escopo do atendimento pós-venda ou da gestão logística.

## 4. Documentos relacionados

- `docs/03-prd.md`
- `docs/06-matriz-de-escopo-do-mvp.md`
- `docs/07-matriz-de-rastreabilidade-de-decisoes-e-perguntas.md`
- `docs/decisions/DEC-001-supervisao-operacional.md`
- `docs/decisions/DEC-002-escopo-atendimento-pos-venda.md`
- `docs/decisions/DEC-004-permissoes-individuais-contatos.md`
