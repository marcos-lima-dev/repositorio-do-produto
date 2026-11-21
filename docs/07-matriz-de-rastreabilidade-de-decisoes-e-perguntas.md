# Matriz de Rastreabilidade de Decisões e Perguntas

**Projeto:** Plataforma de Atendimento Inteligente

**Versão:** 0.8

**Data:** 20/11/2026

**Status:** Em construção — consolidação e rastreabilidade do conhecimento da descoberta

**Finalidade:** Evitar perguntas repetidas, reutilizar decisões anteriores, identificar regras derivadas, detectar contradições e orientar as próximas etapas de descoberta e documentação.

---

## 1. Objetivo

Esta matriz é a base de consulta do conhecimento acumulado durante a descoberta e especificação do produto.

Sua função é permitir que cada nova etapa aproveite decisões e respostas anteriores, evitando retrabalho, inconsistências e perguntas semanticamente semelhantes já respondidas.

A matriz deve funcionar como instrumento de consulta ativa, e não apenas como um histórico de decisões.

Antes de formular uma pergunta, propor uma regra ou iniciar um novo módulo, deve-se consultar:

- Decisões formais registradas em `docs/decisions/`.

- Perguntas e respostas das descobertas anteriores.

- Requisitos e regras estabelecidos no PRD.

- Regras derivadas de decisões aprovadas.

- Restrições e limites do MVP.

- Pendências e decisões ainda não resolvidas.

- Exceções e condições especiais já discutidas.

- Módulos relacionados ao assunto em análise.

**Princípio central:** o conhecimento acumulado deve tornar as próximas etapas mais rápidas, consistentes e precisas.

## 2. Classificação do conhecimento

| Classificação | Significado | Conduta |

|---|---|---|

| Aprovada na descoberta | Decisão expressamente confirmada pelo usuário durante a descoberta | Aplicar sem perguntar novamente |

| Formalizada | Decisão registrada no documento de decisão ou no documento funcional correspondente | Utilizar como regra documental vigente |

| Derivada | Consequência lógica de uma ou mais decisões aprovadas | Aplicar quando a relação lógica for segura e registrar a origem |

| Pendente | Questão ainda sem resposta suficiente | Avaliar quando precisa ser decidida |

| Substituída | Decisão alterada por outra posterior | Preservar histórico e utilizar a decisão vigente |

| Em revisão | Possível contradição ou necessidade justificada de reavaliação | Investigar antes de aplicar |

### 2.1. Situação da documentação

É necessário distinguir três situações:

- **Aprovada na descoberta:** o usuário confirmou a regra, mas ela ainda pode não estar registrada no repositório.

- **Formalizada:** a regra está registrada no documento de decisão ou no documento funcional correspondente.

- **Auditada:** sua aplicação foi conferida nos documentos relacionados e não apresenta inconsistências conhecidas.

Uma decisão não deve ser considerada formalizada apenas porque foi aprovada em uma conversa.

Uma regra derivada também não deve ser apresentada como se tivesse sido expressamente aprovada pelo usuário.

### 2.2. Rastreabilidade obrigatória

Cada conhecimento relevante deve permitir identificar:

1. O que foi decidido ou respondido.

2. Em qual etapa ou conversa surgiu.

3. Qual decisão ou regra lhe dá fundamento.

4. Se foi expressamente aprovado ou derivado.

5. Quais módulos são afetados.

6. Se já foi incorporado ao PRD ou a uma decisão formal.

7. Se existe alguma exceção ou pendência relacionada.

## 3. Procedimento obrigatório antes de formular perguntas

Antes de apresentar qualquer nova pergunta:

1. Identificar o assunto e a regra de negócio envolvida.

2. Pesquisar perguntas anteriores semanticamente semelhantes.

3. Consultar decisões formais relacionadas.

4. Consultar os módulos do PRD que tratam do assunto.

5. Verificar se existe uma resposta expressamente aprovada.

6. Verificar se a resposta pode ser deduzida de decisões anteriores.

7. Identificar exceções e diferenças reais de contexto.

8. Verificar possíveis contradições entre decisões e documentos.

9. Avaliar se a questão é necessária para o MVP.

10. Avaliar se a decisão precisa ser tomada agora ou pode aguardar outro módulo.

11. Somente apresentar a pergunta se existir uma decisão nova que não possa ser deduzida com segurança.

### 3.1. Regras de consulta

- Não repetir uma pergunta apenas porque sua redação mudou.

- Não reabrir decisões aprovadas sem justificativa concreta.

- Não transformar uma consequência lógica em uma nova pergunta.

- Não presumir que uma regra se aplica a contextos diferentes sem verificar suas consequências.

- Não transformar exemplos em requisitos.

- Não antecipar decisões que pertencem a módulos futuros sem necessidade.

- Não inventar respostas para preencher lacunas.

- Não confundir permissão de consulta com permissão de executar uma operação.

- Não confundir autorização comercial com aprovação interna.

- Não confundir uma decisão aprovada na descoberta com sua formalização no PRD.

- Não ampliar o escopo do MVP apenas porque uma funcionalidade foi mencionada.

Se houver diferença real entre dois contextos, apresentar a diferença e explicar por que ela exige uma decisão adicional.

### 3.2. Resultado da consulta

Toda consulta deve terminar com uma das seguintes classificações:

| Resultado | Conduta |

|---|---|

| Já respondida | Aplicar a decisão existente |

| Regra derivada | Aplicar e registrar a origem |

| Lacuna real | Formular uma nova pergunta |

| Contradição | Interromper a definição e investigar |

| Decisão futura | Registrar para o módulo responsável |

| Fora do MVP | Não incorporar automaticamente |

## 4. Identificadores e organização

A matriz utiliza identificadores próprios, independentes dos documentos formais de decisão.

| Prefixo | Utilização |

|---|---|

| DEC | Decisão formal do repositório |

| MXX | Grupo de conhecimento relacionado a um módulo |

| Q | Pergunta identificada durante a descoberta |

| P | Pendência ainda não resolvida ou registrada historicamente |

| RD | Regra derivada de decisão anterior |

Os identificadores MXX, Q, P e RD são referências de rastreabilidade. Não substituem os registros formais do PRD ou de `docs/decisions/`.

Os identificadores existentes devem ser preservados. Uma alteração de conteúdo não justifica renumerar registros anteriores.

## 5. Matriz de decisões e conhecimentos existentes

### 5.1. Decisões formais anteriores

| Assunto | Regra estabelecida | Origem | Aplicação |

|---|---|---|---|

| Supervisão operacional | Supervisão básica integra o MVP | DEC-001 | M08 |

| Pós-venda | Pós-venda completo fica fora do escopo inicial | DEC-002 | Limites do MVP |

| Condução do atendimento | IA compreende, organiza e confirma a solicitação antes de encaminhar ao M06 | DEC-003 | M05/M06 |

| Identificação e autorização | Identificação e vínculo com a empresa não significam acesso irrestrito; as permissões de cada contato autorizado devem ser verificadas individualmente | DEC-003 e DEC-004 | M01 e demais módulos |

| Retomada | Até duas tentativas sem resposta, sem presumir concordância | DEC-003 | M05 |

| Permissões individuais | A empresa define permissões de cada contato autorizado | DEC-004 | Todos os módulos |

### 5.2. Conhecimento aprovado durante a descoberta do M04

O registro abaixo consolida regras esclarecidas durante a descoberta sobre integridade dos preços e aplicação das tabelas comerciais.

A regra foi incorporada ao PRD, nas seções 21.2 a 21.8, e sua correspondência documental foi conferida na auditoria de 20/11/2026.

| ID | Assunto | Regra estabelecida | Aplicação |

|---|---|---|---|

| M04-01 | Integridade dos preços e aplicação das tabelas comerciais | Nenhum produto pode ser utilizado em uma proposta sem preço definido. A ausência de preço bloqueia a utilização daquele produto e deve gerar comunicação à gerência para correção. Essa pendência isolada não impede a continuidade dos demais itens comercialmente válidos, respeitando a regra de proposta parcial M06-03. Tabelas com preços diferentes podem coexistir quando possuem finalidades e públicos ou clientes específicos. A plataforma deve aplicar somente a tabela autorizada para o cliente correspondente; a IA não escolhe livremente entre tabelas. A diferença de preços entre tabelas distintas não constitui conflito por si só. O conflito ocorre quando duas ou mais tabelas são simultaneamente aplicáveis ao mesmo cliente e não existe uma regra válida de prevalência que determine qual deverá ser utilizada. | M04/M06 |

**Distinções importantes para a aplicação desta regra:**

- Ausência de preço: o produto não pode ser utilizado na proposta e a gerência deve ser comunicada para correção.

- Diferença legítima entre tabelas: pode existir quando as tabelas possuem finalidades e públicos ou clientes distintos, respeitando as associações autorizadas.

- Conflito de tabelas: ocorre quando duas ou mais tabelas são simultaneamente aplicáveis ao mesmo cliente e não existe uma regra válida de prevalência que determine qual deverá ser utilizada.

- Pendência isolada de um produto: não bloqueia automaticamente os demais itens comercialmente válidos, respeitando M06-03.

A ausência de preço e o conflito de tabelas são situações diferentes e não devem ser tratados como se fossem o mesmo problema.

### 5.3. Conhecimento aprovado durante a descoberta do M06

Os registros abaixo consolidam o conhecimento aprovado durante a descoberta do M06. Sua formalização documental e sua aplicação no PRD ainda precisam ser verificadas.

Os identificadores M06-01 a M06-45 foram preservados. Os registros M06-46 a M06-49 incorporam complementações de assuntos já tratados na descoberta, sem substituir os identificadores anteriores.

O registro M06-50, incluído na versão anterior, foi retirado por duplicar o conteúdo já estabelecido em M06-28. Seu identificador não será reutilizado.

| ID | Assunto | Regra estabelecida | Aplicação |

|---|---|---|---|

| M06-01 | Elaboração | A plataforma elabora propostas automaticamente, sem aprovação prévia individual do gerente para cada proposta. Situações excepcionais ou que exijam decisão humana são encaminhadas ao responsável. | M06 |

| M06-02 | Conteúdo | A proposta apresenta identificação da empresa/cliente, produtos, descrição e apresentação, quantidades, unidades, preços unitários, totais por item, total geral, condições comerciais e de pagamento aplicáveis, data de emissão e validade. | M06 |

| M06-03 | Proposta parcial | Itens resolvidos podem ser apresentados enquanto outros permanecem pendentes. Os itens pendentes devem ser identificados e separados. Quando resolvidos, podem integrar nova versão ou proposta complementar, preservando o histórico. | M05/M06 |

| M06-04 | Aceite parcial | O cliente pode selecionar os itens desejados. A plataforma gera nova versão com os itens escolhidos e valores recalculados, preservando a proposta original. Itens não selecionados não são considerados recusados definitivamente. | M06 |

| M06-05 | Validade da proposta | A proposta possui validade de 72 horas corridas e exatas, contadas a partir da apresentação efetiva ao cliente. O prazo não começa na criação interna, não é prorrogado automaticamente e não é ampliado pelas tentativas de retomada da conversa. | M06 |

| M06-06 | Expiração | Proposta expirada não pode ser aceita automaticamente. É necessária nova consulta de preços, condições e disponibilidade, seguida da emissão de nova proposta e de nova oportunidade de aceite. Aceite realizado no instante do vencimento ou depois dele não é válido. | M06 |

| M06-07 | Versionamento | Alterações de conteúdo, itens, quantidades ou condições geram novas versões. A versão anterior permanece preservada. O número principal da proposta é mantido, com identificação de versão. | M06 |

| M06-08 | Recusa | A IA reconhece a recusa sem pressionar o cliente ou insistir na compra. Pode perguntar se ele deseja encaminhamento ao gerente. Se não desejar, registra a recusa e encerra a proposta conforme o fluxo definido. | M06 |

| M06-09 | Negociação | A IA não negocia descontos nem cria condições comerciais excepcionais. Pode esclarecer condições oficiais e encaminhar solicitações fora das condições disponíveis para avaliação humana. | M06 |

| M06-10 | Autoridade | Gerente pode negociar e autorizar condições especiais. Funcionário pode atuar quando receber delegação específica, respeitando os limites autorizados. A IA organiza, registra e apresenta a condição autorizada, mas não negocia nem concede exceções. | M06 |

| M06-11 | Delegação | Gerente pode delegar uma negociação específica a funcionário, registrando quem delegou, quem recebeu a delegação e qual atendimento ou proposta está abrangido. A delegação não concede poderes comerciais permanentes. | M06 |

| M06-12 | Limites | Funcionário atua dentro dos limites definidos pelo gerente. Esses limites podem variar conforme funcionário e negociação. Exceções ou condições que ultrapassem os limites dependem de autorização adicional do gerente. | M06 |

| M06-13 | Condição especial | Condição negociada fica vinculada à operação, proposta e cliente correspondentes. Não altera automaticamente tabelas comerciais nem se torna condição permanente ou aplicável a outros clientes. | M06 |

| M06-14 | Alterações | Alteração de condição especial já apresentada ao cliente exige nova versão, preservação da versão anterior e comunicação da mudança. O cliente decide se aceita a nova condição. | M06 |

| M06-15 | Aceite | Aceite válido, integral ou parcial, gera automaticamente o registro do pedido, sem exigir uma segunda confirmação do cliente. O pedido segue para aprovação interna no M07. O cliente deve ser informado de que o pedido aguarda essa aprovação. | M06/M07 |

| M06-16 | Aprovação | Aceite do cliente não substitui aprovação interna da empresa. Se o pedido não for aprovado, a decisão deve ser registrada com seu motivo, comunicada ao cliente e preservada no histórico. A empresa não pode alterar unilateralmente as condições comerciais aceitas. | M06/M07 |

| M06-17 | Permissão de aceite | O contato precisa possuir permissão específica para aceitar propostas e gerar pedidos. Permissão para consultar preços ou propostas não implica autorização para assumir esse compromisso comercial. | M01/M06 |

| M06-18 | Outro contato | Outro contato vinculado à mesma empresa pode aceitar proposta apresentada originalmente a outro contato, desde que possua a permissão específica necessária. O sistema registra quem recebeu originalmente e quem realizou o aceite. | M01/M06 |

| M06-19 | Aceite duplicado | O primeiro aceite válido prevalece. Tentativas posteriores não geram pedidos adicionais para a mesma versão. A plataforma registra as tentativas posteriores e informa que a proposta já foi aceita. | M06/M07 |

| M06-20 | Desistência | Desistência após aceite é registrada e encaminhada para tratamento interno. A proposta aceita e o pedido permanecem preservados. A IA não apaga nem desfaz automaticamente o pedido. | M06/M07 |

| M06-21 | Integridade | Propostas emitidas não podem ser apagadas definitivamente, inclusive por ação do gerente. Recusa, expiração, substituição, cancelamento e correções preservam o histórico. | M06 |

| M06-22 | Identificação | Propostas possuem número único, por exemplo `PROP-2026-000001`, e versões identificadas, como V1 e V2. São registrados os responsáveis pela elaboração e pela entrega. | M06 |

| M06-23 | Histórico | O histórico registra conteúdo integral, destinatários, empresa, cliente, contato, canal, data e hora de emissão, validade com timestamps, responsáveis, tentativas de envio e eventos relevantes, como apresentação, entrega, visualização quando confirmada, alterações, aceite, recusa, expiração, substituição e cancelamento. | M06 |

| M06-24 | WhatsApp | WhatsApp é canal de comunicação. A proposta é um registro comercial formal e independente da mensagem, consultável na área própria da plataforma. Falhas de integração não apagam a proposta nem seu histórico. | M06 |

| M06-25 | Eventos de comunicação | Envio, entrega, recebimento, visualização e aceite são eventos distintos. A plataforma não presume visualização sem confirmação técnica. Quando não houver confirmação disponível, a IA pode perguntar se o cliente recebeu e conseguiu consultar a proposta. Recebimento não significa aceite. | M06 |

| M06-26 | Falha de envio | Falha não apaga a proposta. A plataforma registra tentativas e resultados, permite novas tentativas e não informa entrega sem confirmação. Falhas temporárias podem gerar retentativas automáticas, respeitando limites técnicos do canal. Em falha permanente ou persistente, o gerente é informado. | M06 |

| M06-27 | PDF | Falha na geração do PDF não invalida a proposta nem impede sua apresentação pelo WhatsApp quando esse canal estiver disponível. O erro deve ser registrado, uma nova tentativa de geração pode ser realizada e o cliente deve ser informado de que o PDF está temporariamente indisponível. Não se deve afirmar que o arquivo foi entregue quando isso não foi confirmado. | M06 |

| M06-28 | Consulta | Área própria permite listar e pesquisar propostas por número ou cliente, filtrar por situação, abrir o conteúdo integral e consultar versões anteriores e histórico de eventos. A área é enxuta e não representa um CRM ou sistema de gestão abrangente. Não inclui funil complexo, relatórios ou gráficos avançados nem campanhas automáticas. | M06 |

| M06-29 | Permissões de consulta | Gerente possui visão geral das propostas da empresa. Funcionários consultam conforme permissões individuais. A IA acessa apenas os registros necessários ao atendimento, respeitando permissões e limites. Cliente consulta suas próprias propostas pelo canal autorizado. | M01/M06 |

| M06-30 | Estoque | Proposta não reserva estoque nem bloqueia quantidades. | M06 |

| M06-31 | Disponibilidade | A disponibilidade consultada durante a elaboração fica registrada com referência temporal. Deve ser revalidada no momento adequado do processamento do pedido, a ser especificado no M07. | M06/M07 |

| M06-32 | Indisponibilidade | Se um item ficar indisponível, a plataforma informa o cliente e pode apresentar alternativas autorizadas. Substituição ou redução de quantidade exige decisão do cliente. Nenhuma alteração é realizada unilateralmente. | M06/M07 |

| M06-33 | Notificações | Situações que exigem decisão humana são encaminhadas ao gerente, incluindo negociações de preço ou condições especiais quando não houver delegação válida ou quando a solicitação ultrapassar os limites autorizados, erro em proposta apresentada, falha persistente de envio, pedido de prazo adicional e outras situações que não possam ser resolvidas com segurança pela IA. O aviso identifica cliente, proposta, motivo e acesso ao atendimento. | M06 |

| M06-34 | Pendência humana | Solicitação que depende de gerente ou funcionário delegado permanece pendente e registrada. O cliente é informado de que a solicitação foi encaminhada para avaliação, sem promessa de prazo não confirmado. O contexto da conversa é preservado. | M06 |

| M06-35 | Condição original | Durante uma negociação, preços e condições da proposta original permanecem válidos até o fim de seu prazo, salvo se a proposta expirar ou for substituída por uma nova versão aceita conforme as regras aplicáveis. Mudanças no catálogo não alteram silenciosamente propostas já apresentadas. | M06 |

| M06-36 | Recusa de condição especial | Se o gerente recusar a condição especial solicitada, a decisão é registrada e comunicada ao cliente. A proposta original continua disponível para aceite enquanto estiver dentro do prazo de validade. Se já estiver expirada, é necessária nova consulta e nova proposta. | M06 |

| M06-37 | Estados da proposta | Os estados definidos são: Em elaboração; Apresentada; Aguardando decisão; Aguardando avaliação do gerente; Aceita; Recusada; Expirada; Substituída. Aguardando avaliação do gerente indica dependência de decisão humana e não significa recusa ou cancelamento. | M06 |

| M06-38 | Prazo adicional | Se o cliente pedir mais tempo para decidir, a IA não prorroga automaticamente a proposta. Deve oferecer encaminhamento ao gerente para avaliação. | M06 |

| M06-39 | Ausência de resposta do gerente | Se o gerente não responder a uma solicitação pendente, ela permanece registrada e aguardando decisão. A IA informa o cliente sem prometer prazo, preservando contexto e histórico. | M06 |

| M06-40 | Encerramento da delegação | Delegação termina quando a negociação específica é concluída, quando a condição é autorizada ou recusada, quando a proposta é encerrada ou quando o cliente desiste da negociação. Uma nova negociação exige nova delegação. | M06 |

| M06-41 | Revogação da delegação | Gerente pode revogar a delegação antes da conclusão. O funcionário perde imediatamente a autorização para continuar aquela negociação. O histórico é preservado; o gerente assume ou delega a outra pessoa. A comunicação ao cliente não precisa expor detalhes internos da empresa. | M06 |

| M06-42 | Solicitação de ajuda do funcionário | Funcionário pode solicitar orientação ou autorização adicional quando a negociação ultrapassar seus limites. A negociação aguarda decisão; o funcionário não pode assumir uma decisão para a qual não tem autorização. | M06 |

| M06-43 | Alteração de condição autorizada | Antes de apresentar uma condição ao cliente, ela pode ser substituída, preservando a decisão anterior. Depois de apresentada, a mudança exige nova versão, preserva a anterior, comunica o cliente e deixa a decisão de aceite com ele. | M06 |

| M06-44 | Registro da autorização | A autorização de condição especial registra condição, preço ou desconto, justificativa interna, responsável pela autorização, funcionário que conduziu a negociação quando diferente, data e hora, proposta vinculada e validade. A justificativa é obrigatória, curta e objetiva. | M06 |

| M06-45 | Limites e exceções | Gerente define limites específicos por funcionário e negociação, incluindo percentual de desconto, condições de pagamento, alterações permitidas e restrições. Pode alterar limites ativos, com efeito imediato, registrando responsável e data/hora, preservando os limites anteriores e decisões legitimamente tomadas. Funcionário pode atuar autonomamente dentro dos limites, mas exceções dependem exclusivamente do gerente. | M06 |

| M06-46 | Validade da condição negociada | A condição especial negociada possui validade de três dias corridos, contados a partir da emissão da nova versão da proposta que contém essa condição. Esse prazo é independente da validade geral da proposta, que corresponde a 72 horas corridas e exatas a partir da apresentação efetiva ao cliente. O vencimento da condição especial impede seu aceite, mesmo que a validade geral da proposta ainda esteja em curso. A validade geral da proposta não prorroga nem recupera uma condição especial vencida. Os dois marcos devem ser registrados separadamente. | M06 |

| M06-47 | Alteração de quantidade | Quando o cliente solicitar alteração de quantidade dentro das condições comerciais tabeladas, a IA pode consultar a tabela vigente, atualizar os valores e gerar nova versão da proposta. Quando a alteração envolver negociação por volume ou condição especial fora das regras tabeladas, o atendimento deve ser encaminhado ao gerente. | M06 |

| M06-48 | Equivalência dos formatos | A apresentação da proposta pelo WhatsApp e sua disponibilização em PDF representam a mesma versão da proposta. São formatos ou canais de apresentação do mesmo registro comercial, não propostas independentes. | M06 |

| M06-49 | Correção de proposta apresentada | Erro identificado em proposta já apresentada deve ser encaminhado ao gerente para avaliação. A versão original é preservada, a correção é registrada e a nova versão autorizada é apresentada ao cliente, com comunicação da alteração. | M06 |

### 5.4. Conhecimento aprovado durante a descoberta do M07
Os registros abaixo consolidam decisões aprovadas durante a descoberta do M07. Representam conhecimento aprovado na descoberta, não comprovam formalização no PRD nem implementação. As pendências parcialmente resolvidas permanecem abertas para os pontos explicitamente indicados.

| ID | Assunto | Regra estabelecida | Origem/observação |
|---|---|---|---|
| M07-01 | Contexto para aprovação | A pessoa responsável pela aprovação precisa compreender o contexto da operação: itens e quantidades do pedido, conteúdo da proposta efetivamente apresentado ao cliente, versão e condições aceitas, registro do aceite e situação atual da capacidade de atendimento. O aceite já registrado deve ser exibido como evidência, sem exigir uma segunda confirmação do cliente. | M07 |
| M07-02 | Revalidação antes da aprovação | A disponibilidade deve ser revalidada imediatamente antes da aprovação interna, considerando os produtos, quantidades e a data combinada de entrega. A análise deve distinguir disponibilidade atual da capacidade de atender na data futura acordada. | M07 |
| M07-03 | Evidência da disponibilidade | A revalidação deve deixar registro histórico do resultado, data/hora da consulta, produtos e quantidades, situação por item, data de entrega considerada e restrições ou divergências identificadas. O registro não reserva estoque nem garante disponibilidade futura. | M07 |
| M07-04 | Previsão de reposição | A possibilidade de aprovar um pedido com base em previsão de reposição antes da data de entrega ainda não foi definida. Não presumir que previsão equivale a disponibilidade confirmada. | M07 — pendência P-002/P-006 |
| M07-05 | Kanban de aprovação | A fila de aprovação deve ser apresentada em uma visualização centralizada no estilo Kanban. O Kanban é uma forma de visualizar e organizar o trabalho, não uma definição automática dos estados de negócio do pedido. | M07 |
| M07-06 | Responsabilidade pelo pedido | Cada pedido em aprovação deve estar vinculado a um responsável. O gerente pode organizar a fila e redistribuir responsabilidades a qualquer momento. A redistribuição preserva o histórico de atribuições e não altera permissões nem concede autoridade de aprovação. | M07 |
| M07-07 | Limites de transferência | Funcionários não podem transferir ou delegar a responsabilidade do pedido para outro funcionário. A transferência de responsabilidade operacional é realizada pelo gerente, inclusive por motivos de ausência, férias, afastamento, sobrecarga ou reorganização. | M07 |
| M07-08 | Análise temporária | O responsável pode colocar o pedido em “Em análise” por até 24 horas. Se concluir a análise, o pedido segue conforme a decisão ou encaminhamento aplicável. O estouro do prazo não aprova, reprova, cancela nem transfere automaticamente o pedido. | M07 |
| M07-09 | Estouro do prazo de análise | Se as 24 horas terminarem sem conclusão, o sistema retira o pedido de “Em análise”, sinaliza o atraso e notifica o gerente. O estado exato para o qual o pedido retorna ainda não foi definido. | M07 — pendência de estado |
| M07-10 | Reincidência de análise | Se o responsável encerrar uma análise e voltar a colocar o mesmo pedido em “Em análise”, caracteriza-se reincidência e o gerente deve intervir. Ainda não foi definido se o gerente assume o pedido ou apenas orienta o responsável. | M07 — pendência P-003 |
| M07-11 | Responsável pela correção | Quando o pedido for devolvido para correção, o responsável pela correção é o funcionário que elaborou a proposta. | M07 |
| M07-12 | Prazo de correção | A correção deve ocorrer em até dois dias corridos contados da devolução. O vencimento deve ser registrado e comunicado ao gerente; a pendência permanece aberta e a responsabilidade continua com o funcionário até eventual redistribuição pelo gerente. | M07 |
| M07-13 | Retorno após correção | Após a correção, o pedido retorna automaticamente para “Aguardando análise”. O histórico da devolução e da correção é preservado. Não foi definido um estado intermediário “Em atendimento”. | M07 |
| M07-14 | Cancelamento pela empresa | A empresa pode cancelar um pedido por iniciativa própria, mesmo sem desistência do cliente. A decisão e a execução do cancelamento cabem exclusivamente ao gerente, que assume a condução do atendimento e a comunicação ao cliente. | M07 |
| M07-15 | Registro do cancelamento | O cancelamento registra responsável, data/hora e justificativa, preservando o pedido, a proposta e o histórico. O gerente pode decidir pelo cancelamento antes ou depois da aprovação interna. A IA e funcionários sem autoridade específica não realizam o cancelamento por iniciativa própria. | M07 |
| M07-16 | Aprovação e processamento | Após a aprovação interna, o pedido segue automaticamente para processamento, sem exigir uma segunda autorização humana. A aprovação não significa que a entrega foi realizada nem que o estoque foi reservado. | M07 |
| M07-17 | Notificações de ocorrências | Ocorrências que exigem atenção gerencial devem ser identificáveis no pedido correspondente no Kanban e também gerar mensagem ao gerente, com identificação do pedido, cliente, motivo e ação necessária quando aplicável. | M07 |
| M07-18 | Encerramento de notificação | Quando a ocorrência for efetivamente resolvida, o alerta deixa de permanecer ativo e cessam novas mensagens sobre a mesma ocorrência. Devem permanecer registrados o evento original, sua resolução, responsável e data/hora. Encerrar a notificação não encerra automaticamente o pedido. | M07 |
| M07-19 | Limite de atuação da IA | A IA não negocia condições comerciais em nome da empresa. Interesses comerciais podem ser diversos, conflitantes ou desconhecidos. Negociações, concessões, alternativas e decisões que envolvam alteração de condições cabem ao gerente ou responsável humano com autoridade válida. Apresentar condição previamente autorizada e prevista nas regras não constitui negociação autônoma. | Princípio geral; M06/M07 |
| M07-20 | Registro assistido de negociação | A IA pode organizar informações de negociação fornecidas pelo gerente ou responsável autorizado exclusivamente por mensagem escrita, identificar a operação, estruturar condições e resultados e solicitar complementos ou esclarecimentos. Deve apresentar um resumo estruturado para conferência e confirmação expressa do responsável antes do registro definitivo. Sem confirmação, não há gravação definitiva. A IA não cria condições, negocia nem assume compromissos. | M06/M07 |
| M07-21 | Desistência durante alternativa humana | Durante uma negociação alternativa conduzida por responsável humano, a IA pode registrar a desistência do cliente, vinculá-la ao pedido e à negociação, preservar data/hora e conteúdo, atualizar a situação, encerrar notificações relacionadas e informar o gerente/responsável. A proposta aceita e o pedido permanecem preservados apenas para histórico, sem efetivação comercial ou autorização para processamento. | M07 |
| M07-22 | Reconsideração da desistência | O cliente pode manifestar reconsideração dentro de dois dias úteis contados do registro da desistência. Sem manifestação nesse prazo, a proposta é cancelada automaticamente, preservando-se os registros para consulta e aprendizado. A IA pode registrar a manifestação e notificar o gerente, mas não retoma nem negocia autonomamente. | M07 |
| M07-23 | Retomada após reconsideração | A retomada depende de decisão humana. Se autorizada, exige nova avaliação de preços, disponibilidade e prazo de entrega. Se houver alteração de preço, disponibilidade, itens ou prazo, deve ser criada nova versão, preservando a anterior e exigindo novo aceite do cliente. | M07 |
| M07-24 | Pendência crítica de efetivação | Se o cliente aceitar uma alternativa proposta pelo responsável humano, mas a efetivação ainda não for registrada, o pedido permanece pendente e as notificações continuam. O aceite do cliente, isoladamente, não comprova a efetivação operacional da alternativa. | M07 |
| M07-25 | Efetivação da alternativa autorizada | O gerente ou responsável humano com autoridade para conduzir a alternativa pode efetivá-la após o aceite do cliente, sem uma segunda aprovação formal, desde que registre expressamente a efetivação no histórico. | M07 |
| M07-26 | Bloqueio operacional comercial | Se a pendência crítica não for regularizada em até dois dias úteis contados do aceite do cliente, aplica-se bloqueio operacional comercial. O bloqueio suspende novos atendimentos e operações comerciais, elaboração/envio de propostas, negociações, aprovações e efetivações. Não impede consultas a históricos e pendências, notificações ou ações necessárias à regularização. | M07 |
| M07-27 | Desbloqueio operacional | Somente o gerente pode remover o bloqueio, por ação expressa registrada com responsável, data/hora e motivo. Desbloquear não significa que a pendência foi resolvida; a efetivação deve ser registrada separadamente. | M07 |
| M07-28 | Atendimento automatizado e equipe humana | O atendimento automatizado pode operar 24 horas por dia, sujeito à disponibilidade e às regras do sistema. A equipe humana atua em horário comercial. Notificações podem ser enviadas fora do expediente. | M07 |
| M07-29 | Contagem dos prazos úteis | Os prazos de dois dias úteis para regularização crítica e para reconsideração da desistência foram aprovados, mas as regras detalhadas de calendário, expediente, feriados e contagem ainda precisam ser formalizadas. Não presumir que ambos utilizam necessariamente o mesmo relógio operacional. | M07 — pendência de formalização |
| M07-30 | Comunicação de pendências e alternativas | Quando uma decisão humana for necessária, o cliente deve ser informado de que a solicitação foi encaminhada, sem promessa de prazo não confirmado. A alternativa comercial só pode ser apresentada ou efetivada pelo gerente/responsável humano autorizado e depende da aceitação do cliente quando alterar as condições aplicáveis. | M06/M07 |

### 5.5. Observações sobre o estado desses registros

- Os registros M06 representam conhecimento aprovado durante a descoberta, não uma declaração de que todo o conteúdo já está formalizado no PRD.

- A existência de uma linha na matriz não comprova que o comportamento já foi implementado.

- Antes do encerramento do M06, cada regra deve ser comparada com o texto funcional correspondente.

- Quando houver diferença entre a conversa original e a interpretação consolidada, a diferença deve ser investigada, não resolvida por suposição.

- Regras técnicas de implementação que não tenham sido aprovadas como comportamento do produto devem permanecer identificadas como decisões técnicas ou propostas, não como regras de negócio aprovadas.

- A validade geral da proposta e a validade da condição negociada possuem marcos e efeitos próprios. A condição especial vence três dias corridos após a emissão da nova versão que a contém. A proposta possui prazo geral de 72 horas a partir da apresentação efetiva. O vencimento da condição especial impede seu aceite, ainda que o prazo geral da proposta não tenha terminado.

- O antigo registro M06-50 foi consolidado em M06-28 por duplicidade. Não constitui regra independente e seu identificador não deve ser reutilizado.

## 6. Índice de perguntas respondidas

O índice permite localizar respostas pelo significado da dúvida, e não apenas pelo nome da decisão.

| ID | Pergunta | Resposta | Referência |

|---|---|---|---|

| Q-001 | Quem pode consultar informações comerciais protegidas? | Contatos autorizados, respeitando as permissões individuais configuradas pela empresa. A autorização não concede acesso irrestrito. | DEC-003/DEC-004 |

| Q-002 | A IA pode negociar descontos? | Não. Condições excepcionais dependem de autorização humana. | M06-09/M06-10 |

| Q-003 | O cliente precisa confirmar novamente para gerar o pedido? | Não. Aceite válido gera automaticamente o registro do pedido. | M06-15 |

| Q-004 | Outro contato pode aceitar uma proposta? | Sim, desde que possua a permissão específica necessária. | M06-17/M06-18 |

| Q-005 | Uma proposta expirada pode ser aceita? | Não. Exige nova consulta e nova proposta. | M06-05/M06-06 |

| Q-006 | O aceite do cliente aprova o pedido? | Não. Existe aprovação interna posterior. | M06-16 |

| Q-007 | A proposta apresentada pode ser alterada silenciosamente? | Não. Alterações exigem nova versão e preservação da anterior. | M06-07/M06-14 |

| Q-008 | Um funcionário pode negociar sem consultar o gerente a cada ajuste? | Sim, desde que atue dentro dos limites específicos autorizados. | M06-11/M06-12/M06-45 |

| Q-009 | A delegação é permanente? | Não. É específica para uma negociação e termina conforme as condições estabelecidas. | M06-11/M06-40 |

| Q-010 | Produto indisponível pode ser substituído automaticamente? | Não. O cliente decide. | M06-32 |

| Q-011 | A proposta reserva estoque? | Não. | M06-30 |

| Q-012 | A falha do WhatsApp apaga a proposta? | Não. A proposta e seu histórico permanecem registrados. | M06-24/M06-26 |

| Q-013 | O envio significa que o cliente visualizou? | Não. Envio, entrega, recebimento, visualização e aceite são eventos distintos. | M06-25 |

| Q-014 | O gerente precisa aprovar cada proposta antes do envio? | Não. A elaboração é automática, com encaminhamento de situações excepcionais. | M06-01 |

| Q-015 | A proposta aceita pode gerar dois pedidos? | Não. O primeiro aceite válido prevalece para a mesma versão. | M06-19 |

| Q-016 | A condição especial negociada altera a tabela de preços? | Não. Permanece vinculada à operação específica. | M06-13 |

| Q-017 | A desistência após aceite desfaz automaticamente o pedido? | Não. A desistência após o aceite é registrada e encaminhada para tratamento interno. A proposta aceita e o pedido permanecem preservados; a IA não apaga nem desfaz automaticamente o pedido. | M06-20 |

| Q-018 | A aprovação interna pode alterar as condições aceitas? | Não unilateralmente. | M06-16 |

| Q-019 | Quem registra o aceite? | O contato que efetivamente realizou a ação, com registro de sua autorização. | M06-17/M06-18 |

| Q-020 | Qual é o prazo exato de validade da proposta? | 72 horas corridas e exatas a partir da apresentação efetiva. | M06-05 |

| Q-021 | Uma proposta pode ser apresentada parcialmente? | Sim. Itens resolvidos podem ser apresentados enquanto outros permanecem pendentes e identificados. | M06-03 |

| Q-022 | O que acontece com os itens não selecionados em um aceite parcial? | Não entram no pedido daquela versão e não são considerados recusados definitivamente. | M06-04 |

| Q-023 | O que acontece quando o cliente pede mais prazo? | A IA encaminha a solicitação ao gerente; não prorroga automaticamente. | M06-38 |

| Q-024 | O que acontece se o gerente recusar uma condição especial? | A proposta original continua disponível enquanto estiver válida. | M06-36 |

| Q-025 | A proposta original muda quando o catálogo é atualizado? | Não. Mudanças no catálogo não alteram propostas já apresentadas. | M06-35 |

| Q-026 | O que acontece quando o gerente não responde? | A solicitação permanece pendente e o cliente é informado sem promessa de prazo. | M06-39 |

| Q-027 | O funcionário pode continuar negociando após a revogação da delegação? | Não. Perde imediatamente a autorização para aquela negociação. | M06-41 |

| Q-028 | O funcionário pode solicitar autorização adicional? | Sim. A negociação aguarda a decisão do gerente. | M06-42 |

| Q-029 | A condição autorizada pode ser alterada depois de apresentada ao cliente? | Sim, mas exige nova versão, preservação da anterior e nova decisão do cliente. | M06-43 |

| Q-030 | Uma condição especial autorizada vale automaticamente para outros clientes? | Não. A condição especial autorizada fica vinculada à operação, à proposta e ao cliente correspondentes, não sendo automaticamente aplicável a outros clientes. | M06-13 |

| Q-031 | A falha na geração do PDF invalida a proposta? | Não. A proposta permanece válida e pode ser apresentada por outro canal disponível. | M06-27 |

| Q-032 | O cliente pode consultar propostas anteriores? | A área própria permite consultar propostas, versões anteriores e histórico conforme as permissões aplicáveis. | M06-28/M06-29 |

| Q-033 | O aceite realizado exatamente no instante do vencimento é válido? | Não. O aceite precisa ocorrer antes do vencimento. | M06-05/M06-06 |

| Q-034 | A autorização para consultar preços permite aceitar uma proposta? | Não. O aceite exige permissão específica. | M06-17 |

| Q-035 | Qual é a validade da condição especial negociada e como ela se relaciona com a validade geral da proposta? | A condição especial vale três dias corridos a partir da emissão da nova versão. Esse prazo é independente das 72 horas da proposta, contadas da apresentação efetiva. Se a condição especial vencer primeiro, não poderá mais ser aceita, mesmo que a proposta ainda esteja dentro do prazo geral. | M06-46 |

| Q-036 | A IA pode atualizar a proposta quando o cliente solicitar alteração de quantidade? | Sim. Quando o cliente solicitar uma alteração dentro das condições comerciais tabeladas, a IA consulta a tabela vigente, atualiza os valores e gera uma nova versão da proposta. Alterações que envolvam negociação por volume ou condição especial fora das regras tabeladas devem ser encaminhadas ao gerente. | M06-47 |

| Q-037 | O PDF e a mensagem de WhatsApp representam propostas diferentes? | Não. São formas de apresentação da mesma versão da proposta. | M06-48 |

| Q-038 | Como corrigir um erro em proposta já apresentada? | Encaminhar ao gerente, preservar a versão original, registrar a correção e apresentar nova versão autorizada ao cliente. | M06-49 |

| Q-039 | O que o responsável precisa visualizar antes de aprovar? | Contexto do pedido, itens e quantidades, proposta e versão apresentadas, condições aceitas, registro do aceite e capacidade de atendimento na data combinada. | M07-01 |
| Q-040 | Quando revalidar a disponibilidade? | Imediatamente antes da aprovação interna, considerando a data combinada de entrega. | M07-02 |
| Q-041 | A consulta de disponibilidade reserva estoque? | Não. É evidência temporal e não garante disponibilidade futura. | M06-30/M07-03 |
| Q-042 | Como organizar a fila de aprovação? | Em Kanban centralizado, vinculado a responsáveis e organizado pelo gerente. | M07-05/M07-06 |
| Q-043 | Funcionário pode transferir pedido para outro funcionário? | Não. A redistribuição de responsabilidade cabe ao gerente. | M07-07 |
| Q-044 | Quanto tempo um pedido pode permanecer em análise? | Até 24 horas; o estouro sinaliza atraso e notifica o gerente, sem decisão automática. | M07-08/M07-09 |
| Q-045 | Quem corrige pedido devolvido e em quanto tempo? | O funcionário que elaborou a proposta, em até dois dias corridos contados da devolução. | M07-11/M07-12 |
| Q-046 | Para onde o pedido retorna após a correção? | Automaticamente para “Aguardando análise”, preservando o histórico. | M07-13 |
| Q-047 | Quem pode cancelar pedido por iniciativa da empresa? | Somente o gerente, antes ou depois da aprovação, com justificativa e preservação do histórico. | M07-14/M07-15 |
| Q-048 | O que acontece após a aprovação interna? | O pedido segue automaticamente para processamento, sem segunda autorização; isso não significa entrega nem reserva de estoque. | M07-16 |
| Q-049 | A IA pode negociar condições comerciais? | Não. Negociações e concessões cabem a responsável humano autorizado. | M06-09/M07-19 |
| Q-050 | A IA pode registrar uma negociação informada por gerente? | Sim, pode estruturar informações escritas, apresentar resumo e gravar somente após confirmação expressa do responsável. | M07-20 |
| Q-051 | O aceite de alternativa pelo cliente efetiva o pedido automaticamente? | Não. O pedido permanece pendente até que o responsável humano autorizado registre a efetivação. | M07-24/M07-25 |
| Q-052 | Quem pode remover bloqueio operacional comercial? | Somente o gerente, por ação expressa e registrada; o desbloqueio não resolve por si só a pendência. | M07-26/M07-27 |
| Q-053 | A IA retoma negociação automaticamente após reconsideração da desistência? | Não. A retomada depende de decisão humana e nova avaliação das condições. | M07-22/M07-23 |

Este índice deve ser ampliado sempre que uma pergunta relevante for respondida. Perguntas com o mesmo significado devem ser vinculadas à mesma resposta, em vez de criar registros duplicados.

## 7. Matriz de regras derivadas

As regras abaixo decorrem logicamente das decisões existentes. Não exigem nova aprovação independente quando a consequência for inequívoca, mas devem ser refletidas nos documentos funcionais e permanecer identificadas como derivadas.

| ID | Regra derivada | Origem | Consequência |

|---|---|---|---|

| RD-001 | A permissão específica deve ser verificada no momento da operação protegida. | DEC-004/M06-17 | O aceite não pode ser concluído sem a permissão vigente correspondente à ação solicitada. |

| RD-002 | Pedido deve apontar para a versão exata aceita. | M06-07/M06-15 | Não reconstruir pedido com dados atuais do catálogo. |

| RD-003 | Um aceite válido deve produzir somente um pedido para a mesma versão. | M06-19 | O processamento precisa impedir duplicidade, inclusive em tentativas concorrentes. |

| RD-004 | Aprovação interna não modifica unilateralmente as condições aceitas. | M06-16 | M07 preserva os dados comerciais da operação. |

| RD-005 | Falha do canal não elimina o registro da proposta. | M06-24/M06-26 | Histórico comercial permanece independente do WhatsApp. |

| RD-006 | Condição especial não se torna condição comercial geral. | M06-13 | Uma condição especial autorizada fica vinculada à operação, à proposta e ao cliente correspondentes. Sua aplicação em outra operação exige nova autorização ou regra comercial expressamente estabelecida pela empresa. |

| RD-007 | Delegação encerrada não autoriza nova negociação. | M06-11/M06-40 | Nova negociação exige nova delegação. |

| RD-008 | Tentativas posteriores de aceite não criam novos pedidos. | M06-19 | A plataforma informa que a versão já foi aceita. |

| RD-009 | Proposta e pedido precisam preservar os responsáveis por suas respectivas ações. | M06-22/M06-23 | Rastreabilidade de quem elaborou, entregou, aceitou e aprovou. |

| RD-010 | O histórico da operação precisa sobreviver ao encerramento. | M06-20/M06-21 | Recusa, expiração, substituição e cancelamento não apagam registros. |

| RD-011 | A alteração dos limites de atuação não invalida decisões legitimamente tomadas sob limites anteriores. | M06-45 | Preservar o histórico dos limites anteriores e das decisões tomadas enquanto estavam vigentes. |

| RD-012 | Revalidação de disponibilidade não significa autorização para modificar pedido aceito. | M06-30/M06-32 | Indisponibilidade exige comunicação e decisão do cliente. |

| RD-013 | A validade geral da proposta precisa estar vinculada ao evento de apresentação efetiva ao cliente. | M06-05/M06-23/M06-25 | A criação interna ou uma tentativa de envio sem apresentação efetiva não inicia automaticamente o prazo geral. |

| RD-014 | O pedido precisa preservar o conteúdo comercial aceito, independentemente de alterações posteriores no catálogo. | M06-07/M06-15/M06-35 | A operação deve ser reconstruível a partir da versão aceita. |

| RD-015 | A condição autorizada precisa estar vinculada à autorização que lhe deu origem. | M06-10/M06-11/M06-44 | Não utilizar autorização de outra negociação como justificativa para a condição atual. |

| RD-016 | A revogação da delegação impede novas ações do funcionário que dependam daquela autorização. | M06-40/M06-41 | O gerente assume a negociação ou concede nova delegação, preservando o histórico e a continuidade do atendimento. |

| RD-017 | A proposta precisa manter seu registro comercial mesmo quando a geração de um formato de apresentação falhar. | M06-24/M06-27 | A falha do PDF não apaga a proposta nem altera seu conteúdo. |

| RD-018 | O status comercial da proposta não pode ser deduzido exclusivamente do status da mensagem. | M06-24/M06-25/M06-37 | Envio, entrega ou visualização não representam aceite. |

| RD-019 | Uma alteração posterior à apresentação precisa preservar a possibilidade de reconstruir o que o cliente recebeu anteriormente. | M06-07/M06-14/M06-23/M06-43/M06-49 | Histórico e versões anteriores não podem ser sobrescritos. |

| RD-020 | Permissão de consulta e permissão de aceite são capacidades distintas. | DEC-004/M06-17 | A plataforma deve verificar a permissão correspondente à ação solicitada. |

| RD-021 | PDF e WhatsApp devem apontar para a mesma versão comercial quando forem utilizados para apresentar a mesma proposta. | M06-27/M06-48 | A apresentação em formatos diferentes não cria propostas ou versões comerciais independentes. |

| RD-022 | Alteração de quantidade dentro das condições tabeladas exige atualização da proposta e preservação da versão anterior. | M06-07/M06-47 | A nova quantidade e seus valores devem estar vinculados à nova versão. |

| RD-023 | Correção de erro em proposta apresentada não pode sobrescrever o conteúdo originalmente apresentado. | M06-21/M06-23/M06-49 | A versão original e o registro da correção devem permanecer consultáveis. |

| RD-024 | Alteração de limites de atuação pelo gerente passa a valer imediatamente, sem invalidar decisões legitimamente tomadas sob limites anteriores. | M06-45 | Novas ações do funcionário respeitam os limites vigentes no momento da ação. |

| RD-025 | O vencimento da condição especial negociada não é prorrogado pela validade geral da proposta. | M06-46 | A plataforma deve impedir o aceite da condição especial após seus três dias corridos, mesmo que as 72 horas da proposta ainda não tenham terminado. |

| RD-026 | A aprovação deve avaliar a capacidade de atendimento na data combinada, não apenas o estoque disponível no instante da consulta. | M07-01/M07-02 | Exibir e registrar a data de entrega considerada e a situação por item. |
| RD-027 | Revalidação de disponibilidade é evidência temporal, não reserva de estoque. | M06-30/M07-03 | Não comunicar garantia de disponibilidade futura com base apenas na consulta. |
| RD-028 | Redistribuição gerencial de responsabilidade não altera permissões ou autoridade de aprovação. | M07-06/M07-07 | Separar atribuição operacional de autorização para decidir. |
| RD-029 | Estouro do prazo de análise não produz decisão automática sobre o pedido. | M07-08/M07-09 | Sinalizar atraso e notificar gerente, sem aprovar, reprovar ou cancelar. |
| RD-030 | A correção deve ser atribuída ao elaborador da proposta, salvo redistribuição gerencial registrada. | M07-11/M07-12 | Preservar autoria e histórico de responsabilidade. |
| RD-031 | A aprovação interna autoriza o encaminhamento automático ao processamento, mas não comprova execução ou entrega. | M07-16 | Manter distintos os eventos de aprovação e processamento. |
| RD-032 | A resolução de uma ocorrência encerra seus alertas ativos, não o pedido nem seu histórico. | M07-17/M07-18 | Preservar ocorrência, resolução, responsável e data/hora. |
| RD-033 | IA não pode criar ou negociar condições comerciais; pode apenas registrar conteúdo fornecido por responsável humano após confirmação expressa. | M06-09/M06-10/M06-11/M07-19/M07-20 | Não produzir compromissos comerciais autônomos; respeitar a autoridade e os limites de delegação definidos pela empresa. |
| RD-034 | Aceite de alternativa pelo cliente não equivale à efetivação operacional. | M07-24/M07-25 | Manter pedido pendente até registro expresso da efetivação. |
| RD-035 | Bloqueio operacional comercial não é bloqueio total da plataforma. | M07-26/M07-27 | Preservar consultas e recursos necessários à regularização. |
| RD-036 | Desbloqueio administrativo não comprova regularização da pendência. | M07-27 | Exigir registro separado da efetivação ou resolução. |
| RD-037 | A reconsideração da desistência não retoma automaticamente a negociação. | M07-22/M07-23 | A retomada depende de decisão humana e nova avaliação das condições. |
| RD-038 | Quando houver alteração de preço, disponibilidade, itens ou prazo de entrega após a retomada, deve ser criada nova versão, preservando a anterior e exigindo novo aceite do cliente. | M07-23 | Preservar a versão anterior e registrar o novo aceite do cliente. |
| RD-039 | Kanban é representação operacional da fila, não fonte autônoma de estados de negócio. | M07-05 | Definir estados e transições separadamente da organização visual. |
| RD-040 | A efetivação de alternativa autorizada pelo responsável humano não exige segunda aprovação formal, mas exige registro. | M06-10/M06-11/M07-25 | Preservar autoria, data/hora e conteúdo da efetivação. Não confundir essa autorização específica com autoridade geral para aprovar pedidos. |

### 7.1. Limite das regras derivadas

Uma regra derivada não deve ser utilizada para inventar detalhes que as decisões de origem não definiram.

Quando a consequência depender de escolha de negócio, interpretação ambígua ou exceção não discutida, o assunto deve permanecer como pendência.

## 8. Registro de pendências reais

A tabela abaixo apresenta somente as pendências ainda não resolvidas.

| ID | Assunto | Situação | Etapa prevista | Observação |

|---|---|---|---|---|

| P-001 | Lista e granularidade das permissões individuais | Pendente | Revisão do M01 | A empresa define permissões individuais, mas a lista completa e a granularidade ainda precisam ser especificadas. |

| P-002 | Critérios detalhados de aprovação interna de pedidos | Parcialmente resolvida | M07 | Contexto de análise, consulta da disponibilidade imediatamente antes da aprovação e verificação da data combinada de entrega foram definidos. Permanecem abertas a política para previsão de reposição futura e outras condições específicas de aprovação/reprovação. |

| P-003 | Fila de pedidos aguardando aprovação | Parcialmente resolvida | M07 | Kanban centralizado; pedido vinculado a responsável; gerente organiza e redistribui; funcionários visualizam conforme permissões e não transferem responsabilidade entre si. Permanecem pendentes a definição final das colunas/estados e detalhes de acompanhamento. |

| P-004 | Devolução de pedido para correção antes da decisão | Parcialmente resolvida | M07 | Responsável pela correção é quem elaborou a proposta; prazo de dois dias corridos; retorno automático a Aguardando análise após correção; estouro mantém pendência e notifica gerente. Permanecem pendentes limites/exceções, inclusive eventual limite de ciclos. |

| P-005 | Tratamento detalhado de cancelamento de pedido | Parcialmente resolvida | M07 | Gerente pode cancelar antes ou depois da aprovação, assume condução e comunicação, registra justificativa e preserva histórico. Permanecem pendentes consequências operacionais posteriores e limites de escopo. |

| P-006 | Momento de revalidação da disponibilidade | Parcialmente resolvida | M07 | Revalidar imediatamente antes da aprovação, considerando itens, quantidades e data combinada de entrega. A consulta não reserva estoque nem garante disponibilidade futura. Permanece pendente a política para previsão de reposição antes da entrega. |

| P-007 | Notificações e comunicação dos resultados da aprovação | Parcialmente resolvida | M07 | Ocorrências que exigem atenção gerencial geram aviso visual no Kanban e mensagem ao gerente; a ocorrência resolvida deixa de gerar alertas ativos, mas seu histórico é preservado. Permanecem pendentes detalhes completos de comunicação a cliente e funcionário por evento. |

| P-008 | Detalhamento das operações de supervisão | Pendente | M08 | Especificar ações e consultas indispensáveis ao MVP. |

| P-009 | Necessidade real de funcionalidades adicionais | A avaliar | Após M08 | Não presumir que M09 seja obrigatório. |

| P-010 | Registro da decisão de aprovação ou reprovação | Parcialmente resolvida | M07 | Registrar responsável, data/hora, resultado e justificativa, além da evidência da revalidação de disponibilidade. A aprovação encaminha automaticamente o pedido ao processamento. Permanecem pendentes os detalhes finais de alguns campos e a distinção documental entre autorização e execução. |

### 8.1. Regras para manutenção das pendências

- Não criar uma nova pendência quando o assunto já estiver registrado.

- Se uma pendência for parcialmente resolvida, atualizar sua descrição e situação.

- Se for resolvida, preservar seu identificador e registrar a referência da decisão.

- Se for transferida para outro módulo, atualizar a etapa prevista.

- Se deixar de ser necessária para o MVP, registrar a justificativa sem apagar o histórico.

- Não converter uma pendência em decisão apenas porque existe uma solução tecnicamente possível.

### 8.2. Pendências resolvidas — histórico

As pendências resolvidas permanecem registradas para preservar a rastreabilidade, mas não devem ser apresentadas como questões ainda abertas.

| ID | Assunto | Situação | Referência da resolução |

|---|---|---|---|

| P-011 | Relação entre a validade geral da proposta e a validade da condição negociada | Resolvida na descoberta em 19/11/2026 | M06-46 e RD-025 |

**Resolução de P-011:** os prazos são independentes. A condição especial vence três dias corridos após a emissão da nova versão e não pode ser aceita depois desse prazo, mesmo que as 72 horas da proposta, contadas da apresentação efetiva, ainda estejam em curso.

## 9. Preparação antecipada do M07

### 9.1. Perguntas que não devem ser repetidas

| Pergunta futura | Conhecimento que já responde |

|---|---|

| O que origina um pedido? | Aceite válido de proposta. |

| O pedido precisa de aprovação interna? | Sim. |

| Quem pode aprovar? | O gerente é responsável pela aprovação por padrão, salvo quando outro funcionário possuir autoridade específica de aprovação atribuída pela empresa. A granularidade das permissões, os critérios e o fluxo detalhado de aprovação deverão ser especificados no M07. A delegação comercial do M06 não implica autoridade para aprovar pedidos. |

| O aceite do cliente substitui aprovação interna? | Não. |

| Quem deve ser registrado como responsável pelo aceite? | O contato que realizou a ação. |

| O pedido pode alterar condições aceitas? | Não unilateralmente. |

| O que acontece quando a empresa não aprova? | Registrar motivo, comunicar o cliente e preservar o histórico. |

| Como impedir duplicidade? | Um pedido por versão aceita. |

| A proposta reservou estoque? | Não. |

| A desistência apaga automaticamente o pedido? | Não. |

### 9.2. Pendências do M07 que permanecem abertas após a descoberta\n\n\n\| ID \| Lacuna remanescente \| O que ainda falta definir \|
\|---\|---\|---\|
\| P-002 \| Critérios completos de aprovação/reprovação \| Política para previsão de reposição futura e demais condições específicas ainda não decididas. \|
\| P-003 \| Estados e intervenções gerenciais \| Estado após estouro das 24h; se gerente assume ou orienta na reincidência; definição final das colunas/estados. \|
\| P-004 \| Limites da correção \| Limite de ciclos, exceções e demais limites ainda não confirmados. \|
\| P-005 \| Consequências do cancelamento \| Consequências operacionais posteriores e limites de escopo, sem presumir logística ou pós-venda. \|
\| P-006 \| Previsão de reposição \| Se e em quais condições uma previsão de reposição pode fundamentar aprovação para entrega futura. \|
\| P-007 \| Comunicação por evento \| Matriz completa de destinatários, conteúdo e momento de comunicação a cliente, gerente e funcionário. \|
\| P-010 \| Campos finais do registro \| Campos complementares e distinção documental entre aprovação, autorização para processamento e processamento efetivo. \|
\| M07-PRAZOS \| Contagem dos prazos úteis \| Calendário, expediente, feriados e marcos de contagem dos prazos de dois dias úteis. \|\n\n\n**### 9.3. Conhecimentos que devem orientar a descoberta**

O M07 deve partir das seguintes premissas já estabelecidas:

- O pedido nasce do aceite válido de uma proposta.

- O pedido precisa preservar a versão e as condições aceitas.

- A aprovação interna é uma etapa distinta do aceite do cliente.

- A aprovação ou reprovação precisa ser registrada.

- Reprovação exige justificativa registrada e comunicação ao cliente.

- A desistência não apaga automaticamente a proposta nem o pedido.

- A disponibilidade não foi reservada pela proposta.

- O M07 não deve redefinir as regras comerciais já estabelecidas no M06.

- A delegação comercial para negociação no M06 não deve ser confundida com autoridade para aprovar pedidos.
- A IA não negocia condições comerciais; pode apoiar o registro assistido de informações escritas fornecidas por responsável humano, mediante confirmação expressa.
- O Kanban organiza visualmente a fila, mas não define sozinho os estados de negócio.
- A responsabilidade pelo pedido pode ser redistribuída pelo gerente, sem alteração automática de permissões ou autoridade.
- A revalidação de disponibilidade ocorre imediatamente antes da aprovação e considera a data combinada de entrega, sem reservar estoque.
- Aprovação interna encaminha o pedido ao processamento, mas não comprova processamento ou entrega.
- Bloqueio operacional comercial preserva consultas e recursos necessários à regularização; somente o gerente pode desbloqueá-lo.
O M07 deve tratar o fluxo de aprovação e o resultado do pedido sem assumir automaticamente a inclusão de logística ou de um pós-venda completo.

### 9.4. Lacunas e cuidados de formalização identificados no M07
- O estado do pedido após o estouro das 24 horas de análise não foi definido.
- Na reincidência de análise, ainda falta decidir se o gerente assume o pedido ou orienta o responsável.
- A política para previsão de reposição antes da data de entrega permanece aberta.
- O limite de ciclos de devolução para correção não foi definido.
- Os prazos de dois dias úteis precisam de regra formal de calendário e contagem.
- As comunicações completas a cliente e funcionário ainda precisam ser especificadas por evento.
- O procedimento de desistência, reconsideração e bloqueio operacional precisa ser formalizado sem confundir bloqueio comercial com bloqueio total.
- O PRD deve preservar a distinção entre aprovação, encaminhamento ao processamento, efetivação e entrega.
## 10. Preparação dos módulos seguintes

### 10.1. M08 — Painel administrativo e supervisão

Conhecimento já estabelecido:

- Supervisão operacional básica integra o MVP, conforme DEC-001.

- O gerente possui visão geral das propostas da empresa, conforme as regras específicas do M06.

- Não está estabelecida, por essa regra, uma visão irrestrita do gerente sobre todas as operações da empresa.

- Funcionários acessam conforme permissões individuais.

- A consulta e a supervisão precisam respeitar as permissões configuradas.

- Histórico deve permitir reconstrução das operações.

- Encaminhamentos e pendências precisam ser rastreáveis.

- A área de propostas do M06 já possui requisitos próprios de consulta e acompanhamento.

O escopo detalhado do painel, suas consultas, filtros, ações e limites ainda deve ser especificado no M08.

**Lacuna:** identificar as operações administrativas indispensáveis para a supervisão básica do MVP, sem transformar o painel em CRM, ERP ou sistema de gestão abrangente e sem presumir permissões não estabelecidas.

### 10.2. M09 — Avaliação de necessidade

O M09 não deve ser presumido como obrigatório.

Após M08, consultar a matriz de escopo do MVP para identificar se existe uma necessidade funcional indispensável ainda não atendida.

A decisão de criar M09 dependerá de uma lacuna real do produto, não da necessidade de preencher uma sequência numérica.

## 11. Atualização contínua da matriz

Sempre que uma nova pergunta for respondida:

1. Identificar o significado da pergunta.

2. Verificar se já existe registro semanticamente semelhante.

3. Consultar decisões formais e documentos funcionais relacionados.

4. Registrar a resposta e sua origem.

5. Classificar como aprovada na descoberta, formalizada, derivada ou pendente.

6. Atualizar o índice de perguntas.

7. Identificar módulos afetados.

8. Registrar consequências, exceções e regras derivadas.

9. Atualizar o PRD e a decisão formal quando aplicável.

10. Verificar se alguma pendência anterior foi resolvida.

11. Preservar o histórico de decisões substituídas.

12. Identificar perguntas futuras que já foram respondidas pela nova decisão.

Não esperar o encerramento de um módulo para atualizar o conhecimento acumulado.

### 11.1. Controle de alterações

Quando uma decisão for alterada:

- Não apagar o registro anterior.

- Identificar a decisão que a substituiu.

- Registrar a justificativa da alteração.

- Atualizar a regra vigente e os módulos afetados.

- Verificar se perguntas anteriores precisam apontar para a nova regra.

- Revisar regras derivadas que dependiam da decisão substituída.

## 12. Procedimento de consulta nas próximas descobertas

Antes de iniciar M07, M08, M09 ou qualquer nova fase, realizar uma consulta estruturada.

**Consulta A — Perguntas anteriores**

- Existe pergunta semanticamente semelhante?

- Qual foi a resposta?

- A resposta foi aprovada?

- A pergunta já foi respondida em outro módulo?

**Consulta B — Decisões e documentos**

- Existe DEC relacionada?

- Qual módulo definiu a regra?

- O PRD já contempla essa regra?

- A regra foi formalizada e auditada?

**Consulta C — Consequências**

- Há regra derivada?

- Quais decisões lhe dão origem?

- Existem exceções?

- Há impacto em outros módulos?

**Consulta D — Necessidade**

- É indispensável para o MVP?

- Precisa ser decidido agora?

- Pode aguardar outro módulo?

- A questão já está coberta por uma decisão anterior?

**Resultado obrigatório da consulta:**

- Já respondida: aplicar conhecimento existente.

- Regra derivada: aplicar e registrar origem.

- Lacuna real: formular nova pergunta.

- Contradição: interromper a definição e investigar.

- Decisão futura: registrar no módulo responsável.

- Fora do MVP: registrar como possibilidade futura, sem incorporar automaticamente.

## 13. Princípio de governança

**O conhecimento acumulado deve reduzir o esforço das próximas decisões e aumentar a qualidade de cada etapa do produto.**

A descoberta não deve retornar repetidamente aos mesmos assuntos. Cada decisão aprovada precisa gerar valor para as próximas etapas.

A matriz é um instrumento vivo de rastreabilidade, consulta e prevenção de inconsistências.

Ela não substitui o PRD, os registros formais de decisão ou a auditoria documental. Sua função é conectar esses registros e permitir que sejam consultados antes de novas perguntas e decisões.