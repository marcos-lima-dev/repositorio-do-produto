# Documento 03 — PRD
## Requisitos do Produto

**Produto:** Plataforma de Atendimento Inteligente

**Versão:** 0.2 — Construção incremental

**Data original:** 16 de novembro de 2026

**Revisão documental:** 19 de novembro de 2026

**Status:** Em elaboração — revisão de coerência documental

---

## 1. Objetivo do documento

Definir os requisitos funcionais e comportamentais da Plataforma de Atendimento Inteligente.

O PRD será desenvolvido por módulos, registrando funcionalidades, regras de negócio, fluxos operacionais e critérios de aceitação.

As decisões ainda não tomadas deverão permanecer identificadas como pendentes.

# MÓDULO 01 — IDENTIFICAÇÃO E AUTORIZAÇÃO DE CONTATOS

## 2. Objetivo

Identificar pessoas que iniciam um atendimento pelo WhatsApp, estabelecer sua relação com uma empresa cliente e controlar o acesso às operações comerciais.

O sistema não deve conceder acesso comercial apenas porque alguém informa representar determinada empresa.

## 3. Identificação inicial

Quando uma pessoa iniciar uma conversa:

1. O sistema identifica o número de WhatsApp de origem.
2. Verifica se o número já está associado a um contato cadastrado.
3. Caso seja um novo contato, inicia o processo de identificação.
4. Pergunta qual empresa a pessoa representa.
5. Verifica se a empresa já possui cadastro.
6. Registra uma solicitação de vinculação, sujeita à aprovação do gerente.

A identificação do número de telefone não equivale à autorização comercial.

## 4. Aprovação de novos contatos

**Regra de negócio:** somente o gerente da empresa poderá aprovar novos contatos.

Fluxo:

1. O contato informa a empresa que representa.
2. O sistema registra a solicitação.
3. O gerente recebe uma notificação.
4. O gerente aprova ou rejeita a solicitação.
5. O sistema registra a decisão, o responsável e a data.
6. Em caso de aprovação, o contato passa a integrar os contatos autorizados da empresa.

Funcionários autorizados a aprovar pedidos comerciais não recebem automaticamente autorização para aprovar novos contatos.

## 5. Acesso enquanto aguarda aprovação

Enquanto a solicitação estiver pendente:

- O contato não poderá acessar informações comerciais restritas.
- Não poderá consultar histórico de pedidos da empresa.
- Não poderá realizar operações comerciais.
- Deverá receber informação sobre o andamento da solicitação.
- O sistema deverá manter a solicitação registrada e acompanhar sua aprovação.

Se o gerente não estiver disponível, a solicitação permanecerá pendente. O sistema deverá enviar novos avisos ao gerente, sem liberar o acesso automaticamente.

## 6. Permissões dos contatos autorizados

A empresa será responsável por definir as permissões individuais de cada contato autorizado.

Contatos vinculados à mesma empresa poderão possuir permissões diferentes, conforme as necessidades e os critérios estabelecidos pela própria empresa.

Regras:

- A autorização de um contato para representar a empresa não concederá acesso irrestrito às informações e operações comerciais.
- O sistema deverá verificar as permissões do contato antes de permitir o acesso a informações ou operações protegidas.
- As permissões deverão ser consideradas individualmente, respeitando a configuração estabelecida pela empresa.
- A ausência de uma permissão deverá impedir a realização da operação correspondente.
- As permissões comerciais não substituirão as regras de aprovação interna de propostas e pedidos.
- A autorização para realizar uma operação comercial não significará autorização para aprovar pedidos em nome da empresa.

A lista de permissões disponíveis, sua granularidade e suas regras de configuração serão detalhadas posteriormente.

As regras de aprovação interna continuarão independentes das permissões comerciais individuais, respeitando os responsáveis previamente autorizados pela empresa.

## 7. Revogação de autorização

A empresa poderá revogar a autorização de um contato a qualquer momento.

A revogação deverá:

- Impedir novas ações protegidas a partir de sua efetivação.
- Impedir novas solicitações comerciais pelo contato.
- Bloquear o acesso a informações comerciais restritas.
- Preservar conversas, propostas e pedidos anteriores.
- Registrar quem realizou a revogação e quando.

As permissões deverão ser verificadas no momento de cada ação protegida. Assim, a revogação efetivada antes de uma ação impedirá sua realização, mesmo que o contato já tenha consultado anteriormente as informações relacionadas à operação.

A revogação não deverá invalidar retroativamente ações legitimamente realizadas enquanto a autorização estava vigente.

## 8. Preservação do histórico

A revogação de acesso não deverá apagar a identidade histórica do contato.

O sistema deverá preservar:

- Identificação da pessoa.
- Número de telefone associado aos registros.
- Conversas realizadas.
- Propostas apresentadas.
- Pedidos realizados.
- Decisões e intervenções.
- Data e responsável pela revogação.

Os registros anteriores continuarão vinculados à pessoa que realizou cada operação.

## 9. Estados do contato

| Estado | Significado |
|---|---|
| Não cadastrado | Número ainda não identificado como contato |
| Aguardando autorização | Solicitação de vínculo enviada ao gerente |
| Autorizado | Contato aprovado e habilitado |
| Rejeitado | Solicitação de vínculo recusada |
| Revogado | Autorização anteriormente concedida foi retirada |

## 10. Critérios de aceitação

O módulo será considerado funcional quando:

1. Um novo número puder iniciar o processo de identificação.
2. O sistema solicitar a identificação da empresa representada.
3. Uma solicitação de vínculo for criada e encaminhada ao gerente.
4. Nenhum acesso comercial for concedido antes da aprovação.
5. Somente o gerente puder aprovar novos contatos.
6. O contato aprovado puder realizar somente as operações para as quais recebeu autorização individual.
7. A ausência de resposta do gerente não liberar acesso automaticamente.
8. A revogação impedir novas ações protegidas a partir de sua efetivação.
9. A revogação preservar os registros anteriores e as ações legitimamente realizadas.
10. O sistema conseguir identificar quem autorizou ou revogou um contato e quando.

---

# MÓDULO 02 — CADASTRO E GESTÃO DAS EMPRESAS CLIENTES

## 11. Objetivo

Organizar o cadastro das empresas clientes como entidade principal do relacionamento comercial.

Cada empresa deverá possuir um cadastro próprio, ao qual estarão vinculados seus contatos autorizados, propostas, pedidos, conversas e histórico comercial.

## 12. Empresa como cadastro principal

A empresa será a entidade central do relacionamento comercial.

Regras:

- Uma empresa terá um cadastro principal.
- Poderá possuir vários contatos autorizados.
- Os pedidos serão vinculados à empresa.
- Cada pedido identificará a pessoa que o realizou.
- Os contatos autorizados compartilharão o histórico comercial da empresa.
- A revogação de um contato não afetará os pedidos e registros anteriores.

O sistema deverá evitar a criação de cadastros duplicados para uma mesma empresa.

## 13. Informações cadastrais

O cadastro inicial deverá contemplar:

| Campo | Descrição |
|---|---|
| Razão social | Nome empresarial |
| Nome fantasia | Identificação comercial |
| CNPJ | Documento de identificação da empresa |
| Endereço | Endereço cadastral |
| Telefone | Telefone de contato |
| E-mail | Endereço eletrônico de contato |

A obrigatoriedade individual dos campos e as regras de validação serão detalhadas posteriormente.

## 14. Identificação de empresas já cadastradas

Quando uma pessoa informar uma empresa que já possui cadastro:

1. O sistema deverá localizar o cadastro existente, utilizando o CNPJ informado.
2. Não deverá criar uma segunda empresa.
3. Deverá registrar a solicitação de vinculação do novo contato.
4. A solicitação deverá ser encaminhada ao gerente.
5. Somente após aprovação o número será associado à empresa e o acesso comercial será liberado.

**Regra fundamental:** conhecer ou informar o CNPJ de uma empresa não significa ter autorização para representá-la.

## 15. Gestão dos dados cadastrais

**Regra de negócio:** somente o gerente poderá alterar os dados cadastrais da empresa.

Isso inclui:

- Razão social.
- Nome fantasia.
- CNPJ.
- Endereço.
- Telefone.
- E-mail.

O sistema deverá registrar as alterações, identificando:

- Quem realizou a alteração.
- Quando ocorreu.
- Quais informações foram modificadas.

Os contatos comerciais autorizados não poderão alterar diretamente o cadastro empresarial.

## 16. Desativação de empresas

Quando uma empresa deixar de ser cliente, seu cadastro não deverá ser excluído definitivamente.

Somente o gerente poderá desativar a empresa.

A desativação deverá:

1. Impedir novas operações comerciais.
2. Bloquear o acesso operacional dos contatos vinculados.
3. Preservar pedidos, propostas e conversas anteriores.
4. Preservar os registros de todos os contatos.
5. Registrar quem realizou a desativação e quando.

A desativação não deverá apagar o histórico comercial.

## 17. Reativação de empresas

Quando uma empresa voltar a fazer negócios:

1. O gerente poderá reativar o cadastro existente.
2. O histórico comercial será preservado.
3. Não será criado um novo cadastro para a mesma empresa.
4. Os contatos anteriores não recuperarão automaticamente o acesso.
5. O gerente deverá autorizar novamente os contatos que poderão operar.

A reativação da empresa e a autorização dos contatos serão processos independentes.

## 18. Estados da empresa

| Estado | Significado |
|---|---|
| Ativa | Empresa habilitada para operações comerciais |
| Desativada | Empresa temporariamente impedida de realizar novas operações |

O estado da empresa deverá ser independente do estado de autorização de cada contato.

## 19. Critérios de aceitação

O módulo será considerado funcional quando:

1. Uma empresa puder ser cadastrada com as informações definidas.
2. Uma empresa puder possuir vários contatos vinculados.
3. Os pedidos forem associados à empresa e identificarem seu autor.
4. Os contatos autorizados compartilharem o histórico comercial.
5. O CNPJ permitir localizar o cadastro existente.
6. A informação do CNPJ não conceder acesso automaticamente.
7. Somente o gerente puder alterar os dados cadastrais.
8. As alterações cadastrais forem registradas para auditoria.
9. Somente o gerente puder desativar ou reativar a empresa.
10. A desativação bloquear as operações comerciais sem apagar registros.
11. A reativação preservar o cadastro e exigir nova autorização dos contatos.

---

## 20. Módulo 03 — Catálogo e informações comerciais

### 20.1. Objetivo

Manter um catálogo confiável de produtos e informações comerciais, controlado pela empresa e utilizado pelo sistema durante os atendimentos e negociações.

A IA não poderá inventar produtos, características ou informações comerciais.

### 20.2. Formação do catálogo inicial

Durante a implantação, a empresa fornecerá sua planilha de produtos.

O processo inicial deverá:

1. Receber a planilha fornecida pela empresa.
2. Estruturar e adequar os dados ao formato do catálogo.
3. Permitir a conferência das informações.
4. Disponibilizar o catálogo para utilização após sua validação.

A planilha será utilizada na formação inicial da base. A manutenção posterior será realizada diretamente no sistema.

### 20.3. Cadastro e manutenção dos produtos

O cadastro permitirá:

- Nome comercial.
- Descrição.
- Marca.
- Unidade de comercialização.
- Apresentação e embalagem.
- Situação do produto: ativo ou desativado.

Os preços e as condições comerciais não serão administrados diretamente pelo cadastro do produto. Essas informações serão mantidas pelo Módulo 04, responsável pelas tabelas de preços e condições comerciais.

Novos produtos poderão ser cadastrados individualmente. Produtos existentes poderão ser atualizados individualmente.

Somente o gerente ou pessoas expressamente autorizadas por ele poderão administrar o catálogo.

As pessoas autorizadas poderão publicar diretamente as alterações, sem necessidade de aprovação individual do gerente para cada mudança.

A IA poderá sugerir correções e identificar informações incompletas, mas não poderá alterar ou publicar informações oficiais por conta própria.

### 20.4. Histórico e desativação de produtos

As alterações deverão preservar o histórico anterior, permitindo identificar:

- Informações anteriores e atuais.
- Data e horário da alteração.
- Responsável pela alteração.
- Campos modificados.

Produtos que deixarem de ser comercializados deverão ser desativados, e não excluídos.

Um produto desativado não poderá ser utilizado em novas propostas ou pedidos. Seu cadastro e seu histórico deverão permanecer preservados para consulta das operações anteriores.

### 20.5. Disponibilidade em estoque

A existência de um produto ativo no catálogo não significa que ele esteja disponível em estoque.

Quando não houver informação confiável, a IA deverá informar que a disponibilidade precisa ser confirmada e encaminhar a consulta ao responsável.

Cada confirmação de estoque deverá registrar:

- Produto consultado.
- Quantidade informada como disponível.
- Data e horário da confirmação.
- Funcionário responsável.

A empresa poderá definir a validade das confirmações de estoque.

Após o vencimento dessa validade, a informação anterior não poderá ser apresentada como disponibilidade atual sem nova confirmação.

Quando um produto estiver indisponível, o cliente deverá ser informado. No MVP, não haverá lista de espera nem aviso automático de reposição.

### 20.6. Quantidades e ofertas

Quando a quantidade disponível for inferior à solicitada, o sistema deverá informar a quantidade efetivamente disponível.

A quantidade originalmente solicitada e a quantidade oferecida deverão permanecer identificáveis no histórico.

O cliente deverá aceitar expressamente a quantidade oferecida antes de a operação prosseguir.

O sistema não poderá presumir a aceitação nem modificar silenciosamente a solicitação original.

### 20.7. Produtos substitutos

A empresa poderá cadastrar produtos autorizados como substitutos de outros produtos.

Poderá haver mais de uma alternativa para o mesmo produto, com uma ordem de preferência definida pela empresa.

A IA poderá apresentar essas alternativas, respeitando a ordem estabelecida e informando eventuais diferenças comerciais.

A substituição dependerá sempre da aceitação do cliente.

Se não houver alternativa disponível, o sistema deverá informar a situação, registrar a ocorrência e encaminhá-la ao responsável. Não poderá cancelar ou modificar automaticamente a operação.

### 20.8. Informações incompletas

A IA deverá utilizar somente informações cadastradas e validadas.

Quando faltarem dados como marca, embalagem, unidade ou características:

- Não deverá inventar nem presumir informações.
- Poderá apresentar os dados conhecidos.
- Se a informação ausente for necessária à negociação, deverá encaminhar a consulta ao responsável.

### 20.9. Critérios de aceitação

O módulo deverá permitir:

1. Formar o catálogo inicial a partir da planilha fornecida pela empresa.
2. Cadastrar e atualizar produtos individualmente.
3. Restringir a administração do catálogo às pessoas autorizadas.
4. Preservar o histórico das alterações.
5. Desativar produtos sem apagar seu histórico.
6. Diferenciar produto cadastrado de produto disponível.
7. Registrar e controlar a validade das confirmações de estoque.
8. Informar quantidades disponíveis sem alterar automaticamente a solicitação.
9. Apresentar substitutos autorizados e respeitar sua ordem de preferência.
10. Impedir que a IA invente informações comerciais.

---

## 21. Módulo 04 — Preços, versões de tabelas e condições comerciais

### 21.1. Objetivo

Controlar preços e condições comerciais de maneira rastreável, respeitando as estratégias de venda de cada empresa e preservando as negociações realizadas.

### 21.2. Múltiplas tabelas de preços

Uma empresa poderá trabalhar com diferentes tabelas comerciais, conforme seus interesses.

Exemplos:

- Tabela padrão.
- Tabela para clientes especiais.
- Tabelas para grupos de clientes.
- Tabelas promocionais.
- Outras condições comerciais definidas pela empresa.

A empresa será responsável por definir quais clientes ou grupos poderão utilizar cada tabela.

A IA não poderá escolher livremente entre tabelas para oferecer o preço mais conveniente.

### 21.3. Associação e vigência

A associação entre cliente e tabela poderá possuir data e horário de início de vigência.

As tabelas também poderão ter data e horário de encerramento.

O sistema deverá respeitar os períodos definidos para determinar quais condições comerciais podem ser utilizadas em novas operações.

Quando uma tabela for desativada, o sistema deverá:

- Identificar os clientes associados.
- Alertar o gerente.
- Impedir novas cotações com aquela tabela.
- Não transferir automaticamente os clientes para outra tabela.
- Preservar propostas e operações anteriores.

### 21.4. Ausência de tabela válida e conflitos

Se um cliente não possuir tabela vigente e autorizada, a IA não poderá reutilizar preços expirados nem escolher outra tabela por conta própria.

A situação deverá ser encaminhada ao responsável.

A existência de tabelas diferentes com preços distintos não caracteriza, por si só, um conflito. Diferenças destinadas a clientes, grupos ou finalidades comerciais diferentes são legítimas, desde que respeitem as associações e regras definidas pela empresa.

Haverá conflito quando mais de uma tabela for simultaneamente aplicável ao mesmo cliente e não existir uma regra válida que determine qual deverá prevalecer.

Nesse caso:

1. O sistema deverá alertar o gerente.
2. A negociação que dependa da definição da tabela deverá ser bloqueada.
3. O atendimento poderá continuar para informar o cliente sobre a verificação.
4. A negociação aguardará a decisão do gerente.
5. Após a resolução, o sistema deverá permitir sua retomada, preservando o histórico e o contexto anterior.

### 21.5. Alterações e histórico de preços

Os preços poderão ser alterados por pessoas autorizadas pelo gerente.

Cada alteração deverá preservar:

- Valor anterior.
- Novo valor.
- Data e horário da alteração.
- Início da nova vigência.
- Responsável pela alteração.

As versões anteriores deverão permanecer disponíveis para reconstruir as condições comerciais existentes em cada momento.

### 21.6. Correção de preços cadastrados incorretamente

Quando um preço incorreto for identificado, deverá ser corrigido sem apagar seu registro original.

O tratamento dependerá da existência de negociações afetadas.

**Sem negociação afetada:**
- O preço poderá ser corrigido.
- O histórico da correção será preservado.

**Com negociação em andamento:**
- O sistema deverá identificar os clientes e as operações afetadas.
- Alertar o gerente.
- Apresentar a relação das negociações envolvidas.
- Permitir que o gerente assuma a condução e determine a comunicação aos clientes sobre o erro e o preço correto.

**Com operação já realizada:**
- O preço efetivamente negociado deverá ser preservado.
- A empresa deverá honrar a operação.
- A correção cadastral não poderá apagar ou alterar compromissos comerciais já assumidos.

Relatórios de impacto financeiro e análises gerenciais mais avançadas poderão ser oferecidos em versões futuras.

### 21.7. Proteção das propostas e operações

Cada operação deverá preservar as condições comerciais correspondentes ao momento da negociação.

Quando o cliente aceitar uma proposta, ficam protegidos os produtos, quantidades, preços e condições aceitos.

A aprovação interna posterior não poderá alterar unilateralmente essas condições.

O aceite e a aprovação interna são eventos distintos.

Quando uma proposta perder a validade, sua versão original e as condições que foram apresentadas deverão permanecer preservadas no histórico.

Uma eventual atualização de preços ou condições não poderá ser aplicada silenciosamente à proposta anterior, mesmo quando representar uma condição mais favorável ao cliente. Caso seja necessário apresentar novas condições, deverá ser elaborada uma nova versão ou proposta, com identificação das alterações e oportunidade de manifestação do cliente.

O vencimento ou a desativação da tabela não invalidará propostas já emitidas que ainda estejam dentro do prazo de validade.

### 21.8. Critérios de aceitação

O módulo deverá permitir:

1. Criar e administrar diferentes tabelas comerciais.
2. Associar clientes ou grupos às tabelas.
3. Definir períodos de vigência.
4. Preservar versões anteriores dos preços.
5. Restringir alterações às pessoas autorizadas.
6. Identificar ausência de tabela válida.
7. Detectar conflitos entre tabelas simultaneamente aplicáveis ao mesmo cliente e alertar o gerente.
8. Não tratar diferenças legítimas entre tabelas destinadas a públicos ou finalidades diferentes como conflitos.
9. Bloquear a negociação que dependa da definição da tabela quando houver conflito entre tabelas simultaneamente aplicáveis ao mesmo cliente, sem regra válida de prevalência.
10. Retomar a negociação após a resolução, sem perder seu contexto.
11. Preservar propostas aceitas e operações realizadas.
12. Impedir alterações retroativas silenciosas.
13. Identificar negociações afetadas por preços cadastrados incorretamente.

---

## 22. Próximos módulos do PRD

A ordem de detalhamento dos módulos é:

1. Identificação e autorização de contatos — consolidado.
2. Cadastro e gestão das empresas clientes — consolidado.
3. Catálogo e informações comerciais — consolidado.
4. Preços, versões de tabelas e condições comerciais — consolidado.
5. Atendimento inteligente e interpretação de solicitações — especificado e revisado.
6. Propostas, pedidos e aprovações — descoberta funcional concluída; consolidação e formalização no PRD pendentes.
7. Ocorrências, pendências e encaminhamentos — pendente de especificação.
8. Painel administrativo e supervisão — pendente de especificação.
9. Histórico, relatórios e aprendizado — pendente de especificação.

O Módulo 06 já possui descoberta funcional realizada e decisões registradas na matriz de rastreabilidade. Sua formalização em seção própria do PRD deverá ocorrer em etapa posterior, sem confundir descoberta funcional concluída com especificação documental consolidada ou implementação.

Os módulos seguintes serão detalhados progressivamente, considerando as dependências funcionais e a prioridade do MVP.

A especificação funcional não implica que todos os recursos descritos devam ser implementados na primeira versão. Recursos avançados poderão ser classificados como evoluções futuras.

---

# MÓDULO 05 — ATENDIMENTO INTELIGENTE E INTERPRETAÇÃO DE SOLICITAÇÕES

## 23. Objetivo e responsabilidade

### 23.1. Objetivo

O Módulo 05 será responsável por conduzir o atendimento comercial conversacional, desde o primeiro contato do cliente até a compreensão, organização e confirmação expressa de sua solicitação.

O objetivo é transformar uma conversa em uma solicitação comercial estruturada, com informações suficientes para que o Módulo 06 possa elaborar uma proposta.

### 23.2. Responsabilidades

O módulo deverá:

1. Compreender a intenção e a necessidade apresentada pelo cliente.
2. Conduzir a conversa de maneira contextual, solicitando somente as informações necessárias.
3. Identificar os produtos solicitados e organizar individualmente seus respectivos dados.
4. Consultar informações comerciais disponibilizadas pelos módulos responsáveis.
5. Esclarecer dúvidas utilizando informações confiáveis.
6. Identificar ambiguidades, informações ausentes e situações que exijam intervenção humana.
7. Recuperar o contexto de atendimentos e pedidos anteriores, respeitando as regras de identificação e autorização.
8. Apresentar alternativas comerciais autorizadas quando aplicável.
9. Organizar os itens, quantidades e demais informações compreendidas.
10. Apresentar um resumo da solicitação para conferência do cliente.
11. Obter a concordância expressa do cliente antes de encaminhar a solicitação ao Módulo 06.

### 23.3. Limites de responsabilidade

O Módulo 05 não será responsável por:

- Administrar o cadastro de empresas e contatos.
- Definir ou conceder permissões de acesso.
- Administrar o catálogo de produtos e suas informações oficiais.
- Administrar tabelas de preços e condições comerciais.
- Elaborar e registrar propostas comerciais.
- Registrar pedidos ou executar aprovações internas.

Essas responsabilidades pertencem aos respectivos módulos da plataforma.

O Módulo 05 deverá consultar essas informações e utilizar seus resultados para conduzir corretamente o atendimento.

### 23.4. Condição para encaminhamento

Uma solicitação poderá ser encaminhada ao Módulo 06 quando:

1. As informações necessárias à elaboração da proposta estiverem compreendidas e organizadas para os itens que poderão compor a proposta.
2. As pendências que impeçam a elaboração da proposta inteira ou dos itens correspondentes estiverem resolvidas ou devidamente isoladas.
3. Os itens que poderão integrar uma proposta parcial estiverem identificados e suficientemente compreendidos.
4. O resumo correspondente tiver sido apresentado ao cliente.
5. O cliente tiver manifestado concordância expressa com o conteúdo apresentado.

O silêncio do cliente não será considerado concordância.

A confirmação deverá estar vinculada à versão exata do resumo apresentado, preservando o registro do conteúdo confirmado.

Uma pendência restrita a determinado item não deverá impedir automaticamente o encaminhamento dos demais itens válidos, desde que seja possível elaborar uma proposta parcial e que o cliente tenha concordado expressamente com o conteúdo encaminhado.

## 24. Início e elegibilidade do atendimento

### 24.1. Início do atendimento

O atendimento poderá ser iniciado quando uma pessoa entrar em contato pelos canais disponibilizados pela empresa.

A IA deverá interpretar a mensagem inicial e identificar, conforme as informações disponíveis, a intenção do contato.

O atendimento inicial não deverá depender da conclusão prévia de um cadastro completo.

### 24.2. Identificação e autorização

Antes de consultar ou revelar informações comerciais protegidas, a plataforma deverá verificar:

1. A identidade do contato.
2. O vínculo do contato com a empresa cliente.
3. A autorização do contato para representar essa empresa.
4. As permissões individuais concedidas ao contato para a operação solicitada.

Essas verificações deverão respeitar as responsabilidades e regras estabelecidas nos Módulos 01 e 02.

A identificação de uma pessoa ou a confirmação de seu vínculo com uma empresa não significará autorização irrestrita para acessar informações ou realizar operações comerciais.

### 24.3. Atendimento a novos interessados

Quando o contato ainda não estiver cadastrado ou autorizado, a IA poderá conduzir o atendimento inicial, respeitando os limites de acesso.

Poderá:

- Compreender a necessidade apresentada.
- Identificar os produtos ou serviços de interesse.
- Fornecer informações gerais que a empresa permita disponibilizar publicamente.
- Solicitar os dados necessários para iniciar o cadastro ou a vinculação com uma empresa.
- Aproveitar as informações já fornecidas durante a conversa, evitando perguntas repetidas.

A coleta de dados poderá ocorrer durante a própria conversa, sem exigir o preenchimento de um formulário separado como condição para iniciar o atendimento.

Enquanto a identificação, o vínculo e a autorização não estiverem devidamente validados, a IA não poderá revelar preços particulares, condições comerciais restritas, histórico de pedidos ou outras informações protegidas.

### 24.4. Continuidade após a validação

Quando a identificação, o vínculo, a autorização e as permissões necessárias forem confirmados, o atendimento poderá prosseguir conforme os limites de acesso definidos para aquele contato.

Caso alguma validação esteja pendente, a IA deverá informar a situação ao interessado e seguir as regras dos módulos responsáveis, sem liberar acesso automaticamente.

### 24.5. Critérios de aceitação

O módulo deverá permitir:

1. Iniciar atendimento sem exigir cadastro completo prévio.
2. Compreender a necessidade inicial de novos interessados.
3. Coletar informações de cadastro durante a conversa.
4. Aproveitar informações já fornecidas pelo contato.
5. Respeitar as validações de identidade, vínculo e autorização.
6. Verificar as permissões individuais antes de acessar informações ou operações protegidas.
7. Impedir a exposição de informações comerciais restritas enquanto as validações necessárias estiverem pendentes.
8. Prosseguir com o atendimento após a validação, respeitando as permissões concedidas.

---

## 25. Condução conversacional

### 25.1. Princípio de atendimento

A IA deverá conduzir o atendimento por meio de uma conversa contextual, natural e progressiva.

A interação deverá considerar as informações já fornecidas pelo cliente e o estado atual da solicitação, evitando perguntas desnecessárias, repetitivas ou desconectadas do contexto.

A conversa deverá avançar conforme as necessidades identificadas, sem exigir que o cliente forneça antecipadamente todas as informações possíveis.

### 25.2. Compreensão da solicitação

A IA deverá interpretar as mensagens do cliente para identificar:

- O que o cliente deseja adquirir.
- Quais produtos ou itens foram mencionados.
- As quantidades solicitadas, quando informadas.
- As características, marcas, apresentações ou especificações mencionadas.
- Dúvidas, restrições e condições apresentadas durante a conversa.
- Informações que ainda precisam ser esclarecidas.

A interpretação deverá considerar o contexto da conversa, e não apenas a mensagem mais recente.

### 25.3. Solicitação de informações complementares

Quando faltarem informações necessárias para compreender ou organizar a solicitação, a IA deverá perguntar ao cliente de maneira contextual.

As perguntas deverão:

1. Ser limitadas às informações realmente necessárias.
2. Considerar o que já foi informado na conversa.
3. Evitar solicitar novamente dados disponíveis e válidos no cadastro ou no histórico autorizado.
4. Ser apresentadas de maneira clara, preferencialmente sem concentrar várias perguntas desnecessárias em uma única mensagem.
5. Permitir que o cliente esclareça, corrija ou complemente suas informações.

A IA não deverá presumir respostas para preencher informações ausentes.

### 25.4. Atendimento a solicitações com vários itens

Quando o cliente solicitar diferentes produtos, a IA deverá organizar e acompanhar cada item individualmente.

Uma dúvida ou pendência relacionada a um produto não deverá impedir o atendimento dos demais itens que já possam ser compreendidos.

A plataforma deverá preservar a relação entre cada produto, sua quantidade, suas especificações e eventuais pendências.

### 25.5. Uso do contexto e do histórico

A IA poderá utilizar informações de conversas e pedidos anteriores para contextualizar o atendimento, desde que o acesso seja permitido pelas regras de identificação, autorização e permissões.

Informações históricas poderão auxiliar na compreensão de preferências e solicitações recorrentes, mas não deverão ser tratadas automaticamente como instruções atuais.

Quando uma preferência anterior puder influenciar a solicitação atual, a IA deverá confirmar com o cliente se ela continua válida.

### 25.6. Atualizações durante o atendimento

Quando uma consulta ou processamento exigir algum tempo, a IA deverá manter o cliente informado sobre o andamento.

A comunicação deverá ser objetiva e compatível com a etapa em execução, sem apresentar como concluída uma consulta que ainda esteja pendente.

A IA não deverá deixar o cliente sem retorno quando houver uma operação em andamento ou uma pendência que precise ser comunicada.

### 25.7. Critérios de aceitação

O módulo deverá permitir:

1. Interpretar mensagens considerando o contexto da conversa.
2. Identificar as informações já fornecidas pelo cliente.
3. Solicitar somente os esclarecimentos necessários.
4. Evitar perguntas repetidas.
5. Organizar solicitações com vários produtos.
6. Acompanhar individualmente as informações e pendências de cada item.
7. Utilizar histórico autorizado sem presumir que preferências antigas continuam válidas.
8. Manter o cliente informado durante consultas e etapas em andamento.
9. Preservar as informações fornecidas ao longo da conversa.

---

## 26. Identificação e organização dos produtos

### 26.1. Identificação dos produtos solicitados

A IA deverá identificar os produtos mencionados pelo cliente e relacioná-los às informações oficiais do catálogo da empresa.

A identificação deverá considerar, quando disponíveis:

- Nome comercial.
- Marca.
- Unidade comercial.
- Apresentação ou embalagem.
- Descrição e características.
- Nomes populares, abreviações e termos equivalentes reconhecidos pela empresa.

A IA poderá interpretar variações na maneira como o cliente descreve um produto, desde que exista correspondência confiável com as informações comerciais cadastradas.

### 26.2. Consulta ao catálogo e vocabulário comercial

A identificação deverá utilizar o catálogo e os termos comerciais validados pela empresa.

Quando houver correspondência confiável, a IA deverá relacionar o termo utilizado pelo cliente ao produto cadastrado.

Quando houver mais de uma possibilidade ou incerteza na identificação, deverá solicitar esclarecimentos antes de considerar o item identificado.

A IA não deverá escolher arbitrariamente entre produtos semelhantes.

### 26.3. Produtos não identificados

Quando a IA não conseguir identificar um produto com segurança, deverá:

1. Informar que precisa esclarecer qual produto foi solicitado.
2. Solicitar informações adicionais ao cliente, quando isso puder resolver a dúvida.
3. Evitar incluir o produto na solicitação enquanto sua identificação permanecer incerta.
4. Encaminhar a situação ao gerente quando não for possível resolver a identificação com segurança.

A dúvida sobre um produto não deverá impedir o atendimento dos demais itens que já estejam identificados.

### 26.4. Produtos não comercializados pela empresa

Quando ficar confirmado que um produto não faz parte do catálogo comercializado pela empresa, a IA deverá informar essa condição ao cliente.

Nessa situação:

- O produto não deverá ser incluído na solicitação destinada à elaboração de proposta.
- A IA não deverá oferecer automaticamente outro produto como substituto.
- A demanda poderá ser registrada como interesse em um produto não comercializado, para avaliação posterior da empresa.
- O registro dessa demanda não significará inclusão automática no catálogo.

### 26.5. Produtos indisponíveis ou com restrições de fornecimento

A identificação de um produto no catálogo não significará que ele esteja disponível para fornecimento.

Quando houver informação confiável de indisponibilidade ou restrição de quantidade, a IA deverá comunicar a situação ao cliente e apresentar alternativas somente quando estiverem autorizadas pela empresa.

O cliente deverá decidir se aceita uma alternativa ou se prefere manter, alterar ou retirar o item da solicitação.

A IA não poderá substituir, remover ou modificar automaticamente um produto solicitado.

As regras de consulta e tratamento da disponibilidade serão detalhadas na seção 27 e deverão respeitar o Módulo 03.

### 26.6. Organização dos itens identificados

Cada produto identificado deverá ser mantido como um item individual da solicitação.

A organização deverá preservar, conforme as informações disponíveis:

- Produto identificado.
- Quantidade solicitada.
- Unidade comercial.
- Marca e apresentação, quando especificadas.
- Características ou requisitos informados pelo cliente.
- Situação da identificação.
- Dúvidas ou pendências relacionadas ao item.

As informações deverão permanecer associadas ao respectivo item, permitindo acompanhar separadamente sua identificação e resolução.

### 26.7. Critérios de aceitação

O módulo deverá permitir:

1. Relacionar os termos utilizados pelo cliente aos produtos do catálogo.
2. Reconhecer nomes populares e abreviações validados pela empresa.
3. Solicitar esclarecimentos quando houver ambiguidade.
4. Impedir a inclusão de produtos cuja identificação permaneça incerta.
5. Encaminhar ao gerente situações que não possam ser resolvidas com segurança.
6. Identificar produtos que não são comercializados pela empresa.
7. Registrar demandas por produtos não comercializados sem alterar automaticamente o catálogo.
8. Tratar alternativas de fornecimento somente quando autorizadas pela empresa.
9. Exigir a decisão do cliente antes de substituir, remover ou modificar itens.
10. Organizar e acompanhar individualmente os produtos da solicitação.

---

## 27. Consulta às informações comerciais

### 27.1. Consultas conforme a necessidade do atendimento

A IA deverá consultar as informações comerciais progressivamente, conforme as necessidades identificadas durante a conversa.

Não será necessário consultar antecipadamente todas as informações disponíveis para cada produto.

As consultas deverão utilizar as fontes oficiais da plataforma e respeitar as regras de acesso, identificação, autorização e permissões do contato.

### 27.2. Consulta ao catálogo

A IA deverá utilizar o catálogo do Módulo 03 para consultar as informações dos produtos identificados.

Poderá utilizar as informações cadastradas para:

- Confirmar a identificação do produto.
- Apresentar descrição e características.
- Informar marca, unidade comercial e apresentação ou embalagem.
- Esclarecer dúvidas sobre as informações disponíveis.

A IA deverá apresentar somente informações existentes e validadas no catálogo.

Quando uma informação necessária não estiver cadastrada ou não puder ser confirmada, deverá informar essa limitação e solicitar esclarecimento ou encaminhar a situação ao gerente, conforme o caso.

### 27.3. Consulta à disponibilidade

A IA deverá consultar as informações de disponibilidade antes de afirmar que um produto pode ser fornecido.

Deverá distinguir:

- **Disponível:** existe confirmação válida de disponibilidade.
- **Indisponível:** existe informação confiável de que o produto não está disponível.
- **Desconhecido ou não confirmado:** não existe informação suficiente ou a confirmação perdeu a validade.

A existência de um produto ativo no catálogo não significará que ele esteja disponível em estoque.

Quando a informação estiver desconhecida, desatualizada ou sem confirmação válida, a IA deverá comunicar que precisa verificar a disponibilidade, sem afirmar que o produto está disponível ou indisponível.

Quando houver necessidade de confirmação por um funcionário, a plataforma deverá respeitar o processo definido no Módulo 03.

### 27.4. Atendimento a quantidades solicitadas

A IA deverá considerar a quantidade solicitada pelo cliente ao consultar a disponibilidade.

Quando a quantidade disponível for inferior à quantidade solicitada, deverá informar claramente:

- A quantidade solicitada.
- A quantidade que poderá ser fornecida, conforme confirmação disponível.
- Eventuais limitações identificadas.

A IA não poderá reduzir automaticamente a quantidade solicitada nem considerar aceita uma quantidade diferente.

Qualquer alteração dependerá da concordância expressa do cliente.

### 27.5. Consulta a preços e condições comerciais

Quando a solicitação exigir informações de preço, a IA deverá consultar o Módulo 04, respeitando a tabela comercial e as condições associadas à empresa cliente.

A IA não poderá:

- Escolher livremente uma tabela de preços.
- Utilizar preços de outra empresa ou de outra tabela sem autorização.
- Utilizar preços vencidos ou sem vigência válida.
- Inventar preços, descontos ou condições comerciais.
- Aplicar condições comerciais não autorizadas pela empresa.

Os preços e as condições apresentados deverão corresponder às informações comerciais válidas para aquela empresa e para o momento da consulta.

### 27.6. Ausência ou conflito de informações comerciais

Quando não houver tabela válida para a empresa cliente, a IA deverá informar que precisa de uma verificação interna.

Quando houver conflito entre tabelas ou informações comerciais, deverá:

1. Comunicar que existe uma pendência de verificação.
2. Encaminhar o problema ao gerente.
3. Impedir a continuidade da negociação que dependa da informação conflitante.
4. Preservar o contexto da conversa e as informações já coletadas.
5. Retomar o atendimento após a resolução, sem exigir que o cliente repita o que já informou.

A existência de uma pendência comercial não deverá impedir a continuidade de outros itens ou etapas que possam ser tratados com segurança.

### 27.7. Apresentação de alternativas comerciais

Quando um produto estiver indisponível ou não puder ser fornecido na quantidade solicitada, a IA poderá apresentar alternativas cadastradas e autorizadas pela empresa.

As alternativas deverão respeitar as informações comerciais disponíveis, incluindo diferenças relevantes de produto, marca, apresentação, quantidade e preço, quando aplicáveis.

A IA deverá permitir que o cliente aceite ou recuse as alternativas apresentadas.

Não poderá substituir automaticamente o produto solicitado nem modificar a quantidade ou as condições da solicitação.

### 27.8. Ausência de preço definido

Um produto sem preço definido não poderá ser utilizado na elaboração de uma proposta.

Quando a IA identificar que um produto não possui preço cadastrado ou válido:

1. Deverá impedir a inclusão daquele produto na proposta.
2. Registrar a pendência relacionada ao item.
3. Comunicar a gerência para que o preço seja definido ou corrigido.
4. Informar ao cliente que o item depende de verificação comercial, sem inventar ou presumir um preço.
5. Permitir que os demais itens com informações comerciais válidas prossigam, quando for possível elaborar uma proposta parcial e o cliente concordar com seu conteúdo.

A ausência de preço não deverá ser tratada como preço vencido ou como conflito entre tabelas. São situações distintas e deverão ser identificadas separadamente.

### 27.9. Critérios de aceitação

O módulo deverá permitir:

1. Consultar informações comerciais conforme a necessidade do atendimento.
2. Utilizar o catálogo oficial como fonte de informações dos produtos.
3. Distinguir produto cadastrado de produto disponível.
4. Identificar informações de disponibilidade desconhecidas ou sem validade.
5. Consultar disponibilidade considerando a quantidade solicitada.
6. Impedir alterações automáticas nas quantidades solicitadas.
7. Consultar preços conforme a tabela associada à empresa cliente.
8. Impedir o uso de preços vencidos, conflitantes ou não autorizados.
9. Identificar produtos sem preço definido e impedir sua utilização em propostas.
10. Comunicar à gerência a ausência de preço para correção.
11. Permitir a continuidade dos demais itens válidos quando a pendência estiver isolada.
12. Encaminhar conflitos comerciais ao gerente.
13. Preservar o contexto durante consultas e pendências.
14. Apresentar somente alternativas autorizadas pela empresa.
15. Exigir a concordância do cliente para aceitar alternativas ou alterar sua solicitação.

---

## 28. Ambiguidades e situações não resolvidas

### 28.1. Princípio de segurança

A IA deverá reconhecer situações em que não possui informações suficientes ou confiáveis para continuar determinada etapa do atendimento.

Nessas situações, deverá buscar esclarecimentos, consultar as fontes disponíveis ou encaminhar a questão para avaliação humana.

A IA não poderá inventar informações, presumir decisões do cliente ou apresentar como confirmados dados que ainda estejam pendentes.

### 28.2. Informações insuficientes

Quando faltarem informações necessárias para compreender a solicitação, a IA deverá solicitar os esclarecimentos correspondentes.

Deverá considerar o contexto da conversa e as informações já disponíveis, evitando repetir perguntas.

Quando não for possível obter a informação necessária por meio da conversa ou das fontes oficiais, deverá registrar a pendência e avaliar a necessidade de encaminhamento ao gerente.

### 28.3. Informações divergentes ou conflitantes

Quando forem identificadas informações contraditórias entre o que o cliente informou e os dados disponíveis na plataforma, a IA deverá esclarecer a divergência antes de utilizar a informação.

Quando o conflito envolver dados comerciais oficiais, como catálogo, disponibilidade, preços ou condições, deverá seguir as regras do módulo responsável e encaminhar a situação ao gerente quando necessário.

A IA não poderá escolher arbitrariamente qual informação deverá prevalecer.

### 28.4. Limites de interpretação

A IA deverá reconhecer os limites de sua capacidade de interpretação.

Quando houver dúvida sobre o significado de uma solicitação, produto, quantidade, especificação ou condição apresentada pelo cliente, deverá solicitar confirmação.

Quando a dúvida persistir, deverá encaminhar a situação ao gerente, preservando o contexto e as informações já coletadas.

### 28.5. Pendências que afetam apenas parte da solicitação

Quando uma pendência estiver relacionada a apenas um produto ou item, a IA deverá manter os demais itens em andamento sempre que isso for possível.

Cada item deverá preservar sua própria situação, informações confirmadas e pendências.

A plataforma não deverá considerar toda a solicitação bloqueada quando apenas parte dela depender de esclarecimento ou intervenção.

Uma pendência isolada de item não deverá impedir automaticamente a elaboração de uma proposta parcial para os demais itens válidos.

O encaminhamento ao Módulo 06 deverá respeitar os critérios de suficiência das informações e a concordância expressa do cliente para o conteúdo que integrará a proposta parcial.

Quando uma pendência comprometer a solicitação como um todo ou impedir a elaboração de qualquer proposta, o encaminhamento deverá aguardar sua resolução.

### 28.6. Comunicação ao cliente

Quando não puder resolver uma situação imediatamente, a IA deverá:

- Informar que existe uma pendência ou necessidade de verificação.
- Explicar, de maneira compreensível, o que precisa ser esclarecido ou confirmado.
- Informar quando a situação depender de avaliação humana.
- Preservar as informações já fornecidas pelo cliente.
- Manter o cliente informado sobre o andamento, sem prometer prazos não estabelecidos pela empresa.

### 28.7. Critérios de aceitação

O módulo deverá permitir:

1. Identificar informações insuficientes para continuar o atendimento.
2. Solicitar esclarecimentos antes de tomar decisões baseadas em informações ambíguas.
3. Identificar divergências entre informações do cliente e dados oficiais.
4. Impedir que a IA escolha arbitrariamente entre informações conflitantes.
5. Reconhecer situações que exigem intervenção humana.
6. Registrar pendências e preservar o contexto.
7. Manter itens independentes em andamento quando uma pendência não os afetar.
8. Comunicar claramente ao cliente situações não resolvidas.
9. Impedir o encaminhamento de solicitações globalmente insuficientes ao Módulo 06.
10. Permitir o encaminhamento de itens válidos para proposta parcial quando as condições de confirmação e suficiência forem atendidas.

---

## 29. Histórico e recuperação de pedidos

### 29.1. Utilização do histórico

A IA poderá utilizar o histórico de atendimentos, propostas e pedidos anteriores para contextualizar novas solicitações e facilitar a continuidade do relacionamento comercial.

O acesso ao histórico deverá respeitar as regras de identificação, autorização e permissões individuais estabelecidas no Módulo 01.

A IA deverá distinguir corretamente conversas, propostas e pedidos efetivamente registrados.

### 29.2. Recuperação de pedidos anteriores

Quando o cliente solicitar a repetição de um pedido anterior, a IA deverá localizar o pedido mais recente efetivamente registrado que corresponda à solicitação.

A recuperação deverá considerar:

- Os produtos registrados.
- As quantidades solicitadas.
- As marcas e apresentações, quando disponíveis.
- As demais especificações registradas.
- A situação conhecida do pedido.

Uma proposta que não tenha sido aceita não poderá ser tratada como pedido anterior.

Quando houver mais de um pedido possível ou não for possível identificar com segurança qual deles o cliente deseja repetir, a IA deverá solicitar esclarecimentos.

### 29.3. Pedido anterior como referência

A recuperação de um pedido anterior servirá como referência para a nova solicitação, não como autorização automática para realizar outra compra.

A IA deverá apresentar as informações recuperadas e permitir que o cliente confirme, corrija, complemente ou retire itens.

Preferências e condições utilizadas anteriormente não deverão ser presumidas como válidas para a nova solicitação.

### 29.4. Revalidação das informações comerciais

Antes de utilizar informações de um pedido anterior em uma nova solicitação, a IA deverá consultar novamente as informações comerciais aplicáveis.

Deverão ser revalidados, conforme a necessidade:

- Situação atual dos produtos no catálogo.
- Disponibilidade e quantidades que podem ser fornecidas.
- Preços e tabelas comerciais vigentes.
- Condições comerciais aplicáveis.

A IA não poderá reutilizar automaticamente preços, condições ou informações de disponibilidade de pedidos anteriores.

### 29.5. Consulta à situação de pedidos anteriores

Quando a plataforma possuir informações atualizadas sobre a situação de um pedido anterior, a IA poderá comunicá-las ao cliente, respeitando suas permissões de acesso.

A informação deverá corresponder ao estado efetivamente registrado na plataforma.

A consulta ao histórico e à situação conhecida de pedidos não significará a inclusão de um fluxo completo de pós-venda, gestão logística ou acompanhamento de entregas no escopo deste módulo.

### 29.6. Preservação do histórico

As informações recuperadas deverão manter sua relação com os registros originais.

A utilização de um pedido anterior como referência para uma nova solicitação não poderá alterar os dados do pedido original.

A nova solicitação deverá possuir seu próprio contexto e seguir as etapas de compreensão, organização e confirmação previstas neste módulo.

### 29.7. Critérios de aceitação

O módulo deverá permitir:

1. Consultar histórico respeitando identificação, autorização e permissões individuais.
2. Diferenciar conversas, propostas e pedidos registrados.
3. Localizar pedidos anteriores para referência em novas solicitações.
4. Identificar o pedido mais recente efetivamente registrado quando o cliente solicitar sua repetição.
5. Solicitar esclarecimentos quando houver ambiguidade.
6. Impedir que uma proposta não aceita seja tratada como pedido.
7. Exigir confirmação do cliente para utilizar um pedido anterior como referência.
8. Revalidar informações comerciais antes de utilizá-las em uma nova solicitação.
9. Consultar e comunicar situações de pedidos anteriores quando houver informação disponível e autorizada.
10. Preservar integralmente os registros originais.

---

## 30. Resumo e confirmação da solicitação

### 30.1. Preparação do resumo

Quando as informações necessárias para organizar a solicitação estiverem disponíveis, a IA deverá preparar um resumo para conferência do cliente.

O resumo deverá apresentar, de maneira clara e organizada, os itens compreendidos durante o atendimento.

Deverá incluir, conforme aplicável:

- Produtos identificados.
- Quantidades solicitadas.
- Marcas e apresentações especificadas.
- Características e requisitos informados.
- Alternativas escolhidas pelo cliente.
- Pendências ou limitações que precisem ser consideradas.
- Outras informações relevantes para a elaboração da proposta.

O resumo não deverá apresentar como confirmadas informações que ainda estejam pendentes ou não tenham sido validadas.

### 30.2. Apresentação ao cliente

A IA deverá apresentar o resumo e solicitar que o cliente confira as informações antes de encaminhar a solicitação ao Módulo 06.

O cliente deverá ter a possibilidade de:

- Concordar com o resumo.
- Corrigir informações.
- Complementar a solicitação.
- Alterar quantidades ou especificações.
- Retirar produtos ou itens.
- Informar que ainda precisa esclarecer algum ponto.

A IA deverá incorporar as alterações solicitadas e apresentar uma versão atualizada do resumo quando necessário.

### 30.3. Concordância expressa

O encaminhamento ao Módulo 06 dependerá da concordância expressa do cliente com o conteúdo apresentado.

A concordância deverá ser inequívoca e vinculada à versão exata do resumo submetido à conferência.

Não serão considerados concordância:

- Silêncio do cliente.
- Ausência de resposta.
- Mensagens ambíguas.
- Interações que não demonstrem claramente a aceitação do conteúdo apresentado.

A IA deverá solicitar confirmação quando não for possível determinar com segurança se o cliente concordou.

### 30.4. Registro da confirmação

A plataforma deverá registrar a confirmação do cliente, preservando:

- Identificação do contato que confirmou.
- Empresa vinculada.
- Data e horário da confirmação.
- Conteúdo exato do resumo confirmado.
- Versão do resumo correspondente.
- Registro da manifestação expressa de concordância.

Esse registro deverá permitir identificar exatamente quais informações foram apresentadas e aceitas pelo cliente.

### 30.5. Alterações após a apresentação do resumo

Quando o cliente solicitar qualquer alteração antes da confirmação, a IA deverá atualizar a solicitação e apresentar novamente o resumo para conferência.

A confirmação de uma versão anterior não poderá ser utilizada para autorizar uma versão modificada.

Cada nova versão deverá preservar a relação com as versões anteriores, permitindo identificar as alterações realizadas e qual conteúdo recebeu a concordância do cliente.

### 30.6. Limite da confirmação

A concordância com o resumo confirmará o conteúdo da solicitação comercial, mas não significará:

- Aceite de uma proposta comercial.
- Confirmação de preço ou condição comercial ainda não apresentada em proposta.
- Aprovação interna da empresa.
- Registro automático de um pedido.

A elaboração da proposta e as etapas posteriores serão de responsabilidade do Módulo 06.

### 30.7. Critérios de aceitação

O módulo deverá permitir:

1. Preparar um resumo organizado da solicitação.
2. Apresentar os itens e informações compreendidos ao cliente.
3. Permitir correções, complementações e retirada de itens.
4. Atualizar o resumo após alterações.
5. Exigir concordância expressa antes do encaminhamento.
6. Impedir que silêncio ou mensagens ambíguas sejam interpretados como confirmação.
7. Registrar quem confirmou, quando e qual versão foi aceita.
8. Preservar versões anteriores do resumo.
9. Impedir o encaminhamento de uma versão diferente daquela efetivamente confirmada.
10. Distinguir a confirmação da solicitação do aceite de proposta e da aprovação interna.

---

## 31. Continuidade e retomada

### 31.1. Continuidade do atendimento

A plataforma deverá preservar o estado e o contexto dos atendimentos enquanto houver informações, confirmações ou decisões pendentes.

A ausência de resposta do cliente não deverá provocar o encerramento automático do atendimento.

A IA deverá manter o registro da etapa em andamento, das informações já fornecidas, dos itens organizados e das pendências existentes.

### 31.2. Ausência de resposta à confirmação

Quando o cliente não responder à solicitação de confirmação do resumo, a IA poderá realizar tentativas de retomada de maneira educada e contextual.

O limite será de até duas tentativas de retomada sem resposta.

Após duas tentativas sem manifestação do cliente:

- O atendimento deverá assumir o estado **Aguardando retorno do cliente**.
- O atendimento permanecerá aberto.
- A solicitação não será encaminhada ao Módulo 06.
- A ausência de resposta não será interpretada como concordância.
- O histórico e o contexto deverão permanecer preservados.

### 31.3. Retomada pelo cliente

Quando o cliente retornar, a IA deverá recuperar o contexto e identificar a etapa em que o atendimento foi interrompido.

Deverá considerar:

- Informações já fornecidas.
- Produtos e quantidades organizados.
- Resumo apresentado anteriormente.
- Versões e confirmações registradas.
- Pendências ainda existentes.
- Consultas comerciais realizadas anteriormente.

A IA deverá retomar a conversa a partir do estado registrado, sem obrigar o cliente a repetir informações já disponíveis e válidas.

### 31.4. Revalidação das informações comerciais

Antes de continuar uma negociação interrompida, a IA deverá verificar novamente as informações comerciais que possam ter sofrido alterações durante a interrupção.

Conforme a necessidade, deverá revalidar:

- Situação dos produtos no catálogo.
- Disponibilidade e quantidades.
- Preços e tabelas comerciais.
- Condições comerciais aplicáveis.

Informações anteriores não deverão ser apresentadas como atuais sem nova validação quando sua validade depender de consulta ou vigência.

A revalidação será necessária para orientar as próximas etapas do atendimento e a elaboração de novas versões ou propostas. Ela não deverá alterar retroativamente o conteúdo de uma proposta já apresentada e ainda válida, nem modificar compromissos anteriormente assumidos.

Caso alguma informação tenha mudado e isso afete uma etapa ainda não concluída ou uma nova versão da solicitação ou proposta, a IA deverá comunicar a situação ao cliente e seguir o procedimento aplicável, preservando o histórico e as condições anteriormente apresentadas.

### 31.5. Preservação das confirmações anteriores

A retomada do atendimento não deverá apagar ou modificar confirmações e versões anteriormente registradas.

Quando houver alterações no conteúdo da solicitação após uma confirmação, será necessária uma nova apresentação e concordância expressa do cliente com a versão atualizada antes do encaminhamento ao Módulo 06.

A revalidação de informações comerciais não deverá, por si só, invalidar uma proposta já apresentada e ainda válida. As condições e versões anteriormente apresentadas deverão permanecer rastreáveis.

### 31.6. Critérios de aceitação

O módulo deverá permitir:

1. Preservar o estado e o contexto de atendimentos interrompidos.
2. Realizar até duas tentativas de retomada quando não houver resposta à confirmação.
3. Alterar o estado para **Aguardando retorno do cliente** após duas tentativas sem resposta.
4. Manter o atendimento aberto.
5. Impedir encaminhamento sem confirmação expressa.
6. Recuperar o contexto quando o cliente retornar.
7. Evitar a repetição de perguntas e informações já fornecidas.
8. Revalidar informações comerciais necessárias às próximas etapas.
9. Preservar propostas apresentadas e ainda válidas, sem alteração retroativa de suas condições.
10. Preservar versões e confirmações anteriores.
11. Exigir nova concordância quando houver alterações na solicitação.

---

## 32. Encaminhamento humano

### 32.1. Princípio de encaminhamento

O atendimento automatizado deverá ser o fluxo normal da operação comercial.

A intervenção humana deverá ocorrer quando o cliente solicitar atendimento humano ou quando a IA identificar uma situação que não consiga resolver com segurança dentro das informações, permissões e responsabilidades disponíveis.

A IA não deverá insistir em resolver situações que dependam de avaliação ou decisão humana.

### 32.2. Solicitação de atendimento humano pelo cliente

O cliente poderá solicitar atendimento humano a qualquer momento da conversa.

Quando isso ocorrer, a IA deverá:

1. Reconhecer a solicitação.
2. Interromper a condução automatizada da etapa que motivou o pedido, quando necessário.
3. Preservar as informações e o contexto já registrados.
4. Encaminhar a solicitação ao gerente.
5. Informar ao cliente que o pedido de atendimento humano foi registrado.

A IA não deverá dificultar ou ignorar a solicitação do cliente.

### 32.3. Situações que exigem intervenção humana

A IA deverá encaminhar ao gerente situações que não possam ser resolvidas com segurança, incluindo:

- Produtos cuja identificação permaneça inconclusiva.
- Informações comerciais conflitantes.
- Ausência de dados essenciais que não possam ser obtidos.
- Ausência de preço definido para um produto, situação que deverá ser comunicada à gerência para correção conforme o Módulo 04.
- Dúvidas que dependam de avaliação ou decisão da empresa.
- Situações excepcionais que ultrapassem as regras estabelecidas para o atendimento automatizado.

Negociações de condições especiais que estejam cobertas por uma delegação válida e respeitem os limites estabelecidos pela empresa poderão prosseguir com o funcionário delegado, sem encaminhamento automático ao gerente apenas por serem negociações especiais.

O encaminhamento ao gerente será necessário quando não houver delegação válida para a negociação ou quando a condição solicitada ultrapassar os limites da delegação existente.

A delegação para negociar condições comerciais não deverá ser interpretada como autoridade para aprovar internamente propostas ou pedidos.

O encaminhamento deverá ocorrer sem apresentar informações não confirmadas como se fossem válidas.

### 32.4. Controle do encaminhamento

O encaminhamento inicial deverá ser direcionado ao gerente, quando a situação exigir decisão gerencial.

Caberá ao gerente avaliar a situação e decidir se o atendimento será assumido por ele ou encaminhado a um funcionário autorizado.

Quando houver delegação válida para uma atividade ou negociação específica, o atendimento poderá permanecer com o funcionário delegado dentro dos limites dessa autorização.

A IA não deverá escolher ou transferir automaticamente o atendimento para qualquer funcionário.

A responsabilidade pela definição das delegações e dos atendentes humanos permanecerá sob controle da empresa.

### 32.5. Registro do encaminhamento

A plataforma deverá registrar:

- Identificação do atendimento.
- Cliente e contato envolvidos.
- Motivo do encaminhamento.
- Contexto e histórico relevante.
- Produtos e itens envolvidos.
- Pendências existentes.
- Data e horário do encaminhamento.
- Responsável pela decisão de encaminhamento interno, quando aplicável.

O registro deverá permitir que o responsável humano compreenda a situação sem exigir que o cliente repita toda a conversa.

### 32.6. Comunicação e continuidade

Enquanto aguardar avaliação humana, o cliente deverá receber informações claras sobre a existência e o andamento da pendência.

A IA não deverá prometer prazos de atendimento que não tenham sido definidos pela empresa.

O encaminhamento de uma solicitação não deverá interromper os demais atendimentos da plataforma.

Quando a pendência for resolvida, o atendimento poderá ser retomado com o contexto preservado, respeitando as decisões e orientações registradas pelo responsável humano.

### 32.7. Critérios de aceitação

O módulo deverá permitir:

1. Reconhecer pedidos de atendimento humano em qualquer etapa.
2. Encaminhar situações que ultrapassem os limites de resolução segura da IA.
3. Direcionar ao gerente as situações que dependam de decisão gerencial.
4. Permitir que o gerente escolha o funcionário responsável.
5. Respeitar delegações válidas para negociações específicas e seus limites.
6. Impedir transferências automáticas para funcionários não definidos ou autorizados pela empresa.
7. Preservar o histórico e o contexto do atendimento.
8. Registrar o motivo e os dados relevantes do encaminhamento.
9. Informar o cliente sobre o andamento sem prometer prazos inexistentes.
10. Retomar o atendimento após a resolução da pendência.
11. Manter os demais atendimentos funcionando normalmente.

---

## 33. Integração com o Módulo 06

### 33.1. Responsabilidade pela integração

O Módulo 05 será responsável por entregar ao Módulo 06 uma solicitação comercial compreendida, organizada e confirmada expressamente pelo cliente.

O Módulo 06 será responsável por utilizar essas informações para elaborar a proposta comercial e conduzir as etapas posteriores, conforme suas próprias regras.

### 33.2. Condições para encaminhamento

A solicitação poderá ser encaminhada quando:

1. As informações necessárias para elaboração da proposta estiverem organizadas para os itens que poderão compor a proposta.
2. Os itens incluídos estiverem identificados.
3. As quantidades e especificações informadas estiverem registradas.
4. As pendências que impeçam a elaboração da proposta inteira ou dos itens correspondentes estiverem resolvidas ou devidamente isoladas.
5. O cliente tiver manifestado concordância expressa com o resumo correspondente aos itens que serão encaminhados.

Uma pendência isolada de item não deverá bloquear automaticamente os demais itens válidos.

Quando for possível elaborar uma proposta parcial, os itens sem pendências impeditivas poderão ser encaminhados ao Módulo 06, desde que estejam suficientemente compreendidos, organizados e expressamente confirmados pelo cliente.

Quando uma pendência comprometer a solicitação como um todo ou impedir a elaboração de qualquer proposta, o encaminhamento deverá aguardar sua resolução.

O encaminhamento não poderá incluir itens cuja identificação, informações essenciais ou condições necessárias à elaboração da proposta permaneçam indefinidas.

### 33.3. Informações encaminhadas

O Módulo 05 deverá disponibilizar ao Módulo 06 as informações necessárias à elaboração da proposta, incluindo:

- Identificação da empresa cliente.
- Identificação do contato responsável pela solicitação.
- Registro da validação de identidade, vínculo, autorização e permissões pertinentes à operação.
- Identificação dos produtos solicitados.
- Quantidades e unidades comerciais.
- Marcas, apresentações e especificações informadas.
- Alternativas escolhidas expressamente pelo cliente.
- Observações e requisitos relevantes.
- Registro de eventuais condições ou informações que precisem ser consideradas na elaboração da proposta.
- Histórico relevante da conversa.
- Versão exata do resumo confirmado.
- Registro da concordância expressa do cliente, com data e horário.
- Identificação dos itens que não foram incluídos no encaminhamento, quando houver pendências isoladas que permitam uma proposta parcial.

As informações deverão preservar sua origem e permitir rastrear o conteúdo que fundamentou a elaboração da proposta.

O registro das validações de autorização e permissões deverá permitir comprovar que os controles necessários foram realizados para aquela operação, sem exigir o compartilhamento indiscriminado de todas as permissões do contato.

### 33.4. Preservação da solicitação confirmada

O encaminhamento ao Módulo 06 não poderá alterar o conteúdo da solicitação confirmada pelo cliente.

As informações deverão ser entregues de maneira estruturada, preservando os itens, quantidades, especificações e demais dados registrados.

Caso seja identificada alguma inconsistência que impeça a elaboração da proposta, a solicitação deverá retornar ao Módulo 05 para esclarecimento, mantendo seu histórico e sua versão anteriormente confirmada.

Quando a resolução da inconsistência exigir qualquer alteração no conteúdo confirmado pelo cliente, o Módulo 05 deverá:

1. Atualizar a solicitação conforme os esclarecimentos e as informações validadas.
2. Gerar uma nova versão do resumo.
3. Apresentar a nova versão ao cliente para conferência.
4. Obter nova concordância expressa do cliente.
5. Encaminhar novamente a solicitação ao Módulo 06 somente após essa confirmação.

A confirmação de uma versão anterior não poderá ser utilizada para autorizar alterações posteriores.

### 33.5. Limites entre os módulos

Após o encaminhamento:

- O Módulo 05 não será responsável pela elaboração da proposta.
- O Módulo 05 não deverá registrar aceite de proposta ou aprovação interna.
- O Módulo 06 deverá respeitar o conteúdo da solicitação confirmada.
- Alterações posteriores na solicitação deverão preservar o histórico e seguir as regras de revisão e nova confirmação aplicáveis.
- O aceite da proposta e a aprovação interna continuarão sendo eventos distintos.

A passagem de uma solicitação ao Módulo 06 não significará que a proposta foi aceita ou que o pedido foi aprovado.

### 33.6. Continuidade após o encaminhamento

O histórico do atendimento realizado pelo Módulo 05 deverá permanecer acessível aos módulos responsáveis pelas etapas posteriores, respeitando as permissões de acesso.

As informações deverão permitir reconstruir a sequência entre:

1. Solicitação inicial do cliente.
2. Compreensão e organização dos itens.
3. Apresentação do resumo.
4. Concordância expressa do cliente.
5. Encaminhamento ao Módulo 06.
6. Elaboração e apresentação da proposta.

Essa rastreabilidade deverá preservar a relação entre a solicitação original e as operações comerciais decorrentes dela.

### 33.7. Critérios de aceitação

O módulo deverá permitir:

1. Encaminhar somente solicitações ou itens que atendam às condições estabelecidas.
2. Impedir o encaminhamento sem concordância expressa do cliente.
3. Disponibilizar ao Módulo 06 as informações necessárias à elaboração da proposta.
4. Preservar o conteúdo e a versão exata da solicitação confirmada.
5. Registrar a origem e a confirmação das informações encaminhadas.
6. Identificar inconsistências que impeçam a elaboração da proposta.
7. Preservar o histórico em caso de retorno para esclarecimento.
8. Exigir nova concordância quando o esclarecimento modificar o conteúdo anteriormente confirmado.
9. Permitir proposta parcial quando houver pendência isolada de item e os demais itens forem válidos e confirmados.
10. Manter a separação das responsabilidades dos Módulos 05 e 06.
11. Preservar a rastreabilidade entre o atendimento e as operações comerciais posteriores.

## 34. Critérios gerais de aceitação

O Módulo 05 será considerado funcionalmente adequado quando conseguir conduzir o atendimento comercial desde o primeiro contato até a confirmação expressa da solicitação, respeitando as responsabilidades dos demais módulos.

### 34.1. Atendimento e compreensão

O módulo deverá:

1. Iniciar o atendimento sem exigir cadastro completo prévio.
2. Compreender a intenção do cliente considerando o contexto da conversa.
3. Solicitar somente as informações necessárias para avançar.
4. Evitar perguntas repetitivas.
5. Organizar solicitações com vários produtos, acompanhando cada item individualmente.
6. Preservar o contexto durante todo o atendimento.

### 34.2. Identificação e segurança comercial

O módulo deverá:

1. Respeitar as regras de identificação, vínculo e autorização dos contatos.
2. Verificar as permissões individuais antes de acessar informações ou operações protegidas.
3. Impedir a exposição de informações comerciais restritas sem autorização.
4. Utilizar exclusivamente informações comerciais confiáveis e validadas.
5. Não inventar produtos, características, preços, disponibilidade ou condições comerciais.
6. Reconhecer ambiguidades, divergências e informações insuficientes.

### 34.3. Tratamento de produtos e informações comerciais

O módulo deverá:

1. Identificar produtos conforme o catálogo oficial.
2. Distinguir produtos não identificados, não comercializados e indisponíveis.
3. Consultar disponibilidade considerando as quantidades solicitadas.
4. Consultar preços e condições conforme a tabela aplicável à empresa.
5. Apresentar somente alternativas autorizadas.
6. Exigir a decisão do cliente para alterações de produtos ou quantidades.
7. Manter itens independentes em andamento quando uma pendência não os afetar.
8. Impedir a utilização em propostas de produtos sem preço definido.
9. Comunicar à gerência a ausência de preço para que a informação seja definida ou corrigida.
10. Permitir a continuidade dos demais itens válidos quando a pendência de preço estiver isolada e houver condições para uma proposta parcial.

### 34.4. Histórico e continuidade

O módulo deverá:

1. Recuperar informações anteriores respeitando as permissões de acesso.
2. Diferenciar propostas de pedidos efetivamente registrados.
3. Utilizar pedidos anteriores somente como referência para novas solicitações.
4. Revalidar informações comerciais antes de continuar negociações interrompidas.
5. Preservar o estado e o histórico dos atendimentos.
6. Realizar até duas tentativas de retomada diante da ausência de resposta à confirmação.
7. Manter aberto o atendimento classificado como Aguardando retorno do cliente.
8. Retomar a conversa sem exigir a repetição de informações já disponíveis e válidas.
9. Preservar propostas apresentadas e ainda válidas, sem alterar retroativamente suas condições.

### 34.5. Confirmação da solicitação

O módulo deverá:

1. Preparar um resumo claro e organizado da solicitação.
2. Permitir correções, complementações e retirada de itens.
3. Apresentar uma versão atualizada do resumo quando houver alterações.
4. Exigir concordância expressa do cliente.
5. Não interpretar silêncio ou mensagens ambíguas como confirmação.
6. Registrar o contato responsável, a data, o horário e a versão confirmada.
7. Preservar versões anteriores e suas respectivas manifestações.

### 34.6. Encaminhamento e integração

O módulo deverá:

1. Reconhecer solicitações de atendimento humano.
2. Encaminhar situações não resolvidas com segurança ao gerente ou ao responsável definido conforme as delegações válidas.
3. Permitir que o gerente defina o funcionário responsável quando a situação depender de sua decisão.
4. Respeitar delegações válidas para negociações específicas, sem confundi-las com autoridade para aprovação interna.
5. Preservar o contexto e registrar as pendências do encaminhamento.
6. Comunicar à gerência a ausência de preço definido para um produto e impedir sua utilização na proposta até a correção.
7. Impedir o encaminhamento ao Módulo 06 sem os requisitos necessários e a confirmação expressa do cliente para os itens encaminhados.
8. Permitir o encaminhamento de itens válidos para proposta parcial quando houver pendência isolada em outros itens.
9. Entregar ao Módulo 06 as informações e a versão exata da solicitação confirmada.
10. Preservar a separação entre confirmação da solicitação, aceite da proposta e aprovação interna.

### 34.7. Critério final de conclusão

A missão do Módulo 05 estará cumprida quando a plataforma conseguir transformar uma conversa comercial em uma solicitação organizada, compreendida e expressamente confirmada pelo cliente, pronta para ser encaminhada ao Módulo 06.

O módulo deverá manter o histórico e a rastreabilidade do atendimento, sem assumir decisões comerciais que pertençam ao cliente ou à empresa.
