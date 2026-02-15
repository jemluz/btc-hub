# ⚖️ Questões Legais - Copyright & ToS

Documentação sobre aspectos legais, copyright, termos de serviço e uso ético de dados.

---

## 📋 Resumo Executivo

### ✅ O Que É Legal

- Usar APIs públicas gratuitas com atribuição adequada
- Calcular indicadores usando fórmulas de domínio público
- Exibir dados factuais agregados de múltiplas fontes
- Uso pessoal e educacional do projeto
- Compartilhar código open-source (MIT License)

### ❌ O Que NÃO É Permitido

- Copiar gráficos (imagens) de outros sites
- Violar rate limits das APIs
- Revender dados de APIs pagas
- Remover atribuições de fontes
- Usar para manipulação de mercado

---

## 🌐 APIs Utilizadas - Status Legal

### 1. Alternative.me (Fear & Greed Index)

**URL:** https://api.alternative.me/fng/

**Termos de Uso:**

- ✅ API pública sem autenticação
- ✅ Sem ToS restritivo documentado
- ✅ Amplamente usada pela comunidade

**Obrigações:**

- ✅ Adicionar atribuição: "Data from Alternative.me"
- ✅ Não sobrecarregar com requests excessivos
- ✅ Respeitar disponibilidade do serviço

**Risco Legal:** 🟢 Baixo

---

### 2. CoinGecko API (Preços e Market Data)

**URL:** https://www.coingecko.com/en/api

**Termos de Uso:** https://www.coingecko.com/en/api_terms

**Free Tier:**

- ✅ 10-50 calls/minuto
- ⚠️ Não redistribuir dados comercialmente em larga escala
- ✅ Uso pessoal/educacional permitido
- ✅ Projetos open-source permitidos

**Obrigações:**

- ✅ Respeitar rate limits (10-50 calls/min)
- ✅ Adicionar atribuição: "Powered by CoinGecko API"
- ✅ Implementar cache adequado
- ❌ Não criar clone comercial do CoinGecko

**Nosso Uso:**

- ✅ Cache de 10 minutos implementado
- ✅ Máximo 4-6 calls/hora em uso normal
- ✅ Atribuição presente em todos os componentes

**Risco Legal:** 🟢 Baixo (cumprimos todos os requisitos)

---

### 3. Blockchain.info (Blockchain Data)

**URL:** https://blockchain.info/q/

**Termos de Uso:**

- ✅ APIs públicas sem autenticação
- ✅ Dados on-chain são públicos por natureza
- ✅ Sem rate limit oficial documentado

**Obrigações:**

- ✅ Uso ético e responsável
- ✅ Não sobrecarregar servidores

**Nosso Uso:**

- ✅ Cache de 30 minutos implementado
- ✅ Apenas 2 endpoints usados (block height, supply)

**Risco Legal:** 🟢 Baixo

---

## 📐 Fórmulas e Cálculos

### Domínio Público

As seguintes fórmulas são de **domínio público** e podem ser usadas livremente:

#### Mayer Multiple

```
Fórmula: Preço BTC / MA(200)
Criador: Trace Mayer
Status: Domínio público
Fonte: https://mayermultiple.info/
```

#### Rainbow Chart

```
Fórmula: Regressão logarítmica sobre preço vs tempo
Criador: Comunidade Bitcoin (BitcoinTalk forums)
Status: Domínio público
Fonte: https://www.blockchaincenter.net/bitcoin-rainbow-chart/
```

#### Stock-to-Flow

```
Fórmula: S2F = Supply / Annual Flow
         Model Price = 0.4 * S2F^3
Criador: PlanB (@100trillionUSD)
Status: Publicado em Medium, uso livre citando fonte
Fonte: https://medium.com/@100trillionUSD
```

**Nota:** Fórmulas matemáticas não são patenteáveis. Podemos calcular livremente desde que citemos a fonte.

---

## 🚫 Scraping Web - Quando É Permitido?

### Legalidade do Web Scraping

**Contexto Legal (EUA - hiQ Labs vs LinkedIn, 2019):**

- ✅ Scraping de dados **públicos** é geralmente legal
- ❌ Violar autenticação/paywalls é ilegal
- ❌ Violar explicitamente ToS pode gerar consequências
- ⚖️ Zona cinza: depende de jurisdição e caso

### Nosso Caso

**Não estamos fazendo scraping no projeto atual (V1/V2).**

Todos os dados vêm de:

- APIs públicas documentadas
- Cálculos próprios baseados em dados públicos

### Se Quiséssemos Fazer Scraping (V3+)

#### Sites que Exibem Indicadores On-Chain:

**Lookintobitcoin.com:**

- Exibe: MVRV, NUPL, Puell Multiple, etc.
- ToS: Não menciona scraping explicitamente
- Risco: 🟨 Médio - podem bloquear IP
- **Alternativa recomendada:** Pedir permissão ao criador

**Glassnode.com (versão gratuita):**

- ToS: **Proíbe explicitamente** scraping
- Risco: 🔴 Alto - violação clara de ToS
- **Não fazer**

#### Scraping Ético - Boas Práticas:

```typescript
// ✅ BOM: Scraping responsável
const SCRAPE_INTERVAL = 3600000; // 1 hora
const USER_AGENT =
  "BTC-Indicators-Dashboard/1.0 (+https://github.com/jemluz/btc-indicators)";

// Respeitar robots.txt
// Implementar exponential backoff em erros
// Cachear agressivamente
```

```typescript
// ❌ MAU: Scraping abusivo
setInterval(() => scrape(), 1000); // A cada segundo
// Sem User-Agent identificável
// Sem respeitar robots.txt
```

### Recomendação

**Para indicadores pagos (MVRV, NUPL, etc.):**

1. **Opção A - Pedir Permissão** (Recomendado)
   - Contatar criadores no Twitter/email
   - Explicar projeto open-source educacional
   - Muitos são receptivos à comunidade

2. **Opção B - Pagar APIs**
   - Glassnode: $29-800/mês
   - CryptoQuant: $49-299/mês
   - Legal, confiável, suportado

3. **Opção C - Calcular Você Mesmo**
   - Alguns indicadores podem ser calculados com dados blockchain públicos
   - Mais complexo, mas 100% legal
   - Ex: NUPL requer UTXO set completo

---

## 📊 Dados Factuais vs Apresentação

### O Que Tem Copyright

❌ **Design visual de gráficos** (cores, layout, estilo)
❌ **Código proprietário** de outros sites
❌ **Bases de dados proprietárias**
❌ **Marcas registradas** (logos, nomes)

### O Que NÃO Tem Copyright

✅ **Dados factuais** (preços, números, estatísticas)
✅ **Fórmulas matemáticas** (não são patenteáveis)
✅ **Informações de blockchain** (públicas por natureza)
✅ **Ideias e conceitos** (apenas implementação tem copyright)

**Exemplo Prático:**

```
❌ Copiar imagem do gráfico Rainbow de outro site
✅ Calcular Rainbow usando a mesma fórmula e dados públicos
✅ Criar nossa própria visualização com design diferente
```

---

## 🛡️ Proteções Legais Implementadas

### 1. Disclaimers

```html
<!-- Footer de todas as páginas -->
<footer>
  <p>
    This site aggregates publicly available Bitcoin data for educational
    purposes. Data sources: Alternative.me, CoinGecko, Blockchain.info.
  </p>
  <p>
    <strong>Not financial advice. DYOR (Do Your Own Research).</strong>
  </p>
  <p>This project is open-source and not affiliated with any data provider.</p>
</footer>
```

### 2. Atribuições

Cada componente de gráfico inclui:

```typescript
<div className="text-xs text-gray-500 mt-4">
  Data source: Alternative.me
</div>
```

### 3. Rate Limiting & Cache

```typescript
// Respeitar APIs externas
const CACHE_DURATION = 10 * 60 * 1000; // 10 minutos
// Evita chamadas excessivas
```

### 4. Licença Open-Source

```
MIT License

Copyright (c) 2026 jemluz

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

**Benefícios da MIT:**

- ✅ Uso livre (pessoal e comercial)
- ✅ Modificação permitida
- ✅ Distribuição permitida
- ❌ Sem garantias (liability protection)

---

## 💼 Uso Comercial

### Projeto Atual (Gratuito)

**Permitido:**

- ✅ Hospedar gratuitamente (Vercel free tier)
- ✅ Open-source no GitHub
- ✅ Uso educacional e pessoal
- ✅ Portfolio/currículo

**Não Permitido (sem licenças adequadas):**

- ❌ Cobrar assinatura por acesso
- ❌ Vender dados agregados
- ❌ Ads pesadas sem consentimento de APIs

### Se Quiser Monetizar (Futuro)

**Opções Legais:**

1. **Freemium Model:**
   - Indicadores gratuitos: grátis para todos
   - Indicadores premium: pagar APIs e cobrar usuários
   - Transparente sobre custos

2. **Doações:**
   - Bitcoin Lightning tips
   - GitHub Sponsors
   - Patreon
   - 100% legal, sem problemas

3. **Ads Éticos:**
   - Google AdSense (com moderação)
   - Verificar se CoinGecko ToS permite
   - Adicionar disclaimer

4. **Consultoria/Custom:**
   - Oferecer versões customizadas
   - Integração para empresas
   - White-label solutions

---

## ⚠️ Riscos e Mitigações

### Risco: Mudança de ToS das APIs

**Cenário:** CoinGecko muda ToS proibindo uso em dashboards

**Mitigação:**

- ✅ Arquitetura modular (fácil trocar provider)
- ✅ Múltiplas fontes de dados (não depender de 1 única)
- ✅ Possibilidade de migrar para APIs alternativas

### Risco: Rate Limit / IP Ban

**Cenário:** Muitos usuários simultâneos excedem rate limits

**Mitigação:**

- ✅ Cache agressivo server-side
- ✅ Considerar Redis/Vercel KV (V3)
- ✅ Implementar nossa própria API rate limiting
- ✅ Upgrade para tier pago se necessário

### Risco: DMCA Takedown

**Cenário:** Alguém alega copyright infringement

**Mitigação:**

- ✅ Documentação clara de fontes (este arquivo)
- ✅ Atribuições visíveis
- ✅ Apenas usar dados públicos e cálculos próprios
- ✅ Responder rapidamente e colaborar

### Risco: Responsabilidade Legal

**Cenário:** Usuário perde dinheiro e culpa o dashboard

**Mitigação:**

- ✅ **Disclaimer claro:** "Not financial advice"
- ✅ **Sem recomendações:** Apenas exibir dados
- ✅ **Open-source:** Código auditável
- ✅ **MIT License:** Liability protection

---

## 📞 Contatos Úteis

### Para Pedir Permissão

**Criadores de Indicadores:**

- **Will Clemente** (@WClementeThIII) - Puell Multiple, outros
- **Philip Swift** (lookintobitcoin.com) - MVRV, NUPL, etc.
- **Willy Woo** (@woonomic) - NVT, VDD, outros

**Como Contatar:**

- Twitter DM (mais rápido)
- Email (verificar em perfis)
- Mencionar: projeto open-source educacional

**Template de Mensagem:**

```
Hi [Name],

I'm building an open-source Bitcoin indicators dashboard
(https://github.com/jemluz/btc-indicators) to help the
community monitor on-chain metrics in one place.

Would you be open to me including [Indicator Name] in
the project? Full attribution will be given, and the
project is 100% free and educational.

Thanks for your work!
```

---

## 📚 Referências Legais

**Casos Relevantes:**

- hiQ Labs, Inc. v. LinkedIn Corp. (2019) - Scraping de dados públicos
- Oracle v. Google (2021) - APIs e fair use

**Recursos:**

- [EFF - Legal Guide to Web Scraping](https://www.eff.org/)
- [GitHub ToS](https://docs.github.com/en/site-policy/github-terms/github-terms-of-service)
- [Vercel ToS](https://vercel.com/legal/terms)

---

## ✅ Checklist de Compliance

```
□ Atribuições visíveis em todos os gráficos
□ Disclaimer "Not financial advice" no footer
□ Rate limits respeitados (cache implementado)
□ Licença MIT no repositório
□ README com créditos às fontes
□ Código open-source auditável
□ Sem violação de autenticação/paywalls
□ User-Agent identificável em requests
□ Respeitar robots.txt (se aplicável)
□ Documentação de fontes de dados (este arquivo)
```

---

## 🎓 Conclusão

**Este projeto é 100% legal porque:**

1. ✅ Usa apenas APIs públicas documentadas
2. ✅ Calcula indicadores usando fórmulas de domínio público
3. ✅ Fornece atribuição adequada às fontes
4. ✅ Respeita rate limits e ToS
5. ✅ Não copia código ou design proprietário
6. ✅ É open-source e educacional
7. ✅ Inclui disclaimers apropriados

**Se surgir dúvida:** Sempre opte pelo caminho mais conservador e ético.

---

**Última atualização:** 2026-02-12  
**Disclaimer:** Este documento não constitui aconselhamento jurídico. Consulte um advogado para casos específicos.
