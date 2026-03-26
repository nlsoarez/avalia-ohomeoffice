# COP Rede — Portal de Avaliação Home Office

Portal de monitoramento contínuo de KPIs para avaliação de colaboradores (Home Office).

## Como usar

1. Acesse o portal via GitHub Pages
2. Faça upload das planilhas:
   - **Indicadores Residencial** → aceita múltiplos arquivos de uma vez. O mês é detectado pelo campo `ANOMES` de cada arquivo.
   - **Indicadores TOA** → aceita múltiplos arquivos. Mês auto-detectado.
   - **TOA Chat** → aceita múltiplos arquivos. Mês auto-detectado.
   - **Ocupação DPA** → arquivo único consolidado. O portal extrai cada mês automaticamente do pivot cache XML interno.
3. Configure o **período de avaliação** (quantidade de meses e mês inicial)
4. Os dados são processados **100% no navegador** — nenhum dado sai da sua máquina

## Estrutura de Upload

```
Residencial ──── selecione todos de uma vez ──→ [Jan.xlsx, Fev.xlsx, Mar.xlsx]
TOA Form ─────── selecione todos de uma vez ──→ [Jan.xlsx, Fev.xlsx, Mar.xlsx]
TOA Chat ─────── selecione todos de uma vez ──→ [Jan.xlsx, Fev.xlsx, Mar.xlsx]
DPA ──────────── arquivo único ───────────────→ [Ocupacao_DPA_2026.xlsx]
```

O portal detecta o mês de cada arquivo automaticamente. Não há slots fixos — funciona para qualquer mês/ano.

## Indicadores e Metas

| Indicador | Meta | Fonte |
|-----------|------|-------|
| ETIT (GPON + Fibra HFC) | ≥ 90% | Indicadores Residencial |
| Assertividade (GPON + Fibra HFC) | ≥ 90% | Indicadores Residencial |
| DPA (Ocupação Produtiva) | ≥ 90% | Ocupação DPA |
| Formulário TOA | ≤ 15 min (≥90% aderência) | Indicadores TOA |
| Chat TOA | ≤ 10 min (≥90% aderência) | TOA Chat |

## Critérios de Classificação

- **Aprovado** → Média ≥ 90% em ≥75% dos meses do período
- **Plano de Melhoria** → Média entre 80-89%
- **Não Aprovado** → Média < 80%

## Deploy no GitHub Pages

1. Crie um repositório no GitHub
2. Faça upload do `index.html`
3. Settings → Pages → Source: main branch
4. Acesse em `https://seu-usuario.github.io/nome-do-repo/`

## Tecnologias

- HTML/CSS/JS puro (zero build)
- SheetJS (parsing Excel)
- JSZip (extração DPA pivot cache)
- 100% client-side
