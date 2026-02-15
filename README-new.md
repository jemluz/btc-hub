#hubBTC

> Close those tabs! Open huBTC.

Real-time Bitcoin on-chain indicators in a single dashboard.
Stop juggling 10+ browser tabs. Track Fear & Greed, Mayer Multiple, Rainbow Chart, Stock-to-Flow, and more—all in one beautiful dashboard.

**One tab. All the charts.**

🔓 Open-source • 🆓 100% Free • 📊 Real-time data

## 📖 Sobre o Projeto

Dashboard centralizado para monitorar múltiplos indicadores on-chain do Bitcoin em uma única página, eliminando a necessidade de manter várias abas abertas.

### Problema que Resolve

Traders e investidores de Bitcoin frequentemente precisam monitorar diversos indicadores simultaneamente, resultando em:

- 10+ abas abertas no navegador
- Navegação constante entre diferentes sites
- Dificuldade em correlacionar dados

**Solução:** Dashboard único com todos os indicadores principais em tempo real.

---

## 🎯 Indicadores Disponíveis

### V1 (Gratuitos)

- ✅ **Fear & Greed Index** - Sentimento do mercado (0-100)
- ✅ **Mayer Multiple** - Preço vs MA 200 dias
- ✅ **Rainbow Chart** - Regressão logarítmica com bandas coloridas
- ✅ **Stock-to-Flow** - Modelo de escassez

### V2+ (Planejados - Requerem APIs pagas)

- ⏳ **MVRV-Z Score** - Market Value to Realized Value
- ⏳ **NUPL** - Net Unrealized Profit/Loss
- ⏳ **Puell Multiple** - Receita dos mineradores
- ⏳ **VDD** - Value Days Destroyed

---

## 🛠️ Stack Tecnológica

- **Frontend:** Next.js 14 (App Router)
- **Linguagem:** TypeScript
- **Gráficos:** Recharts
- **Styling:** Tailwind CSS
- **Deploy:** Vercel
- **APIs:** Alternative.me, CoinGecko, Blockchain.info

---

## 🚀 Quick Start

### Pré-requisitos

```bash
Node.js 18+
npm ou yarn
```

### Instalação

```bash
# Clone o repositório
git clone https://github.com/jemluz/btc-indicators.git
cd btc-indicators

# Instale dependências
npm install

# Execute em desenvolvimento
npm run dev

# Abra http://localhost:3000
```

---

## 📂 Estrutura do Projeto

```
btc-indicators/
├── app/
│   ├── api/
│   │   ├── fear-greed/route.ts
│   │   ├── mayer-multiple/route.ts
│   │   ├── rainbow/route.ts
│   │   └── stock-to-flow/route.ts
│   ├── page.tsx
│   └── layout.tsx
├── components/
│   ├── FearGreedChart.tsx
│   ├── MayerMultipleChart.tsx
│   ├── RainbowChart.tsx
│   └── StockToFlowChart.tsx
├── lib/
│   └── utils.ts
├── docs/
│   ├── README.md
│   ├── ROADMAP.md
│   ├── API_REFERENCE.md
│   └── LEGAL.md
└── public/
```

---

## 📊 Como Funciona

### Arquitetura

```
┌─────────────────┐
│   Frontend      │
│   (Next.js)     │ ← Usuário acessa
└────────┬────────┘
         │
         │ fetch('/api/...')
         ▼
┌─────────────────┐
│   API Routes    │
│   (Next.js)     │ ← Processa e calcula
└────────┬────────┘
         │
         │ fetch data
         ▼
┌─────────────────┐
│  External APIs  │
│  CoinGecko, etc │ ← Dados externos
└─────────────────┘
```

### Fluxo de Dados

1. **Frontend** requisita dados via `/api/[indicator]`
2. **API Route** busca dados de fontes externas
3. **Cálculos** são feitos server-side
4. **JSON estruturado** é retornado ao frontend
5. **Componente** renderiza gráfico

---

## 🔄 Atualização de Dados

- **Intervalo:** A cada 10 minutos (configurável)
- **Método:** Polling via `setInterval`
- **Cache:** Implementado nas API routes (10min)

---

## 🌐 Deploy

### Vercel (Recomendado)

```bash
# 1. Push para GitHub
git push origin main

# 2. Importar no Vercel
# 3. Deploy automático!
```

### Variáveis de Ambiente

Nenhuma API key necessária na V1 (todas as APIs são públicas).

---

## 📈 Roadmap

Veja [ROADMAP.md](./ROADMAP.md) para detalhes completos.

**V1 - Spike de Backend** ✅ (Atual)

- API routes funcionando
- Validação de dados

**V2 - Dashboard Visual** 🔄 (Em progresso)

- Componentes de gráficos
- Interface completa
- Auto-refresh

**V3 - Melhorias** ⏳ (Futuro)

- Cache inteligente
- Mais indicadores
- Preferências de usuário

---

## 🤝 Contribuindo

Pull requests são bem-vindos! Para mudanças maiores, abra uma issue primeiro.

1. Fork o projeto
2. Crie sua feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

---

## ⚖️ Legal

- ✅ Dados de APIs públicas e gratuitas
- ✅ Cálculos baseados em fórmulas de domínio público
- ✅ Atribuição adequada às fontes de dados
- ❌ Não é aconselhamento financeiro

Veja [LEGAL.md](./LEGAL.md) para detalhes sobre copyright e ToS.

---

## 📝 Licença

MIT License - use livremente!

---

## 👤 Autor

**jemluz**

- GitHub: [@jemluz](https://github.com/jemluz)

---

## 🙏 Agradecimentos

- Alternative.me (Fear & Greed API)
- CoinGecko (Price data)
- Blockchain.info (Blockchain data)
- PlanB (Stock-to-Flow model)
- Comunidade Bitcoin

---

## ⚠️ Disclaimer

**Este projeto é apenas para fins educacionais e informativos.**

- ❌ NÃO é aconselhamento financeiro
- ❌ NÃO garante precisão dos dados
- ❌ NÃO deve ser usado como única fonte para decisões de investimento
- ✅ DYOR (Do Your Own Research)

---

**Made with ❤️ for the Bitcoin community**
