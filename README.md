# YieldGuard

A Binance Agent OS skill that sits in front of Binance Agentic Wallet.

The agent proposes one on-chain DeFi action.
The skill decides BLOCK or CONFIRM.
No fake transaction hash.

## Why

On-chain actions are easy to type and hard to undo.
This skill blocks the wrong chain, the wrong farm, an oversized amount, or an empty wallet.
## How to use it

1. claude.ai → Customize → Connectors
2. Add custom connector
3. URL: https://agent.binance.com/mcp/agentic
4. Connect and authorize Binance
5. Customize → Skills → Add skill
6. Copy `skills/yield-guard/SKILL.md` from this repo and paste it into Claude
7. New chat, then ask:

Use YieldGuard. Show balances, daily limit, and DeFi positions.

Deposit 500 USDT to RandomFarm on Solana

Deposit 25 USDT to Venus on BSC

Type CONFIRM only if you want a real write.
If you do not confirm, the answer must be NOT SENT.
## Real test result

Spot USDT: 0.00
Spot BNB: 0.00
DeFi positions: none found

RandomFarm / Solana / $500 → BLOCKED
Venus / BSC / $25 → rules PASS, balance 0.00 → BLOCKED, NOT SENT

## Rules

- BSC only
- USDT, USDC, BNB only
- Venus or PancakeSwap only
- Max $50 per action
- Empty wallet or unknown farm = BLOCKED

## Disclaimer

Not financial advice.
Nothing is sent unless you type CONFIRM and the wallet accepts.
