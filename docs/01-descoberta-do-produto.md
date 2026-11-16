# Documento 01 — Descoberta do Produto

**Nome provisório:** Plataforma de Atendimento Inteligente
**Status:** Primeira versão para revisão
**Data:** 16 de novembro de 2026
**Repositório:** `marcos-lima-dev/repositorio-do-produto`

---

## 1. Resumo executivo

A proposta é desenvolver uma plataforma de atendimento inteligente para empresas, capaz de realizar boa parte do processo de atendimento ao cliente, executar tarefas operacionais, acompanhar solicitações e envolver funcionários quando uma decisão ou intervenção humana for necessária.

O produto não deve se limitar a responder perguntas frequentes ou encaminhar mensagens. Seu objetivo é dar continuidade ao atendimento, reduzir o tempo de espera, organizar processos e evitar que solicitações fiquem esquecidas.

Além da automação do atendimento, a plataforma deverá oferecer à empresa visibilidade sobre toda a operação, permitindo acompanhar conversas, pedidos, propostas, pendências, ocorrências e decisões.

O produto também deverá aprender com a operação, identificar padrões positivos e negativos e recomendar melhorias, sempre respeitando as regras de validação e o isolamento dos dados de cada empresa.

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

A ideia do produto nasceu da percepção de que a tecnologia poderia assumir boa parte desse trabalho, mantendo a continuidade dos atendimentos e permitindo que os funcionários interviessem apenas quando necessário.

**Importante:** a distribuidora de laticínios é a inspiração e um cenário real de observação. Isso não significa que o mercado inicial do produto já esteja definido.

## 3. Problema que queremos resolver

Empresas que recebem solicitações de clientes por canais digitais podem enfrentar dificuldades para manter um atendimento rápido, contínuo e organizado.

O problema não está somente na demora da primeira resposta. Está também no que acontece depois dela.

Um atendimento pode depender de:

- Consulta de informações.
- Verificação de disponibilidade.
- Comparação de produtos.
- Preparação de propostas.
- Confirmações do cliente.
- Aprovações internas.
- Respostas de funcionários.
- Resolução de ocorrências.

Quando essas atividades dependem exclusivamente de comunicação manual, o processo pode ficar lento, fragmentado e sujeito a esquecimentos.

O produto pretende reduzir essa dependência operacional, automatizando tarefas possíveis e acompanhando as que ainda precisam de intervenção humana.

## 4. Visão do produto

Construir uma plataforma que permita às empresas oferecer atendimento digital rápido, contínuo e inteligente, com capacidade de executar operações e acompanhar cada solicitação até um desfecho.

A experiência deverá combinar:

1. Atendimento automatizado.
2. Execução de tarefas operacionais.
3. Gestão de propostas e pedidos.
4. Encaminhamento inteligente para funcionários.
5. Acompanhamento de pendências.
6. Visibilidade gerencial.
7. Histórico e rastreabilidade.
8. Aprendizado e melhoria contínua.

### Princípio central

**O chatbot atende, executa e acompanha. A equipe humana intervém quando sua participação é necessária.**

O produto deve ter inteligência e complexidade suficientes para conduzir processos, mas sua utilização precisa ser simples para clientes, funcionários e gestores.

## 5. Público e participantes

O mercado inicial ainda não foi escolhido.

Segmentos como restaurantes, consultórios, pequenos comércios e distribuidores foram considerados como possibilidades, mas não existe decisão definitiva.

### Participantes da operação

**Empresa contratante**

É a empresa que contrata o serviço e configura sua operação.

**Gerente ou responsável comercial**

É responsável pelas decisões comerciais, especialmente aprovação ou recusa de pedidos, salvo delegação previamente autorizada.

**Funcionários autorizados**

Podem receber solicitações e executar tarefas conforme as permissões configuradas pela empresa.

**Cliente final**

É a pessoa ou empresa que utiliza o canal de atendimento para consultar produtos, solicitar serviços, negociar e realizar pedidos.

**Contatos de uma empresa cliente**

Uma empresa cliente poderá ter várias pessoas autorizadas a fazer pedidos. O cadastro e o histórico comercial pertencem à empresa cliente, e não a cada contato individual.

A autorização de cada contato deverá ser validada antes de permitir ações comerciais.

## 6. Funcionamento esperado do atendimento

O chatbot deverá conduzir a maior parte das etapas possíveis sem depender de um funcionário para cada interação.

### Jornada comercial de referência

1. O cliente inicia uma conversa.
2. O chatbot identifica a solicitação.
3. Consulta a base de informações da empresa.
4. Verifica produtos, características, preços e disponibilidade, conforme os dados disponíveis.
5. Apresenta opções ao cliente.
6. Esclarece dúvidas usando informações confiáveis.
7. Prepara uma proposta com itens, quantidades, preços e condições.
8. Apresenta a proposta para conferência.
9. Aguarda a decisão do cliente.
10. Se aceita, encaminha para aprovação interna.
11. O gerente ou funcionário previamente autorizado decide.
12. O chatbot comunica o resultado ao cliente.
13. O atendimento é acompanhado até seu encerramento.

A plataforma deverá manter outros atendimentos funcionando enquanto uma solicitação aguarda uma decisão ou resposta humana.

### Princípio de continuidade

Uma pendência não deve bloquear o restante da operação.

O sistema deve continuar atendendo outros clientes, acompanhando cada processo individualmente e informando os envolvidos sobre o andamento das solicitações.

## 7. Catálogo e confiabilidade das informações

A base de informações da empresa será fundamental para o funcionamento do chatbot.

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

O arquivo apresenta também campos desconhecidos ou não informados, demonstrando a importância de validar a qualidade dos dados antes de disponibilizá-los ao chatbot.

A base servirá como referência para estudar a importação, organização e conferência de informações.

### Regras de confiabilidade

- A IA não deve inventar características, qualidades ou vantagens dos produtos.
- Deve apresentar informações fornecidas pela empresa ou fontes autorizadas.
- Comparações devem utilizar critérios objetivos e dados disponíveis.
- Não deve afirmar que um produto é melhor que outro sem critérios documentados.
- Quando não houver informação confiável, deve reconhecer a limitação e solicitar apoio humano.

### Atualização da base

A planilha era atualizada pela equipe da distribuidora, e o gerente avisava quando havia uma nova versão.

Não existia um sistema centralizado para controlar essas atualizações.

O produto deverá investigar mecanismos para receber, importar, comparar, conferir e aprovar novas versões da base.

Uma atualização não deverá apagar silenciosamente o histórico anterior.

## 8. Histórico de preços e negociações

Uma descoberta importante foi que o preço utilizado em uma negociação precisa ser relacionado ao momento em que aquela negociação aconteceu.

O cliente não deve conseguir alterar retroativamente as condições de uma negociação simplesmente porque uma tabela posterior apresentou valores diferentes.

A plataforma deverá preservar:

- Versão da tabela de preços utilizada.
- Data e horário da proposta.
- Produtos e quantidades apresentados.
- Valores e condições comerciais.
- Decisões do cliente.
- Aprovações e responsáveis.
- Resultado final da negociação.

### Regra de validade da proposta

Foi definida uma validade de três dias para a proposta:

- A proposta é apresentada ao cliente.
- O cliente pode aceitá-la dentro de três dias.
- Se não houver aceite nesse período, a proposta é considerada rejeitada.

### Aprovação comercial

O aceite do cliente não dispensa a aprovação da empresa.

Regras já definidas:

- O gerente é o responsável pela aprovação comercial por padrão.
- A própria empresa configura previamente quais funcionários também podem aprovar.
- Enquanto não houver autorização ou delegação configurada, a responsabilidade permanece com o gerente.
- Funcionários não autorizados não podem liberar pedidos.
- Toda aprovação deve registrar quem tomou a decisão e quando.
- O chatbot acompanha a pendência e comunica o resultado ao cliente.

**Ponto ainda pendente:** definir exatamente o efeito comercial do aceite do cliente sobre os preços e condições enquanto o pedido aguarda aprovação interna.

Também precisamos formalizar o significado de encerramento da negociação e de acordo comercial, sem confundir aceite do cliente com autorização da empresa.

## 9. Gestão de ocorrências e pendências

O produto deverá identificar situações que impeçam ou atrasem a continuidade de um atendimento.

Exemplos:

- Estoque insuficiente.
- Falta de aprovação.
- Informação ausente ou desatualizada.
- Funcionário sem resposta.
- Sobrecarga operacional.
- Solicitação que exige uma decisão humana.

### Comportamento esperado

- Registrar a ocorrência.
- Informar a empresa responsável.
- Manter o cliente informado sobre o andamento.
- Encaminhar a situação ao funcionário adequado.
- Acompanhar o prazo.
- Cobrar uma ação quando necessário.
- Escalar para um substituto previamente autorizado, quando aplicável.
- Registrar a resolução, sua causa e a solução aplicada.

A empresa deverá conseguir consultar as ocorrências e acompanhar seus estados.

O sistema não deverá gerar burocracia desnecessária nem envolver muitos funcionários sem necessidade.

### Encaminhamento

A preferência definida é encaminhar solicitações para funcionários específicos, de acordo com o tipo de situação, em vez de utilizar uma fila genérica para tudo.

Em situações especiais, mais de um funcionário poderá participar, mas isso não deverá ser o padrão.

## 10. Painel administrativo e visibilidade operacional

A empresa deverá ter acesso a uma visão completa da operação.

Não apenas dos atendimentos problemáticos.

### Visão geral

O painel deverá permitir acompanhar:

- Todos os atendimentos em andamento.
- Atendimentos concluídos.
- Clientes envolvidos.
- Etapas de cada atendimento.
- Pedidos e propostas.
- Solicitações aguardando decisão.
- Ocorrências abertas e resolvidas.
- Responsáveis por cada pendência.

### Visão de atenção

Também deverá destacar:

- Pedidos aguardando aprovação.
- Pendências aguardando funcionários.
- Solicitações próximas do prazo.
- Pendências atrasadas.
- Ocorrências recorrentes.

### Tempo de espera

O tempo de cada pendência deverá ser visível.

A empresa precisa identificar não apenas quantas solicitações estão pendentes, mas há quanto tempo cada uma aguarda uma ação.

### Histórico completo

A empresa deverá conseguir abrir qualquer atendimento e consultar integralmente:

- Conversas entre cliente e chatbot.
- Intervenções dos funcionários.
- Produtos apresentados.
- Preços e propostas.
- Confirmações e decisões.
- Aprovações e recusas.
- Ocorrências.
- Datas e horários dos acontecimentos.

O histórico deverá permitir reconstruir o que aconteceu comercialmente em cada atendimento, não apenas reproduzir uma transcrição de mensagens.

## 11. Aprendizado e inteligência operacional

O produto deverá evoluir com a experiência acumulada durante a operação.

Não queremos um chatbot limitado a uma base estática de perguntas e respostas.

### Aprendizado individual

Cada empresa deverá ter uma evolução própria, baseada em:

- Suas informações.
- Suas regras.
- Suas conversas.
- Suas ocorrências.
- Suas respostas humanas.
- Suas soluções aplicadas.

Quando o chatbot não souber responder e um funcionário resolver a situação, o sistema poderá identificar uma oportunidade de atualização da base.

Essa informação deverá ser submetida à validação da empresa antes de integrar sua base oficial.

### Aprendizado coletivo

O produto também deverá melhorar como plataforma.

Experiências e padrões generalizáveis de diferentes empresas poderão contribuir para a evolução da inteligência geral do serviço.

Isso deverá respeitar:

- Isolamento dos dados de cada empresa.
- Privacidade dos clientes.
- Confidencialidade das informações comerciais.
- Autorizações aplicáveis.
- Uso controlado de dados e padrões agregados.

Não significa compartilhar catálogos, preços, clientes ou conversas entre empresas.

### Reconhecimento de padrões

O sistema deverá identificar padrões positivos e negativos.

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

O sistema deverá sugerir melhorias com base nas evidências coletadas.

A IA poderá observar, aprender e recomendar, mas a empresa deverá manter o controle sobre alterações relevantes em sua operação.

## 12. Relatórios de evolução

O produto deverá gerar relatórios periódicos para a empresa contratante.

Os relatórios deverão apresentar:

- O que está funcionando bem.
- O que está gerando problemas.
- Padrões identificados.
- Dúvidas frequentes.
- Causas e soluções das ocorrências.
- Informações acrescentadas à base.
- Sugestões de melhoria.
- Evolução dos atendimentos.
- Problemas que continuam recorrentes.

Também serão úteis para os responsáveis pelo produto, permitindo identificar limitações comuns e oportunidades de evolução da plataforma.

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

## 14. Princípios orientadores do produto

Os princípios abaixo deverão orientar as decisões futuras:

1. **Simplicidade operacional:** a tecnologia não pode criar burocracia.
2. **Continuidade:** um atendimento pendente não bloqueia os demais.
3. **Confiabilidade:** a IA não inventa informações comerciais.
4. **Rastreabilidade:** decisões e alterações precisam ter histórico.
5. **Responsabilidade:** decisões comerciais respeitam as permissões da empresa.
6. **Transparência operacional:** cliente e empresa recebem informações sobre o andamento.
7. **Visibilidade:** a empresa acompanha todos os atendimentos.
8. **Aprendizado controlado:** informações novas passam por validação.
9. **Isolamento:** os dados de cada empresa permanecem separados.
10. **Evolução contínua:** o produto identifica oportunidades de melhoria.

## 15. Decisões confirmadas

| Assunto | Decisão |
|---|---|
| Atendimento | Chatbot deve conduzir a maior parte do processo |
| Operação | Deve executar tarefas quando autorizado e possível |
| Continuidade | Atendimentos independentes não podem bloquear uns aos outros |
| Catálogo | Base inicial poderá vir de planilhas |
| Qualidade dos dados | Base deve ser conferida antes de entrar em operação |
| IA comercial | Não deve inventar características ou vantagens |
| Propostas | Validade de três dias para aceite do cliente |
| Aprovação | Gerente ou funcionário previamente autorizado |
| Delegação | Configurada previamente pela empresa |
| Auditoria | Registrar quem aprovou e quando |
| Pendências | Devem ser registradas, acompanhadas e cobradas |
| Histórico | Empresa pode consultar todas as conversas e intervenções |
| Painel | Deve mostrar todos os atendimentos |
| Inteligência | Identificar padrões positivos e negativos |
| Aprendizado | Individual e coletivo, com isolamento e proteção dos dados |
| Relatórios | Devem apresentar evolução e recomendações |
| Implantação | Assistida conforme necessidade |

## 16. Hipóteses e questões ainda abertas

As questões abaixo não devem ser tratadas como decisões já aprovadas.

### Mercado e posicionamento

- Qual será o primeiro segmento de atuação?
- Qual tipo de empresa apresenta melhor combinação entre dor, capacidade de pagamento e facilidade de implantação?
- Qual será o posicionamento comercial definitivo?

### Canais

- WhatsApp e Telegram foram considerados.
- Ainda não foi decidido quais canais entrarão na primeira versão.
- Precisamos definir as integrações necessárias e suas limitações.

### Operação comercial

- O que exatamente caracteriza o encerramento de um pedido?
- Em que momento os preços e condições ficam definitivamente protegidos?
- O que acontece quando o cliente aceita dentro do prazo, mas a aprovação interna demora?
- Como tratar alterações de preços enquanto existem propostas pendentes?
- Como serão tratados cancelamentos, reservas, pagamentos e indisponibilidade posterior?

### Dados

- Como as empresas enviarão novas versões de suas planilhas?
- Como será feita a comparação entre versões?
- Como serão atualizados preços e estoques na rotina?
- Quais integrações com sistemas de gestão serão necessárias?
- Como será definido o nível de qualidade mínimo da base?

### Gestão

- Quem configura os responsáveis por cada tipo de solicitação?
- Como serão definidos os prazos e regras de escalonamento?
- Quais indicadores serão prioritários nos relatórios?

### Inteligência artificial

- Como medir a qualidade das respostas?
- Como validar recomendações?
- Quais dados poderão contribuir para o aprendizado coletivo?
- Como serão controladas as mudanças nos modelos e nas bases?

### Produto e negócio

- Qual será o escopo do MVP?
- Como será estruturada a cobrança?
- Quais funcionalidades serão padrão e quais poderão ser serviços adicionais?
- Como será feito o suporte e acompanhamento das empresas?

## 17. Próxima etapa

Com a descoberta conceitual consolidada, o próximo trabalho será transformar essa visão em uma estrutura funcional.

A sequência proposta é:

1. Documento de Visão e Escopo do Produto.
2. Identificação dos módulos e responsabilidades.
3. Mapeamento das jornadas e fluxos.
4. Documento de Requisitos do Produto (PRD).
5. Formalização das regras de negócio.
6. Estudo da arquitetura inicial.
7. Definição do MVP.

**Não iniciar o desenvolvimento antes de termos clareza suficiente sobre o escopo da primeira versão.**

---

**Nota de governança:** este documento registra a descoberta realizada até 16/11/2026. Alterações futuras deverão preservar a distinção entre decisões confirmadas, hipóteses e questões ainda pendentes.