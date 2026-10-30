# DexPaprika MCP - Solana Only

> Phiên bản tập trung **chỉ cho Solana** của [DexPaprika MCP](https://github.com/coinpaprika/dexpaprika-mcp).

Repo này dành cho các AI agent (Claude, Cursor, Grok...) chuyên phân tích token, pool, DEX trên **Solana** (Raydium, Pump.fun, Orca, Meteora...).

## Cách dùng nhanh

### 1. Cài đặt MCP (giống bản gốc)

```bash
npx dexpaprika-mcp@latest
```

Hoặc cấu hình Claude Desktop / Cursor:

```json
{
  "mcpServers": {
    "dexpaprika": {
      "command": "npx",
      "args": ["dexpaprika-mcp@latest"]
    }
  }
}
```

### 2. Luôn chỉ dùng network = "solana"

Khi gọi tool, **bắt buộc** truyền `network: "solana"` (hoặc `"sol"`).

### Tools quan trọng nhất cho Solana

| Tool | Mục đích |
|------|----------|
| `getTokenDetails` | Lấy thông tin chi tiết token (giá, volume, liquidity, holders...) |
| `getTokenPools` | Tìm tất cả pool chứa token đó |
| `getNetworkPools` | Top pool trên Solana theo volume / liquidity |
| `getPoolDetails` | Chi tiết 1 pool (TVL, volume, fee...) |
| `getPoolOHLCV` | Dữ liệu nến OHLCV của pool |
| `getPoolTransactions` | Giao dịch gần đây của pool |
| `getTopTokens` | Top token Solana theo volume / liquidity / price change |
| `search` | Tìm token / pool / DEX bằng tên hoặc address |
| `getTokenMultiPrices` | Lấy giá nhiều token cùng lúc |

### Ví dụ prompt gợi ý cho AI

- "Phân tích token này trên Solana: [CA]. Lấy price, volume 24h, top pools, và liquidity."
- "Tìm top 10 pool volume cao nhất trên Solana hôm nay."
- "So sánh volume giữa Raydium và Meteora trên Solana."
- "Lấy OHLCV 24h của pool SOL/USDC trên Raydium."
- "Kiểm tra token [CA] có bao nhiêu pool, pool nào volume lớn nhất."

### Lưu ý quan trọng

- Bản MCP gốc hỗ trợ 36 chain. Repo này **chỉ hướng dẫn và khuyến khích dùng Solana**.
- Free tier không cần API key vẫn dùng được tốt.
- Muốn rate limit cao hơn → lấy free key tại [console.dexpaprika.com](https://console.dexpaprika.com)

### Link gốc

- Repo gốc đầy đủ: [coinpaprika/dexpaprika-mcp](https://github.com/coinpaprika/dexpaprika-mcp)
- Docs chính thức: [docs.dexpaprika.com](https://docs.dexpaprika.com)
- Hosted MCP (không cần cài): `https://mcp.dexpaprika.com/streamable-http`

---

**Dành cho AI agent:** Khi nhận được repo này, hãy ưu tiên dùng `network: "solana"` trong mọi tool call liên quan đến token/pool.
