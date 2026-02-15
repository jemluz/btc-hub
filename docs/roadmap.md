# 🗺️ Roadmap - BTC Indicators Dashboard

## 📦 V1 - SPIKE DE BACKEND (Validação de Dados)

**Status:** 🔄 Em desenvolvimento  
**Duração estimada:** 1 semana  
**Objetivo:** Validar que conseguimos obter e processar dados corretamente.

### Escopo

#### ✅ APIs Implementadas

- [x] Fear & Greed Index (Alternative.me)
- [x] Mayer Multiple (CoinGecko + cálculo)
- [x] Rainbow Chart (CoinGecko + regressão log)
- [x] Stock-to-Flow (Blockchain.info + cálculo)

#### ✅ Entregas

- [x] 4 API routes (`/api/[indicator]/route.ts`)
- [x] Respostas JSON estruturadas
- [x] Página de teste simples
- [x] Validação de dados

#### 📋 Checklist V1

```
□ Setup Next.js + TypeScript
□ /api/fear-greed funcionando
□ /api/mayer-multiple calculando corretamente
□ /api/rainbow retornando bandas
□ /api/stock-to-flow calculando S2F
□ Página de teste renderizando JSON
□ Comparar dados com sites de referência
□ Documentar estrutura de resposta
```

### Critérios de Sucesso

✅ Todas as 4 APIs retornam dados válidos  
✅ Cálculos conferem com fontes conhecidas  
✅ Nenhum erro de rate limit  
✅ Código limpo e documentado

---

## 🎨 V2 - DASHBOARD COM GRÁFICOS

**Status:** ⏳ Planejado  
**Duração estimada:** 1-2 semanas  
**Pré-requisito:** V1 completa  
**Objetivo:** Transformar dados em visualizações úteis.

### Escopo

#### 📊 Componentes de Gráfico

- [ ] `FearGreedChart.tsx` - Line chart com histórico 30 dias
- [ ] `MayerMultipleChart.tsx` - Line chart com zonas de referência
- [ ] `RainbowChart.tsx` - Multi-line chart com bandas coloridas
- [ ] `StockToFlowChart.tsx` - Cards com métricas + info halving

#### 🎨 Interface

- [ ] Layout responsivo (mobile + desktop)
- [ ] Grid 2 colunas em telas grandes
- [ ] Header com título e descrição
- [ ] Footer com disclaimers e créditos
- [ ] Loading states
- [ ] Error handling

#### 🔄 Funcionalidades

- [ ] Auto-refresh a cada 10 minutos
- [ ] Botão de refresh manual
- [ ] Timestamp de última atualização
- [ ] Tooltips informativos

#### 📋 Checklist V2

```
□ Instalar Recharts
□ Criar componente FearGreedChart
□ Criar componente MayerMultipleChart
□ Criar componente RainbowChart
□ Criar componente StockToFlowChart
□ Página principal com todos os gráficos
□ Implementar auto-refresh
□ Testar responsividade
□ Adicionar disclaimers
□ Deploy no Vercel
```

### Critérios de Sucesso

✅ Dashboard carrega em < 3 segundos  
✅ Gráficos renderizam corretamente  
✅ Responsivo em mobile/tablet/desktop  
✅ Auto-refresh funcionando  
✅ Deploy em produção funcionando

---

## 🚀 V3 - MELHORIAS E OTIMIZAÇÕES

**Status:** 💡 Ideias  
**Duração estimada:** 2-3 semanas  
**Pré-requisito:** V2 completa  
**Objetivo:** Melhorar UX e adicionar features avançadas.

### Features Planejadas

#### 🎯 Alta Prioridade

- [ ] **Cache inteligente**
  - Redis ou Vercel KV
  - Reduzir chamadas às APIs
  - Melhorar performance

- [ ] **Configurações de usuário**
  - Escolher quais gráficos exibir
  - Ordem personalizada
  - Salvar no localStorage

- [ ] **Modo escuro**
  - Toggle dark/light mode
  - Persistir preferência

#### 🔔 Média Prioridade

- [ ] **Sistema de alertas**
  - Notificar quando indicadores atingem valores
  - Ex: "Fear & Greed < 20" → notificação

- [ ] **Comparação temporal**
  - Ver indicadores há 1 mês, 6 meses, 1 ano
  - Overlay de períodos

- [ ] **Export de dados**
  - Download CSV/JSON
  - Compartilhar snapshot

#### 🎨 Baixa Prioridade

- [ ] **Temas customizáveis**
  - Diferentes paletas de cores
  - Temas da comunidade

- [ ] **Indicadores adicionais** (requer APIs pagas)
  - MVRV-Z Score (Glassnode)
  - NUPL (Glassnode)
  - Puell Multiple (Glassnode)
  - VDD (Glassnode)

- [ ] **Análise correlacionada**
  - Mostrar correlações entre indicadores
  - Sugestões baseadas em patterns

---

## 🔮 V4+ - FUTURO (Ideias)

### Possíveis Features

**Social:**

- Comentários/discussões por indicador
- Compartilhar no Twitter/Nostr
- Perfis de usuário

**Análise Avançada:**

- Machine Learning para predições
- Backtesting de estratégias
- Simulador de portfolios

**Mobile:**

- App React Native
- Push notifications
- Widgets iOS/Android

**Monetização (se necessário):**

- Tier gratuito com indicadores básicos
- Tier premium com indicadores pagos
- Sem ads (sempre)

---

## 📊 Timeline Estimado

```
┌─────────────────────────────────────────────────────────┐
│ Fev 2026 │ Mar 2026 │ Abr 2026 │ Mai 2026 │ Jun 2026   │
├─────────────────────────────────────────────────────────┤
│    V1    │    V2    │    V3    │    V3    │    V4      │
│  (1 sem) │ (2 sem)  │ (2 sem)  │ (2 sem)  │   (TBD)    │
└─────────────────────────────────────────────────────────┘
```

**Nota:** Timeline flexível baseado em disponibilidade de tempo.

---

## 🎯 Objetivos por Versão

| Versão | Objetivo Principal          | Usuários Alvo      |
| ------ | --------------------------- | ------------------ |
| V1     | Validar viabilidade técnica | Dev (você)         |
| V2     | Produto mínimo viável (MVP) | Early adopters     |
| V3     | Produto polido e otimizado  | Comunidade Bitcoin |
| V4+    | Features avançadas          | Power users        |

---

## 📈 Métricas de Sucesso

### V1

- ✅ Todas APIs funcionando
- ✅ Dados validados

### V2

- 🎯 100+ usuários únicos/mês
- 🎯 Deploy estável sem crashes
- 🎯 Feedback positivo inicial

### V3

- 🎯 1000+ usuários únicos/mês
- 🎯 < 2s load time
- 🎯 5+ stars no GitHub

### V4+

- 🎯 10k+ usuários únicos/mês
- 🎯 Mencionado em comunidades BTC
- 🎯 Contribuições open-source

---

## 🔄 Processo de Desenvolvimento

### Para cada versão:

1. **Planejamento** (1-2 dias)
   - Definir escopo fechado
   - Criar issues no GitHub
   - Estimar tempo

2. **Desenvolvimento** (60% do tempo)
   - Implementar features
   - Commits frequentes
   - Code review

3. **Testes** (20% do tempo)
   - Testes manuais
   - Validar em diferentes browsers
   - Mobile testing

4. **Deploy** (10% do tempo)
   - Deploy em staging
   - Testes finais
   - Deploy em produção

5. **Documentação** (10% do tempo)
   - Atualizar README
   - Changelog
   - API docs

---

## 🤝 Como Contribuir com o Roadmap

Tem ideias? Abra uma issue com:

- **Feature Request:** Descreva a feature e o problema que ela resolve
- **Bug Report:** Descreva o bug e como reproduzir
- **Discussion:** Inicie discussão sobre direção do projeto

---

**Última atualização:** 2026-02-12  
**Próxima revisão:** Após conclusão de cada versão
