# Fluid-Protocol-Research


Aims to be a liquidity layer for DeFi.
Designed to address liquidity fragmentation and enhance capital efficiency within DeFi.

Features include:
	- liquidity layer
	- automated limits  (dynamically adjust the debt/collateral ceiling when funds are nearing limits)
	- lending and vault protocols. 

Advantages of Fluid Protocol

	Interest- free Liquidity

	Fixed Minimum Collateral Ratio (135%)

	Partial Liquidations

	Multiple Collateral Types
		FUEL, ETH, wstETH, EzETH, weETH, RsETH

Fluid offers a dynamic liquidity platform where users can maximize their investments through simple earnings, improved borrowing capacities, and enhanced security features.

It optimizes capital efficiency and streamlines DeFi through a unified liquidity layer supporting lending, borrowing, and trading.

q:but what is unified liquidity layer? ( think of an imaginary layer that is sitting at bottom of each protocol as source of liquidity for borrowing and trading )

Fluid also cooperated with Barter, becoming a key source of liquidity and accounting for more than 10% of the total DEX trading volume on Ethereum

## Architecture
![architecture_fluid](https://github.com/user-attachments/assets/8595f8cf-07f0-421d-9ce3-ede65bd55d55)



automated limits encourage organic borrow activity , but limiting any sudden whale movements that could point to code vulnerabilities or economic exploits.
q:what are the risks for whales here ?

Fluid has two important protocols inside it .

1. Lend
The Lend protocol within Fluid is designed to facilitate lending activities via direct access to the Liquidity layer.

2. Vault
The Vault protocol is targeted towards borrowers and offers a range of benefits over existing borrowing protocols including
	- better capital efficiency 
	- higher loan-to-value (LTV) or lower CR 135% minimum as of now
	- better rates
	- lower liquidation penalty ( q: so liquidators are less incentivized as compared to other protocols .. leading to less activity and bad debt ? )
	- smart debt & collateral features.


No Fees for using fluid as of now . q:how it generates revenue then ? sustainable ? what if company runs out of funds to still keep building



Recent audits:

[Immuenfi (14 November 2024 - 12 December 2024)](https://reports.immunefi.com/fluid-protocol) - 4 criticals + 1 medium

