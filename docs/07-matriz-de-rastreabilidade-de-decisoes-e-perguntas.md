# Matriz de Rastreabilidade de Decisões e Perguntas

**Projeto:** Plataforma de Atendimento Inteligente

**Versão:** 0.7

**Data:** 19/11/2026

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

### 5.4. Observações sobre o estado desses registros

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

### 7.1. Limite das regras derivadas

Uma regra derivada não deve ser utilizada para inventar detalhes que as decisões de origem não definiram.

Quando a consequência depender de escolha de negócio, interpretação ambígua ou exceção não discutida, o assunto deve permanecer como pendência.

## 8. Registro de pendências reais

A tabela abaixo apresenta somente as pendências ainda não resolvidas.

| ID | Assunto | Situação | Etapa prevista | Observação |
|---|---|---|---|---|
| P-001 | Lista e granularidade das permissões individuais | Pendente | Revisão do M01 | A empresa define permissões individuais, mas a lista completa e a granularidade ainda precisam ser especificadas. |
| P-002 | Critérios detalhados de aprovação interna de pedidos | Pendente | M07 | Não confundir autoridade para aprovar com critérios utilizados na aprovação. |
| P-003 | Fila de pedidos aguardando aprovação | Pendente | M07 | Definir visualização, organização e acompanhamento. |
| P-004 | Devolução de pedido para correção antes da decisão | Pendente | M07 | Definir limites e preservação do histórico. |
| P-005 | Tratamento detalhado de cancelamento de pedido | Pendente | M07 | Distinguir situações anteriores e posteriores à aprovação. |
| P-006 | Momento de revalidação da disponibilidade | Pendente | M07 | Preservar condições comerciais aceitas e a decisão do cliente. |
| P-007 | Notificações e comunicação dos resultados da aprovação | Pendente | M07 | Detalhar destinatários, eventos e conteúdo das comunicações. |
| P-008 | Detalhamento das operações de supervisão | Pendente | M08 | Especificar ações e consultas indispensáveis ao MVP. |
| P-009 | Necessidade real de funcionalidades adicionais | A avaliar | Após M08 | Não presumir que M09 seja obrigatório. |
| P-010 | Registro da decisão de aprovação ou reprovação | Pendente | M07 | Registrar responsável, data/hora, resultado e justificativa. |

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

### 9.2. Perguntas que realmente precisam ser investigadas

| ID | Questão | Observação |
|---|---|---|
| P-002 | Quais critérios orientam aprovação ou reprovação? | Não confundir autoridade para aprovar com critérios da aprovação. |
| P-003 | Como funciona a fila de aprovação? | Identificar responsável e situação. |
| P-004 | O pedido pode voltar para correção? | Definir limites e preservação do histórico. |
| P-005 | Como tratar cancelamento em cada situação do pedido? | Distinguir antes e depois da aprovação. |
| P-006 | Em qual momento revalidar disponibilidade? | Preservar condições comerciais aceitas. |
| P-007 | Quais notificações são necessárias? | Cliente, gerente e funcionário autorizado. |
| P-010 | Como registrar a decisão de aprovação ou reprovação? | Responsável, data, resultado e justificativa. |

### 9.3. Conhecimentos que devem orientar a descoberta

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

O M07 deve tratar o fluxo de aprovação e o resultado do pedido sem assumir automaticamente a inclusão de logística ou de um pós-venda completo.

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