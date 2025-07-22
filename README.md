# 🚀 PeakPay Proxy Reverso

Proxy Nginx para consolidar os 34 serviços PeakPay em uma arquitetura otimizada.

## 📊 Otimização de Recursos

| Antes | Depois | Economia |
|-------|--------|----------|
| 34 serviços | 3 serviços | 91% menos |
| $170-340/mês | $15-30/mês | $155-310/mês |

## 🔧 Como Funciona

### Roteamento por Subdomínio
O proxy identifica o tenant baseado no subdomínio e roteia para o backend consolidado:

```
ed.peakpay.com.br → backend-consolidado (tenant=ed)
johann.peakpay.com.br → backend-consolidado (tenant=johann)
karen.peakpay.com.br → backend-consolidado (tenant=karen)
```

### Subdomínios Suportados
- `ed.peakpay.com.br`
- `johann.peakpay.com.br`
- `isabele.peakpay.com.br`
- `franciele.peakpay.com.br`
- `giga.peakpay.com.br`
- `lala.peakpay.com.br`
- `karen.peakpay.com.br`
- `chaves.peakpay.com.br`
- `brand.peakpay.com.br`
- `angela.peakpay.com.br`
- `rude.peakpay.com.br`
- `pantera.peakpay.com.br`
- `gorila.peakpay.com.br`
- `pinducci.peakpay.com.br`
- `tenente.peakpay.com.br`
- `basa.peakpay.com.br`
- `elite.peakpay.com.br`

## 🏗️ Arquitetura

```
[Subdomínios] → [Nginx Proxy] → [Backend Consolidado]
                              → [Frontend Consolidado]
```

## 🔒 Recursos

- ✅ **CORS configurado**
- ✅ **Headers de segurança**
- ✅ **Compressão gzip**
- ✅ **Health check endpoint**
- ✅ **Logs detalhados por tenant**
- ✅ **Timeouts configurados**

## 🚀 Deploy

Este proxy é deployado automaticamente no Railway quando conectado ao repositório.

## 📝 Logs

Os logs incluem informação do tenant para facilitar debugging:
```
192.168.1.1 - - [22/Jul/2025:21:20:00 +0000] "GET /api/checkout HTTP/1.1" 200 1234 tenant="ed"
```