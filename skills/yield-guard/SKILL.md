---
name: yield-guard
description: Use before any on-chain DeFi write via Binance Agentic Wallet. Blocks the wrong chain, farm, size, or empty wallet.
---

# YieldGuard

Propose one action. Check rules. Wait for CONFIRM. Fail closed.
## Hard rules

- Chain: BSC only
- Tokens: USDT, USDC, BNB only
- Protocols: Venus or PancakeSwap only
- Actions: deposit, redeem, add_liquidity, remove_liquidity, claim, swap
- Max: $50 per action
- Unknown farm, wrong chain, or empty wallet = BLOCKED
- Never invent a transaction hash
- Never give investment advice
- ## Workflow

1. Read balances, daily limit, DeFi positions
2. Propose one action
3. Print table: Field | Proposed | Rule | PASS or BLOCK
4. Say BLOCKED or APPROVE_WITH_CONFIRM
5. Wait until the user types CONFIRM
6. If not sent, write NOT SENT

## Demo prompts

Use YieldGuard. Show balances, daily limit, and DeFi positions.

Deposit 500 USDT to RandomFarm on Solana

Deposit 25 USDT to Venus on BSC
