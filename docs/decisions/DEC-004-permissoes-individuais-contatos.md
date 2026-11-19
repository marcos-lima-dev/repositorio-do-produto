# DEC-004 — Permissões individuais dos contatos autorizados

**Produto:** Plataforma de Atendimento Inteligente  
**Data:** 18 de novembro de 2026  
**Status:** Aprovada

## 1. Contexto

O Módulo 01 — Identificação e autorização de contatos estabeleceu inicialmente que todos os contatos autorizados de uma mesma empresa teriam os mesmos poderes nas operações comerciais.

Durante a especificação do Módulo 05, foi identificada a necessidade de permitir que a empresa controle individualmente as permissões concedidas a cada contato.

A identificação e a autorização de uma pessoa para representar uma empresa não significam que ela deva ter acesso irrestrito às informações ou operações comerciais.

## 2. Decisão

A empresa deverá definir as permissões de cada contato autorizado.

Contatos vinculados à mesma empresa poderão possuir permissões diferentes, conforme a configuração estabelecida pela empresa.

A autorização de um contato não concederá automaticamente acesso a todas as informações ou operações disponíveis na plataforma.

## 3. Consequências e limites

- O Módulo 01 deverá contemplar permissões individuais para os contatos autorizados.
- O sistema deverá verificar as permissões do contato antes de permitir o acesso a informações ou operações protegidas.
- A autorização de um contato e suas permissões deverão ser tratadas como informações distintas.
- As permissões não deverão ser presumidas apenas com base na identificação do contato ou no vínculo com a empresa.
- A lista de permissões disponíveis, sua granularidade e suas regras de configuração serão especificadas posteriormente.
- As permissões comerciais não substituirão as regras de aprovação interna de propostas e pedidos.
- A definição das permissões deverá respeitar as responsabilidades já estabelecidas para o gerente e para os funcionários autorizados.

## 4. Documentos relacionados

- `docs/03-prd.md`
- `docs/decisions/DEC-001-supervisao-operacional.md`
- `docs/decisions/DEC-003-principios-atendimento-comercial.md`