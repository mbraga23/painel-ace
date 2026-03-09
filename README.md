# 🦟 ACE Lagoa Santa — Painel de Monitoramento v4.0

> Dashboard web para acompanhamento em tempo real das atividades dos Agentes de Combate às Endemias (ACE) do município de Lagoa Santa/MG.

![Status](https://img.shields.io/badge/status-ativo-34d399?style=flat-square)
![Versão](https://img.shields.io/badge/versão-2.0-4f8ff7?style=flat-square)
![Licença](https://img.shields.io/badge/licença-proprietário-fbbf24?style=flat-square)

---

## 📋 Sobre

Este painel se conecta diretamente ao **Supabase** para visualizar dados sincronizados pelo aplicativo mobile ACE Lagoa Santa. É um arquivo HTML único, 100% client-side — sem backend, sem framework, sem complicação.

### Funcionalidades

| Feature | Status | Descrição |
|---------|--------|-----------|
| Dashboard interativo | ✅ | KPIs animados, gráficos de visitas, depósitos e ranking |
| Mapa de calor | ✅ | Visualização geográfica dos focos de depósitos |
| Ranking de recusas | ✅ | Top ruas com mais recusas por território |
| Comparativo de territórios | ✅ | Análise lado a lado entre territórios |
| Ranking de agentes | ✅ | Produtividade e desempenho individual |
| Filtros avançados | ✅ | Por data, agente e território |
| Detalhamento de depósitos | ✅ | Inspecionados vs eliminados vs tratados |
| Espécimes Aedes | ✅ | Tabela por semana epidemiológica |
| Registro de visitas | ✅ | Últimas 300 visitas com status e GPS |

---

## 🚀 Como Usar

### Acesso Online

Acesse o painel em: **[https://mbraga23.github.io/painel-ace/](https://mbraga23.github.io/painel-ace/)**

Na tela de login, informe:
- **URL do Projeto** — encontre em Supabase → Settings → API
- **Anon Key (Legacy)** — a key que começa com `eyJ...`

> As credenciais ficam salvas apenas no localStorage do seu navegador.

### Acesso Local

Baixe o arquivo `index.html` e abra diretamente no navegador.

---

## 🛠️ Stack Tecnológica

| Tecnologia | Uso |
|------------|-----|
| [Supabase JS](https://supabase.com/docs/reference/javascript) | Conexão com banco de dados |
| [Chart.js](https://www.chartjs.org/) | Gráficos interativos |
| [Leaflet](https://leafletjs.com/) | Mapas |
| [Leaflet.heat](https://github.com/Leaflet/Leaflet.heat) | Mapa de calor |
| [CartoDB Dark](https://carto.com/basemaps) | Tiles do mapa |
| HTML/CSS/JS puro | Zero dependências de build |

---

## 📊 Abas do Painel

### 📊 Visão Geral
KPIs principais (visitas, quarteirões, depósitos, recusas, fechados, agentes), gráfico de visitas por dia, tipos de imóvel, depósitos por tipo e ranking de agentes. Filtros por período, agente e território.

### 🏘️ Territórios
Cards visuais de cada território com barras de progresso, gráficos comparativos de visitas, depósitos empilhados por tipo, pendências e índice de eficiência (depósitos/visita). Tabela comparativa com % de recusa.

### 👤 Agentes
Ranking geral de visitas com medalhas, gráfico de produtividade (visitas/dia trabalhado), tabela detalhada com todas as métricas individuais.

### 🗺️ Mapa de Calor
Mapa interativo com heatmap de depósitos, markers clicáveis com popup detalhado, legenda de cores por intensidade. Centralizado em Lagoa Santa/MG.

### 🪣 Depósitos
Comparação inspecionados vs eliminados vs tratados por tipo (A1 a E), gráfico de proporção de ações, tabela de espécimes de Aedes Aegypti e Albopictus por semana epidemiológica.

### ⚠️ Pendências
Gráfico de pendências por tipo, top 20 ruas com mais recusas, evolução temporal de pendências.

### 📋 Visitas
Registro das últimas 300 visitas com data, agente, endereço, tipo de imóvel, quarteirão, depósitos, status e GPS.

---

## 🗄️ Banco de Dados (Supabase)

### Tabelas
- `agentes` — Cadastro dos agentes
- `registros_diarios` — Registros diários de trabalho
- `visitas` — Visitas individuais com todos os campos do formulário
- `resumos_semanais` — Resumos por semana epidemiológica

### Views
- `view_stats_agente` — Estatísticas agregadas por agente
- `view_mapa_calor` — Pontos GPS com depósitos para o mapa
- `view_ranking_recusas` — Ranking de recusas por logradouro

---

## 📱 App Mobile

Este painel complementa o aplicativo Flutter **ACE Lagoa Santa**, que os agentes usam em campo para registrar visitas, depósitos, pendências e fotos com GPS. O app sincroniza automaticamente com o Supabase quando há conexão.

---

## 🔒 Segurança

- As credenciais do Supabase ficam salvas **apenas no navegador do usuário** (localStorage)
- Nenhuma chave está hardcoded no código
- RLS (Row Level Security) habilitado em todas as tabelas
- A anon key permite apenas operações definidas pelas policies

---

## 📄 Licença

Projeto proprietário — uso restrito à Prefeitura Municipal de Lagoa Santa/MG.

---

<p align="center">
  Desenvolvido com 🦟 para o combate às endemias em Lagoa Santa/MG
</p>
