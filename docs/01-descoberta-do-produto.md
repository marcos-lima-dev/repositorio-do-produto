# Documento 01 — Descoberta do Produto

**Nome provisório:** Plataforma de Atendimento Inteligente
**Status:** Versão revisada para consolidação
**Data da revisão:** 19 de novembro de 2026
**Data de referência da descoberta:** 16 de novembro de 2026
**Repositório:** `marcos-lima-dev/repositorio-do-produto`

---

## 1. Resumo executivo

A proposta é desenvolver uma plataforma de atendimento inteligente para empresas, capaz de receber solicitações comerciais, compreender necessidades, consultar informações oficiais, conduzir negociações e executar operações comerciais autorizadas.

O produto não deve se limitar a responder perguntas frequentes ou encaminhar mensagens. Seu objetivo é dar continuidade ao atendimento, reduzir o tempo de espera, organizar processos e evitar que solicitações comerciais fiquem esquecidas.

A plataforma deverá permitir que a empresa acompanhe atendimentos, propostas, pedidos, pendências e decisões, mantendo um histórico que permita reconstruir o que aconteceu durante cada operação.

A inteligência artificial deverá atuar como parte da operação, respeitando as informações, permissões e decisões estabelecidas pela empresa.

A visão de longo prazo também contempla aprendizado operacional, identificação de padrões e recomendações de melhoria. Essas capacidades deverão evoluir conforme a validação do produto e não devem ser confundidas com os requisitos obrigatórios do MVP.

## 2. Origem da ideia

A ideia surgiu da observação de uma operação comercial de uma distribuidora de laticínios.

A empresa recebia contatos de potenciais clientes pela internet, inclusive por anúncios pagos no Google. Os vendedores eram responsáveis por atender esses contatos e conduzir as negociações.

Durante essa experiência, foram identificadas dificuldades:

- Vendedores podiam priorizar clientes habituais em detrimento de novos contatos.
- Alguns leads demoravam para receber resposta.
- A consulta de estoque e disponibilidade dependia da comunicação entre vendedores e outros setores.
- O vendedor precisava interromper o atendimento para obter informações.
- O atendimento simultâneo de vários clientes gerava acúmulo de conversas e tarefas.
- Algumas solicitações ficavam aguardando respostas ou decisões humanas.

A operação dependia muito da capacidade individual dos funcionários de administrar conversas, consultas e tarefas simultâneas.

A ideia do produto nasceu da percepção de que a tecnologia poderia assumir boa parte desse trabalho, mantendo a continuidade dos atendimentos e permitindo que os funcionários interviessem quando necessário.

**Importante:** a distribuidora de laticínios é a inspiração e um cenário real de observação. Isso não significa que o mercado inicial do produto já esteja definido.

## 3. Problema que queremos resolver

Empresas que recebem solicitações de clientes por canais digitais podem enfrentar dificuldades para manter um atendimento rápido, contínuo e organizado.

O problema não está somente na demora da primeira resposta. Está também no que acontece depois dela.

Um atendimento comercial pode depender de:

- Consulta de informações.
- Verificação de disponibilidade.
- Comparação de produtos.
- Preparação de propostas.
- Confirmações do cliente.
- Aprovações internas.
- Respostas de funcionários.
- Resolução de ocorrências comerciais.

Quando essas atividades dependem exclusivamente de comunicação manual, o processo pode ficar lento, fragmentado e sujeito a esquecimentos.

O produto pretende reduzir essa dependência operacional, automatizando tarefas possíveis e acompanhando as que ainda precisam de intervenção humana.

O foco inicial será o atendimento comercial. Outras áreas operacionais poderão ser consideradas posteriormente, conforme as necessidades identificadas na utilização real.

## 4. Visão do produto

Construir uma plataforma que permita às empresas oferecer atendimento digital rápido, contínuo e inteligente, com capacidade de conduzir operações comerciais e acompanhar cada solicitação até um desfecho.

A experiência deverá combinar:

1. Atendimento automatizado.
2. Consulta confiável de informações.
3. Execução de operações comerciais autorizadas.
4. Preparação e acompanhamento de propostas e pedidos.
5. Encaminhamento de situações que exigem intervenção humana.
6. Acompanhamento de pendências comerciais.
7. Visibilidade operacional e supervisão.
8. Histórico e rastreabilidade.
9. Evolução e melhoria contínua.

### Princípio central

**A IA atende, compreende, executa operações autorizadas e acompanha. A equipe humana intervém quando sua participação é necessária.**

O produto deve ter inteligência e complexidade suficientes para conduzir processos, mas sua utilização precisa ser simples para clientes, funcionários e gestores.

O MVP deverá concentrar-se no atendimento comercial, desde o primeiro contato até o aceite da proposta, o registro automático do pedido e sua aprovação interna.

Capacidades mais amplas de gestão operacional, aprendizado avançado e integração com outros setores pertencem à visão de evolução do produto.

## 5. Público e participantes

O mercado inicial ainda não foi escolhido.

Segmentos como restaurantes, consultórios, pequenos comércios e distribuidores foram considerados como possibilidades, mas não existe decisão definitiva.

### Participantes da operação

**Empresa contratante**

É a empresa que contrata o serviço e configura sua operação, suas informações comerciais, seus contatos autorizados e as regras de funcionamento.

**Gerente ou responsável comercial**

É responsável pelas decisões comerciais e pela aprovação ou recusa de pedidos, salvo quando houver autoridade de aprovação atribuída a outro funcionário conforme as configurações da empresa.

Também atua na resolução de ocorrências e situações que ultrapassem as autorizações concedidas a outros participantes.

**Funcionários autorizados**

Podem receber solicitações e executar tarefas conforme as permissões configuradas pela empresa.

A autorização para uma atividade não representa acesso irrestrito às demais operações.

A empresa poderá conceder delegações específicas para determinadas atividades comerciais, observando os limites estabelecidos. A autorização para negociar uma condição especial, por exemplo, não representa automaticamente autoridade para aprovar pedidos.

**Cliente final**

É a pessoa ou empresa que utiliza o canal de atendimento para consultar produtos, negociar e realizar pedidos.

**Contatos de uma empresa cliente**

Uma empresa cliente poderá ter várias pessoas autorizadas a realizar operações comerciais.

O cadastro e o histórico comercial pertencem à empresa cliente, e não a cada contato individual.

A empresa deverá definir as permissões de cada contato autorizado. Assim, contatos vinculados à mesma empresa poderão possuir permissões diferentes.

A autorização de cada contato deverá ser verificada antes de permitir acesso a informações protegidas ou execução de operações comerciais.

A identificação de um contato, isoladamente, não representa autorização irrestrita. Cada ação protegida deverá respeitar as permissões individuais configuradas pela empresa.

## 6. Funcionamento esperado do atendimento

A IA deverá conduzir a maior parte das etapas possíveis sem depender de um funcionário para cada interação.

### Jornada comercial de referência

1. O interessado inicia uma conversa.
2. A IA compreende a solicitação inicial.
3. Quando necessário, conduz a identificação e o cadastro do interessado durante a própria conversa.
4. Verifica o vínculo com a empresa e as permissões individuais do contato antes de liberar informações ou operações protegidas.
5. Compreende os produtos, quantidades e condições desejadas.
6. Consulta a base de informações da empresa.
7. Verifica produtos, características, preços e disponibilidade, conforme os dados disponíveis e as regras comerciais aplicáveis.
8. Apresenta opções e esclarece dúvidas usando informações confiáveis.
9. Organiza a solicitação e apresenta um resumo para conferência.
10. Aguarda a concordância expressa do cliente com a solicitação organizada.
11. Encaminha a solicitação confirmada para o processo comercial seguinte, desde que os dados necessários estejam disponíveis.
12. O processo comercial elabora e apresenta uma proposta ao cliente.
13. O cliente manifesta aceite ou recusa da proposta apresentada, respeitando sua versão, condições e prazos de validade.
14. O aceite válido gera automaticamente o registro do pedido, integral ou parcial, sem exigir uma segunda confirmação do cliente.
15. O pedido segue para aprovação interna no M07. O cliente deverá ser informado de que o pedido aguarda essa aprovação.
16. O gerente ou funcionário com autoridade específica toma a decisão, e a IA comunica o resultado e mantém o histórico atualizado.

A confirmação da solicitação organizada não representa aceite de proposta, aprovação interna ou registro automático de pedido. São eventos distintos, que precisam ser registrados separadamente.

Uma pendência restrita a determinado produto ou item não deverá bloquear automaticamente os demais itens válidos. A plataforma deverá preservar a situação de cada item e permitir o prosseguimento parcial quando as regras comerciais e os dados disponíveis permitirem.

Uma pendência que comprometa a solicitação como um todo poderá impedir o encaminhamento global correspondente.

A plataforma deverá manter outros atendimentos funcionando enquanto uma solicitação aguarda uma decisão ou resposta humana.

### Princípio de continuidade

Uma pendência não deve bloquear o restante da operação.

O sistema deve continuar atendendo outros clientes, acompanhando cada processo individualmente e informando os envolvidos sobre o andamento das solicitações.

A continuidade não significa insistir indefinidamente com o cliente ou transferir automaticamente qualquer situação a um funcionário. Quando a intervenção humana for necessária, a plataforma deverá preservar o contexto e encaminhar a situação para a decisão do responsável adequado.

Quando um atendimento for retomado, as informações necessárias às etapas ainda não concluídas deverão ser revalidadas. Essa revalidação não deverá alterar retroativamente uma proposta já apresentada e ainda válida.

## 7. Catálogo e confiabilidade das informações

A base de informações da empresa será fundamental para o funcionamento da IA.

Na experiência que inspirou o produto, existia uma planilha comercial com informações dos produtos, incluindo:

- Código.
- Nome original.
- Nome normalizado.
- Marca.
- Unidade de precificação.
- Apresentação individual.
- Peso de referência.
- Embalagem.
- Quantidade por embalagem.
- Preço à vista.
- Preço a prazo.

Foi disponibilizado um JSON derivado de uma planilha real da distribuidora, com 77 registros de produtos.

O arquivo apresenta também campos desconhecidos ou não informados, demonstrando a importância de validar a qualidade dos dados antes de disponibilizá-los à IA.

A base servirá como referência para estudar a importação, organização e conferência de informações comerciais.

### Regras de confiabilidade

- A IA não deve inventar características, qualidades ou vantagens dos produtos.
- Deve apresentar informações fornecidas pela empresa ou fontes autorizadas.
- Comparações devem utilizar critérios objetivos e dados disponíveis.
- Não deve afirmar que um produto é melhor que outro sem critérios documentados.
- Quando não houver informação confiável, deve reconhecer a limitação e solicitar esclarecimento ou apoio humano.
- Informações comerciais devem respeitar as permissões de acesso configuradas pela empresa.
- Um produto sem preço definido não poderá ser incluído em uma proposta.
- A ausência de preço deverá bloquear o item afetado e gerar comunicação à gerência para correção do cadastro.
- A ausência de preço de um produto não deverá impedir automaticamente a continuidade dos demais itens válidos da solicitação.
- A IA deverá respeitar a tabela de preços autorizada para o cliente ou grupo correspondente, sem escolher livremente entre tabelas disponíveis.

### Tabelas comerciais e preços

A empresa poderá manter diferentes tabelas comerciais para finalidades, públicos ou grupos de clientes distintos.

A existência de preços diferentes entre tabelas não representa, por si só, inconsistência. A aplicação deverá respeitar a associação autorizada entre cliente e tabela, assim como sua vigência.

Quando não existir tabela válida e autorizada para o cliente, a IA não deverá escolher outra tabela nem reutilizar preços expirados.

Quando houver conflito entre tabelas simultaneamente aplicáveis ao mesmo cliente, a negociação deverá ser bloqueada até a resolução pela pessoa responsável.

A ausência de preço definido para um produto é uma situação diferente da ausência de tabela válida ou de conflito entre tabelas. Cada ocorrência deverá receber o tratamento correspondente.

### Atualização da base

A planilha era atualizada pela equipe da distribuidora, e o gerente avisava quando havia uma nova versão.

Não existia um sistema centralizado para controlar essas atualizações.

A experiência demonstrou a necessidade de mecanismos para receber, importar, comparar, conferir e aprovar informações comerciais.

Para o MVP, a importação e validação inicial do catálogo serão realizadas durante a implantação. Alterações posteriores poderão ser feitas manualmente por pessoas autorizadas.

Uma atualização não deverá apagar silenciosamente o histórico anterior.

A IA poderá identificar problemas e sugerir correções, mas não deverá alterar ou publicar informações comerciais oficiais por conta própria.

Alterações de preços e tabelas deverão respeitar as propostas e operações anteriores, sem modificar retroativamente condições comerciais legitimamente preservadas.

## 8. Histórico de preços e negociações

Uma descoberta importante foi que o preço utilizado em uma negociação precisa ser relacionado ao momento em que aquela negociação aconteceu.

O cliente não deve perder as condições comerciais de uma proposta aceita simplesmente porque uma tabela posterior apresentou valores diferentes.

A plataforma deverá preservar:

- Versão da tabela de preços utilizada.
- Data e horário da emissão e da apresentação efetiva da proposta.
- Produtos e quantidades apresentados.
- Valores e condições comerciais.
- Versões da proposta e alterações realizadas.
- Decisões do cliente.
- Aprovações e responsáveis.
- Resultado final da negociação.

### Validade da proposta

A validade geral da proposta será de **72 horas corridas a partir de sua apresentação efetiva ao cliente**.

A plataforma deverá distinguir:

- **Pendente de decisão:** proposta apresentada, ainda dentro do prazo e sem manifestação conclusiva do cliente.
- **Aceita:** cliente manifesta expressamente seu aceite à versão apresentada, dentro do prazo e das condições aplicáveis.
- **Recusada:** cliente manifesta expressamente que não aceita a proposta.
- **Expirada:** o prazo termina sem aceite do cliente.

A ausência de manifestação dentro do prazo não deverá ser registrada como rejeição expressa. A proposta expirada deverá permanecer no histórico com seu estado e prazo registrados.

### Condições especiais negociadas

Quando uma nova versão apresentar uma condição comercial especial, essa condição terá validade própria de **três dias corridos contados da emissão da nova versão**.

Esse prazo é independente da validade geral de 72 horas da proposta, contada da apresentação efetiva ao cliente.

A condição especial somente poderá ser aceita dentro de seu próprio prazo de validade, ainda que a validade geral da proposta permaneça em aberto.

O vencimento da condição especial impede o aceite daquela condição, mas não invalida automaticamente a proposta original ou outras condições que ainda estejam válidas.

A plataforma deverá preservar as versões, os prazos e as condições de forma independente, sem substituir silenciosamente uma condição por outra.

### Aprovação comercial

O aceite do cliente e a aprovação da empresa são etapas distintas.

As regras estabelecidas são:

- O gerente é o responsável pela aprovação comercial por padrão.
- A própria empresa configura previamente quais funcionários também possuem autoridade para aprovar pedidos.
- Enquanto não houver autoridade de aprovação atribuída a outro funcionário, a responsabilidade permanece com o gerente.
- Funcionários sem autoridade de aprovação não podem liberar pedidos.
- Toda aprovação ou recusa deve registrar quem tomou a decisão e quando.
- A IA acompanha a pendência e comunica o resultado ao cliente.

A autoridade para aprovar pedidos não deve ser confundida com a permissão individual de um contato cliente ou com a delegação específica para negociar condições comerciais especiais.

### Proteção das condições comerciais

As condições comerciais aceitas pelo cliente dentro da validade aplicável devem ser preservadas.

A aprovação interna posterior não autoriza a empresa a alterar unilateralmente produtos, quantidades, preços ou condições aceitas.

Se a empresa não puder aprovar a operação, deverá registrar o motivo e comunicar o cliente, preservando o histórico da negociação.

Alterações posteriores nas tabelas comerciais não modificam retroativamente propostas ou pedidos encerrados.

Quando uma proposta expirar sem aceite, uma negociação posterior deverá considerar as condições comerciais vigentes no momento da nova negociação.

Se houver necessidade de modificar uma proposta já aceita, a alteração deverá ser tratada de forma transparente, com nova apresentação e concordância do cliente, respeitando as regras comerciais aplicáveis.

Essas regras não significam que a plataforma deva assumir gestão financeira, logística ou controle de estoque completo.

## 9. Gestão de ocorrências e pendências

O produto deverá identificar situações que impeçam ou atrasem a continuidade de um atendimento comercial.

Exemplos:

- Estoque insuficiente.
- Falta de aprovação.
- Informação ausente ou desatualizada.
- Produto sem preço definido.
- Ausência de tabela válida para o cliente.
- Conflito entre tabelas simultaneamente aplicáveis.
- Funcionário sem resposta.
- Solicitação que exige uma decisão humana.

### Comportamento esperado

No contexto do MVP, a plataforma deverá:

- Registrar a ocorrência relacionada à operação comercial.
- Informar a empresa responsável.
- Manter o cliente informado sobre o andamento, quando apropriado.
- Encaminhar a situação ao responsável adequado.
- Acompanhar a pendência.
- Solicitar uma ação quando necessário.
- Registrar a resolução, sua causa e a solução aplicada.

A empresa deverá conseguir consultar as ocorrências e acompanhar seus estados, conforme os recursos de supervisão operacional básica.

A ausência de preço definido deverá gerar comunicação à gerência para correção. O item afetado não poderá integrar a proposta enquanto não houver preço válido, mas os demais itens válidos poderão continuar no fluxo comercial.

O sistema não deverá gerar burocracia desnecessária nem envolver muitos funcionários sem necessidade.

A gestão geral de tarefas administrativas, ocorrências de outros setores e processos completos de pós-venda não faz parte do escopo inicial.

### Encaminhamento

A preferência definida é encaminhar solicitações para funcionários específicos, de acordo com o tipo de situação, em vez de utilizar uma fila genérica para tudo.

Em situações especiais, mais de um funcionário poderá participar, mas isso não deverá ser o padrão.

A escolha do responsável deverá respeitar as autorizações e configurações da empresa.

Negociações especiais poderão ser conduzidas por funcionário que possua delegação específica, válida e dentro dos limites autorizados. Essas situações não deverão ser encaminhadas automaticamente ao gerente apenas por envolverem uma condição especial.

Quando não houver delegação válida, ou quando a negociação ultrapassar os limites concedidos, a situação deverá ser encaminhada ao gerente ou responsável competente para decisão.

O encaminhamento deverá preservar o contexto e o histórico do atendimento.

## 10. Painel administrativo e visibilidade operacional

A empresa deverá ter acesso a uma visão operacional dos atendimentos e das situações que exigem atenção.

A supervisão inicial deverá permitir acompanhar o andamento do atendimento comercial sem exigir um painel analítico complexo.

### Visão geral

O painel deverá permitir:

- Visualizar os atendimentos e seus estados.
- Identificar atendimentos com pendências.
- Consultar propostas e decisões.
- Visualizar solicitações aguardando decisão humana.
- Consultar o histórico de intervenções.
- Acompanhar o estado das operações comerciais.

### Visão de atenção

Também deverá permitir identificar:

- Pedidos aguardando aprovação.
- Pendências aguardando funcionários.
- Solicitações que exigem providências.
- Atendimentos que dependem de decisão humana.

### Tempo de espera

O tempo de cada pendência poderá ser utilizado para identificar situações que aguardam uma ação.

A visibilidade do tempo de espera deverá contribuir para a supervisão e a organização da operação.

### Histórico completo

A empresa deverá conseguir consultar o histórico de cada atendimento, incluindo:

- Conversas entre cliente e IA.
- Intervenções dos funcionários.
- Produtos apresentados.
- Preços e propostas.
- Versões e condições comerciais.
- Confirmações e decisões.
- Aceites e recusas.
- Aprovações e recusas internas.
- Ocorrências comerciais.
- Datas e horários dos acontecimentos.

O histórico deverá permitir reconstruir o que aconteceu comercialmente em cada atendimento, não apenas reproduzir uma transcrição de mensagens.

O acesso ao histórico e às informações protegidas deverá respeitar as permissões configuradas pela empresa.

### Limites do MVP

A supervisão operacional básica faz parte do MVP.

Relatórios avançados, indicadores sofisticados, análises de desempenho e painéis analíticos mais completos ficam para evoluções futuras.

## 11. Aprendizado e inteligência operacional

O produto deverá ter capacidade de evoluir com a experiência acumulada durante sua operação.

Não queremos que a visão de longo prazo fique limitada a um chatbot estático de perguntas e respostas.

Entretanto, os mecanismos avançados de aprendizado e inteligência operacional não são requisitos obrigatórios do MVP.

### Aprendizado individual

Cada empresa poderá ter uma evolução própria, baseada em:

- Suas informações.
- Suas regras.
- Suas conversas.
- Suas ocorrências.
- Suas respostas humanas.
- Suas soluções aplicadas.

Quando a IA não souber responder e um funcionário resolver a situação, o sistema poderá identificar uma oportunidade de atualização da base.

Essa informação deverá ser submetida à validação da empresa antes de integrar sua base oficial.

### Aprendizado coletivo

O produto também poderá evoluir como plataforma.

Experiências e padrões generalizáveis de diferentes empresas poderão contribuir para a evolução da inteligência geral do serviço, desde que existam mecanismos adequados de proteção e controle.

Isso deverá respeitar:

- Isolamento dos dados de cada empresa.
- Privacidade dos clientes.
- Confidencialidade das informações comerciais.
- Autorizações aplicáveis.
- Uso controlado de dados e padrões agregados.

Não significa compartilhar catálogos, preços, clientes ou conversas entre empresas.

O aprendizado coletivo permanece como possibilidade de evolução futura, não como compromisso do MVP.

### Reconhecimento de padrões

Em versões futuras, o sistema poderá identificar padrões positivos e negativos.

Exemplos positivos:

- Redução do tempo de atendimento.
- Melhoria na resolução de ocorrências.
- Funcionários que resolvem determinados tipos de solicitação com eficiência.
- Informações que diminuem dúvidas recorrentes.

Exemplos negativos:

- Produtos que geram muitas dúvidas.
- Etapas que atrasam pedidos.
- Informações desatualizadas que provocam erros.
- Pendências recorrentes.
- Aumento de desistências.

### Recomendações

O sistema poderá sugerir melhorias com base nas evidências coletadas.

A IA poderá observar e recomendar, mas a empresa deverá manter o controle sobre alterações relevantes em sua operação.

## 12. Relatórios de evolução

A geração de relatórios periódicos e análises avançadas faz parte da visão de evolução do produto.

Em versões futuras, os relatórios poderão apresentar:

- O que está funcionando bem.
- O que está gerando problemas.
- Padrões identificados.
- Dúvidas frequentes.
- Causas e soluções das ocorrências.
- Informações acrescentadas à base.
- Sugestões de melhoria.
- Evolução dos atendimentos.
- Problemas que continuam recorrentes.

Também poderão ser úteis para os responsáveis pelo produto, permitindo identificar limitações comuns e oportunidades de evolução da plataforma.

Esses relatórios avançados não devem ser confundidos com a supervisão operacional básica prevista para o MVP.

## 13. Modelo de implantação e contratação

O produto deverá ser simples de configurar e utilizar.

Entretanto, a implantação poderá exigir ajuda especializada, principalmente quando a empresa tiver uma base de dados desorganizada ou precisar de auxílio na configuração administrativa.

### Implantação autônoma

A própria empresa poderá realizar a configuração inicial e começar a utilizar o serviço.

### Implantação assistida

Poderá ser oferecida conforme a necessidade do contratante, incluindo:

- Organização e importação da base de dados.
- Conferência e validação das informações.
- Configuração do painel administrativo.
- Cadastro de funcionários e permissões.
- Configuração das regras operacionais.
- Apoio no início da operação.

A implantação assistida não será obrigatória para todas as empresas.

O modelo comercial definitivo, incluindo contratação, cobrança e serviços adicionais, ainda precisa ser validado.

## 14. Princípios orientadores do produto

Os princípios abaixo deverão orientar as decisões futuras:

1. **Simplicidade operacional:** a tecnologia não pode criar burocracia.
2. **Continuidade:** um atendimento pendente não bloqueia os demais.
3. **Confiabilidade:** a IA não inventa informações comerciais.
4. **Rastreabilidade:** decisões e alterações precisam ter histórico.
5. **Responsabilidade:** decisões comerciais respeitam as permissões e delegações estabelecidas pela empresa.
6. **Transparência operacional:** cliente e empresa recebem informações sobre o andamento.
7. **Visibilidade:** a empresa acompanha os atendimentos conforme o nível de supervisão previsto.
8. **Aprendizado controlado:** informações novas passam por validação.
9. **Isolamento:** os dados de cada empresa permanecem separados.
10. **Evolução responsável:** novas capacidades são incorporadas conforme necessidades reais e validação do produto.

## 15. Decisões confirmadas e direcionamentos

As decisões formais e os direcionamentos já estabelecidos incluem:

| Assunto | Decisão ou direcionamento |
|---|---|
| Missão do MVP | Atendimento comercial até o aceite da proposta, o registro automático do pedido e sua aprovação interna |
| Atendimento inicial | Não exige cadastro obrigatório para iniciar a conversa |
| Identificação | Necessária antes de liberar informações e operações protegidas |
| Cadastro | Pode ser conduzido pela IA durante a conversa |
| Permissões | Definidas individualmente para cada contato autorizado |
| Verificação de permissões | Cada ação protegida deve respeitar as permissões individuais configuradas pela empresa |
| Atendimento comercial | A solicitação deve ser compreendida, organizada e confirmada expressamente antes de seguir para o processo comercial seguinte |
| Operação | Executar tarefas quando autorizado e possível |
| Continuidade | Atendimentos independentes não podem bloquear uns aos outros |
| Pendências por item | Uma pendência isolada não bloqueia automaticamente os demais itens válidos |
| Catálogo | Base inicial poderá vir de planilhas validadas |
| Qualidade dos dados | Base deve ser conferida antes de entrar em operação |
| IA comercial | Não deve inventar características, vantagens ou informações comerciais |
| Preço ausente | Produto sem preço definido não entra na proposta; a gerência deve ser comunicada e os demais itens válidos podem prosseguir |
| Tabelas comerciais | A aplicação deve respeitar a tabela autorizada para cada cliente ou grupo |
| Conflito de tabelas | Conflito ocorre quando mais de uma tabela é simultaneamente aplicável ao mesmo cliente e exige resolução |
| Validade geral da proposta | 72 horas corridas a partir da apresentação efetiva ao cliente |
| Condição especial | Três dias corridos a partir da emissão da nova versão que contém a condição especial, em prazo independente da validade geral |
| Expiração | Ausência de aceite até o fim do prazo gera expiração, não rejeição expressa |
| Aceite | Deve estar vinculado à versão e às condições apresentadas, dentro dos prazos aplicáveis |
| Aprovação | Gerente ou funcionário com autoridade de aprovação previamente configurada |
| Delegação comercial | Delegação específica para negociar condições especiais, respeitando seus limites |
| Auditoria | Registrar quem tomou cada decisão e quando |
| Condições comerciais | Condições aceitas devem ser preservadas conforme as regras aplicáveis |
| Pendências | Devem ser registradas e acompanhadas no ciclo comercial |
| Histórico | Empresa pode consultar conversas, intervenções e decisões, respeitando permissões |
| Painel | Supervisão operacional básica faz parte do MVP |
| Pós-venda | Atendimento completo permanece fora do escopo inicial |
| Aprendizado | Novas informações passam por validação antes de integrar a base oficial |
| Aprendizado coletivo | Possibilidade de evolução futura, não requisito do MVP |
| Relatórios avançados | Evolução futura |
| Implantação | Assistida conforme necessidade |

### Decisões formais relacionadas

- **DEC-001 — Supervisão operacional básica no MVP:** estabelece os recursos mínimos de supervisão.
- **DEC-002 — Escopo do atendimento pós-venda:** delimita o foco inicial no atendimento comercial.
- **DEC-003 — Princípios de condução do atendimento comercial:** estabelece as regras de compreensão, confirmação e condução do atendimento.
- **DEC-004 — Permissões individuais dos contatos autorizados:** estabelece que cada contato poderá possuir permissões diferentes.

As decisões formais devem ser consultadas em `docs/decisions/` antes de alterar requisitos relacionados.

A matriz de rastreabilidade é o instrumento complementar para consultar perguntas, decisões, regras derivadas, pendências e relações entre os módulos.

Este documento apresenta a visão consolidada da descoberta. Os detalhes funcionais e critérios de aceitação devem permanecer nos documentos responsáveis, especialmente no PRD e nas decisões formais.

## 16. Hipóteses e questões ainda abertas

As questões abaixo não devem ser tratadas como decisões já aprovadas. A existência de uma questão nesta seção também não significa que ela precise ser resolvida imediatamente: sua necessidade e seu momento deverão ser avaliados conforme a etapa do produto.

### Mercado e posicionamento

- Qual será o primeiro segmento de atuação?
- Qual tipo de empresa apresenta melhor combinação entre dor, capacidade de pagamento e facilidade de implantação?
- Qual será o posicionamento comercial definitivo?

### Canais

- WhatsApp e Telegram foram considerados.
- Ainda não foi decidido qual canal entrará na primeira versão.
- Precisamos definir as integrações necessárias e suas limitações.

### Operação comercial

- Como serão tratados cancelamentos, reservas e pagamentos?
- Como serão tratadas situações de indisponibilidade posterior ao aceite?
- Quais serão os procedimentos operacionais para situações comerciais excepcionais ainda não especificadas?

As regras já definidas sobre validade das propostas, aceite do cliente, proteção das condições comerciais, delegação para negociações especiais e aprovação interna não devem ser reabertas como questões pendentes.

### Dados

- Como as empresas enviarão novas versões de suas planilhas após a implantação inicial?
- Como será feita a comparação entre versões?
- Como serão atualizados preços e estoques na rotina?
- Quais integrações com sistemas de gestão serão necessárias?
- Como será definido o nível de qualidade mínimo da base?

### Gestão

- Quem configura os responsáveis por cada tipo de solicitação?
- Como serão definidos os prazos e regras de encaminhamento?
- Quais informações adicionais serão úteis para a supervisão operacional?

### Inteligência artificial

- Como medir a qualidade das respostas?
- Como validar recomendações?
- Quais dados poderão contribuir para eventual aprendizado coletivo?
- Como serão controladas as mudanças nos modelos e nas bases?

### Produto e negócio

- Como será estruturada a cobrança?
- Quais funcionalidades serão padrão e quais poderão ser serviços adicionais?
- Como será feito o suporte e acompanhamento das empresas?
- Como será validada a proposta de valor com empresas do segmento escolhido?

## 17. Próximas etapas

A descoberta conceitual deu origem aos documentos de visão, escopo, requisitos e decisões do produto.

A documentação está sendo consolidada progressivamente, respeitando a responsabilidade de cada arquivo.

A estrutura atual de trabalho é:

1. Documento 01 — Descoberta do Produto: revisão e consolidação.
2. Documento 02 — Visão e Escopo do Produto: elaborado e revisado; em auditoria de consistência.
3. Documento 03 — PRD: módulos 01 a 05 especificados e revisados; descoberta funcional do M06 concluída, com consolidação e formalização no PRD pendentes; módulos posteriores seguem conforme o planejamento.
4. Documento 04 — Regras de Negócio: reservado para detalhamento posterior, com sua função documental ainda a definir.
5. Documento 05 — Arquitetura Inicial: reservado para elaboração posterior.
6. Documento 06 — Matriz de Escopo do MVP: elaborada e revisada.
7. Documento 07 — Matriz de Rastreabilidade de Decisões e Perguntas: instrumento permanente de consulta e governança.
8. `docs/decisions/` — Registro formal das decisões aprovadas.

A próxima etapa é concluir a auditoria de consistência da documentação, verificando se as decisões aprovadas estão refletidas nos documentos correspondentes e se não existem contradições entre visão, escopo, PRD e matriz do MVP.

O desenvolvimento deverá avançar com base em um escopo suficientemente claro, sem transformar possibilidades futuras em requisitos obrigatórios da primeira versão.

**Princípio de governança:** construir primeiro um produto pequeno, viável e altamente necessário, validar sua utilização real e ampliar suas capacidades conforme as necessidades identificadas.

---

**Nota de governança:** este documento registra a origem, a descoberta e a evolução conceitual do produto. Alterações futuras deverão preservar a distinção entre observações históricas, direcionamentos, decisões confirmadas, regras derivadas, hipóteses e questões ainda pendentes. A matriz de rastreabilidade e os registros formais de decisão deverão ser consultados antes de formular novas perguntas ou alterar requisitos já definidos.