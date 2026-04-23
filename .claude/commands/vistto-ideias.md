---
description: Roda o fluxo completo do banco de ideias semanal, do input do n8n até o Google Docs.
argument-hint: "data de início da semana no formato DD-MM-AAAA (ex: 21-04-2026)"
---

# Vistto Ideias — Semana de $ARGUMENTS

## Passo 0 — Setup

Crie a pasta da semana:
./semanas/$ARGUMENTS/

Data de hoje: rode `date +%Y-%m-%d`

## Passo 1 — Receber dados

Pergunte ao usuário:
"Cole aqui os dados dos vídeos enviados pelo n8n para a semana de $ARGUMENTS."

Aguarde a resposta antes de continuar.

## Passo 2 — Execução

**Fase 1** → Acione o `coletor` com os dados recebidos
**Fase 2** → Após 00-input.md pronto, acione o `analisador`
**Fase 3** → Após 01-analise.md pronto, acione o `filtro-cfm`
**Fase 4** → Após 02-filtro-cfm.md pronto, acione o `gerador-ideias` para os 5 nichos em PARALELO
**Fase 5** → Após todos os 03-*.md prontos, acione o `publicador`

## Passo 3 — Entrega

Apresente ao usuário:
1. Link do Google Docs com o banco da semana
2. Resumo: X trends processadas, X ideias geradas, X nichos cobertos
3. Avise se algum vídeo foi descartado pelo filtro-cfm e por quê
