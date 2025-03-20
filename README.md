# Instadapp Fluid (FLUID) Research
![image](https://github.com/user-attachments/assets/4faeec72-fb78-4a35-a091-4a6163135930)

## 1. Introduction  
Instadapp Fluid (FLUID) is a suite of smart contracts designed to streamline advanced DeFi operations within the Instadapp ecosystem. By unifying lending, vault management, and decentralized trading under a single liquidity layer, Fluid optimizes capital usage, reduces transaction costs, and enhances overall efficiency.

---

## 2. System Overview  
At the heart of Instadapp Fluid is a **unified liquidity layer** that serves multiple protocols:
- **Lending Protocol** – Users supply liquidity and earn interest through fTokens.
- **Vault Protocol** – Users borrow against collateral (e.g., ETH) with high loan-to-value (LTV) ratios.
- **Additional Modules** – Includes flashloans, stETH, and a DEX module for trading.

![SystemOverview-1](https://github.com/user-attachments/assets/074c2afc-77bd-4de6-9267-dae8e45c80dc)

source : https://twitter.com/0xfluid/status/1820485781888323689

---

## 3. Architecture  
Fluid’s architecture revolves around a single liquidity framework that connects its core components. This diagram (based on the provided illustration) outlines the system:

```
              +----------------------+
              |  Additional Modules  |
              |  (Flashloan, stETH,  |
              |       DEX, etc.)     |
              +-----------^----------+
                          |
                          v
        +---------+    Unified       +---------+
        | Lending | <- Liquidity ->  |  Vault  |
        |Protocol |    Layer         |Protocol |
        +---------+                  +---------+
```

*The unified liquidity layer feeds into every module, ensuring that assets are used efficiently across lending, borrowing, and trading activities.*

---

## 4. Essential Concepts  
- **Liquidity:** Funds available for lending, borrowing, or trading.  
- **Vault:** A secure contract that manages collateral and debt positions.  
- **Flashloan:** A short-term loan that is borrowed and repaid within a single transaction.  
- **fTokens:** Tokens issued when depositing assets into the liquidity layer, representing a user’s stake and accruing interest over time.  
- **Oracle:** Provides real-time price data for accurate asset valuation.  
- **Resolver:** Modules that help execute specific tasks (e.g., monitoring vault positions or managing liquidity actions).

---

## 5. Features & Mechanics

### Unified Liquidity Layer  
Fluid consolidates capital into one pool that supports multiple functionalities—lending, vault operations, and trading. This approach minimizes liquidity fragmentation and maximizes capital efficiency.

### Advanced Lending & Borrowing  
- **Deposits & fTokens:** Users deposit assets (e.g., USDC) into the liquidity layer and receive fTokens, which accrue interest over time.
- **Collateralized Borrowing:** Users can use assets like ETH as collateral to borrow funds with LTV ratios of up to 95%, enabling high borrowing capacity with controlled liquidation risk.

### Integrated DEX  
The DEX module leverages smart collateral and debt management to facilitate efficient trading, allowing users to optimize positions and earn liquidity provider fees—all within the unified system.

### Smart Debt
Fluid introduces **Smart Debt**, a feature that transforms borrowed assets into productive liquidity within its Decentralized Exchange (DEX) protocol. By allocating debt as trading liquidity, users can earn trading fees, effectively offsetting borrowing costs and enhancing capital efficiency.
**Key Benefits:**
- **Cost Reduction:** Trading fees earned from providing debt as liquidity can offset interest expenses, reducing the overall cost of borrowing.
- **Capital Efficiency:** This mechanism allows users to maximize the utility of their borrowed assets, turning liabilities into income-generating assets.

### Range liquidations
In traditional borrow and lending protocols, liquidation is like a limit order and highly inefficient,where liquidator selects each position to liquidate. Vault protocol revolutionizes liquidations similar to how Uniswap v3 has revolutionized limit orders. Allowing all the positions in range to get liquidated without any increase in gas.

### Advanced Oracles Management
The Vault protocol uses an advanced oracle system that combines Uniswap's TWAP checkpoints with Chainlink's feeds to deliver accurate, real-time pricing data. This multi-source approach ensures asset values are reliably determined and cross-verified, minimizing the risk of price manipulation and enabling timely liquidation of bad debt. As a result, the protocol enhances security and supports higher LTV ratios, providing users with a more transparent and trustworthy borrowing experience.


---

## 6. How Fluid Works

### Liquidity Provision  
Users deposit assets into the unified liquidity layer and receive fTokens. These fTokens represent their stake and accrue interest via the Lending Protocol.

### Collateralized Borrowing  
Depositing assets such as ETH into the Vault Protocol allows users to borrow against their collateral. A specialized Vault Resolver monitors positions to manage risk and prevent sudden liquidations.

### Decentralized Trading & Fee Generation  
The integrated DEX facilitates cost-effective trades by combining smart collateral and debt management. This not only optimizes trade execution but also allows users to earn fees as liquidity providers.

### Governance
- **Governance Token:** INST is the governance token for Fluid, empowering holders to shape the protocol.
- **Key Responsibilities:**
  - Set rate curves, fees, and token configurations within the liquidity layer.
  - Configure protocol settings and establish allowances for interactions with the liquidity layer.
  - Establish automated limits and classify protocols.
  - Set up Vault configurations.
  - Determine reward structures for both the Lending and Vault protocols.
---

## 7. The Vision  
Fluid aspires to build a sustainable, interoperable liquidity infrastructure that drives capital optimization and cost-effective transactions across the DeFi landscape.

---

## 8. Use Cases

### 8.1 Use Cases for the FLUID Token  
- **Transaction Fees:** FLUID tokens are used to pay fees within the ecosystem, ensuring smooth operations.  
- **Governance:** Token holders can participate in governance decisions that shape the protocol’s future.  
- **Incentives & Rewards:** Users earn FLUID tokens by contributing liquidity, staking assets, or engaging in protocol activities.

### 8.2 Use Cases for the Fluid Protocol  
- **Lending & Borrowing:** Provides mechanisms for earning interest through deposits and accessing loans with high LTV ratios.  
- **Decentralized Trading:** Integrated DEX enables efficient trading with minimal slippage and competitive fee structures.

---

## 9. Financial Snapshot (Data from DeFi Llama)  
- **Total Value Locked (TVL):** $793.54M  
- **Market Cap:** $199.51M  
- **Token Price:** $5.05  
- **24h Token Volume:** $1.52M  
- **Borrowed Amount:** $665.75M  
- **Annualized Fees:** $91.8M  
- **Annualized Revenue:** $3.86M

---

## 10. Pros & Cons

### Pros

- **Lower liquidation Penalty**
  Vault protocol users lose only 5% of their collateral ( liquidate what's needed ) as compared to 50% or 100% on other lending/borrow protocols.

- **High Capital Efficiency:**  
  The unified liquidity layer optimizes asset utilization across multiple functions.

- **Advanced Lending & Borrowing:**  
  Attractive features like high LTV ratios and interest-bearing fTokens benefit both lenders and borrowers.

- **Minimal Liquidation Penalties:**
    Fluid's Vault protocol offers exceptionally low liquidation penalties, starting from as low as 0.1%, compared to the typical 5-10%
    in other DeFi platforms. This significantly reduces the financial burden on borrowers during liquidation events, preserving more of their collateral.

- **Seamless Trading Integration:**  
  The integrated DEX allows efficient trading and fee generation within the same ecosystem.

### Cons
- **Automated Limits: Impact on Large Whale Transactions**
  Automated limits are implemented to protect the protocol by dynamically adjusting borrowing and liquidity ceilings. However, they can sometimes throttle large
  transactions causing delays or partial fills—even when market conditions are stable, which may frustrate users with high-volume activity.

- **Reduced Incentives for Liquidators:** The lower liquidation penalties in Fluid may diminish the financial motivation for liquidators, potentially affecting their participation and the overall efficiency of the liquidation process.

- **High LTV Risks:**  
  While high LTV ratios provide borrowing capacity, they also increase exposure to market volatility and the risk of rapid liquidations.

- **Limited Cross-Chain Fragmentation Solution**  
  Although Fluid aims to address chain fragmentation by unifying liquidity, its current implementation is limited to EVM-compatible networks—specifically Ethereum,
  Arbitrum, Base, and Polygon. This focus means that while Fluid streamlines operations within the EVM ecosystem, it doesn't fully resolve fragmentation across non-EVM
  chains. Consequently, users and assets on other blockchains remain excluded, limiting overall interoperability and network diversity.

## 11. Future insights
With the release of uniswap V4 , and the features it gives like hooks and inverse-range-orders , Fluid's founder has shared a vision of going completely oracleless in his [article](https://blog.instadapp.io/oracleless-lending-protocol-on-uniswap-v4/).

## 12. Developer Kickstarter
This section will take deep dives in to the technical side of things to help developers better understand the protocol when they want to integrate with it.

### How Vault Liquidation Mechanism Works

The Vault protocol’s liquidation mechanism is a significant innovation inspired by Uniswap v3, yet it delivers performance improvements up to 100x over traditional systems. When a user opens a position, the protocol assigns it to a specific tick based on the user's debt-to-collateral ratio. This tick is calculated using the formula `ratio = 1.0015^t` (with `t` representing the tick), effectively grouping positions into discrete liquidity buckets. This design consolidates user liquidity and streamlines liquidations, making the process resemble a simple swap operation. To optimize gas efficiency, Fluid employs a custom **TickMath library**—inspired by Uniswap v3—that allows for fast and accurate computation of tick values from given ratios, significantly reducing on-chain computational overhead.

#### Branch and User's Tick Retrieval

When a liquidation event occurs, the protocol must retrieve the user's position in real time. Fluid achieves this through a branch-based mechanism where a "branch" captures the state of liquidation-related variables. The user's pre-liquidation tick serves as the starting point, establishing the debt factor and linking to a branch. As the system iterates through the branch, it identifies the minimum tick (minima) and calculates the total liquidation impact. This approach enables efficient, precise liquidation even for users with multiple past liquidations. As market conditions change—new users entering at higher ticks when prices rise, and higher ticks being liquidated when prices fall—a branch remains active until it reaches the base branch's minima, at which point it merges with the base branch to continue the liquidation process seamlessly.

For a more detailed mathematical explanation, refer to [Fluid's Vault Whitepaper](https://1779047404-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F1GnplQv2H5lIIg0ygng0%2Fuploads%2FXhmUuTV7RpeVnPpadddp%2FVault_Protocol_Whitepaper_.pdf?alt=media&token=1509f8b8-dd0d-4da3-b765-f9188d9fc1dd).

... To be continued
