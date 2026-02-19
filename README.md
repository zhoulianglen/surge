# Surge Rule Set

个人维护的 [Surge](https://nssurge.com) 规则集，主要用于 Crypto / Web3 相关网站的代理分流。

## 目录结构

```
├── Rule/
│   ├── CEX.list      # 中心化交易所（Binance, OKX, Bybit, Bitget 等）
│   ├── Web3.list     # Web3 / DeFi 相关站点
│   └── Bus.list      # 其他
└── Proxy/
    └── zhanweifu.list # 代理节点模板
```

## 规则分类

### CEX.list

覆盖主流中心化交易所域名：

- Binance / OKX / Bybit / Bitget
- MEXC / Gate.io / KuCoin / CoinW
- Bitstamp / BitPanda / Bithumb 等

### Web3.list

按功能分类的 Web3 站点：

| 分类 | 包含项目 |
|------|---------|
| 钱包 | MetaMask, WalletConnect, Ledger, Trezor, OneKey, Keplr 等 |
| K 线 | CoinMarketCap, CoinGecko, DexScreener, TradingView, Birdeye 等 |
| DEX / Swap | Uniswap, PancakeSwap, DYDX, Curve, SushiSwap 等 |
| 跨链桥 | Bungee, Jumper, Stargate, XY Finance |
| 借贷协议 | Aave, Kamino, Benqi |
| 区块浏览器 | Etherscan, Arbiscan, BscScan, Polygonscan |
| RPC / 工具 | Alchemy, Ankr, Infura, Chainlist |
| NFT | OpenSea, Blur, Element |

## 使用方式

在 Surge 配置文件中通过 `RULE-SET` 引用远程规则列表：

```ini
[Rule]
RULE-SET,https://raw.githubusercontent.com/zhoulianglen/surge/master/Rule/CEX.list,Proxy
RULE-SET,https://raw.githubusercontent.com/zhoulianglen/surge/master/Rule/Web3.list,Proxy
RULE-SET,https://raw.githubusercontent.com/zhoulianglen/surge/master/Rule/Bus.list,Proxy
```

将 `Proxy` 替换为你实际使用的策略组名称。
