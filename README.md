# POD · Raio-X de Relacionamento — demo

Demonstração estática do **data lake de relacionamento da Power of Data**: o comercial
digita o nome de um cliente e vê, antes da reunião, tudo o que a POD já construiu com
ele — contatos, quais comerciais já tocam a conta, oportunidades, eventos, NPS e a
linha do tempo.

**▶ Abrir a demo:** https://jpborgesll.github.io/pod-raio-x-demo/

Sugestão: comece por `CEMIG`. Deep-link direto:
[`?empresa=CEMIG`](https://jpborgesll.github.io/pod-raio-x-demo/?empresa=CEMIG).

## O que está sendo demonstrado

Pipeline medalhão em DuckDB, da planilha crua até a busca:

| Camada | O que faz |
|---|---|
| **Landing** | A planilha exportada de RD Station + Pipedrive, crua |
| **Bronze** | Cópia imutável, com data de ingestão |
| **Prata** | Higienização + **resolução de entidade** — CEMIG, CEMIG D e Companhia Energética de Minas Gerais viram uma empresa só |
| **Ouro** | Variáveis por empresa e por contato + grafo de relacionamento |
| **App** | A busca 360 (Streamlit em produção; esta página é a versão estática) |

## Sobre os dados

🔒 Todos os dados desta página são **fictícios**, gerados por um script de exemplo.
Nenhum dado real de cliente ou de lead da POD foi publicado. O código do pipeline
está em repositório privado.

## Como esta página funciona

`index.html` + `data/lake.json` — HTML/CSS/JS puro, sem build e sem servidor. O JSON é
um dump da camada ouro gerado por `exportar_site.py` no repositório privado.
