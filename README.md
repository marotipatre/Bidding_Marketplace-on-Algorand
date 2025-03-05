# bidding_market

Welcome to your new AlgoKit project!

This is your workspace root. A `workspace` in AlgoKit is an orchestrated collection of standalone projects (backends, smart contracts, frontend apps and etc).

By default, `projects_root_path` parameter is set to `projects`. Which instructs AlgoKit CLI to create a new directory under `projects` directory when new project is instantiated via `algokit init` at the root of the workspace.

## Getting Started

To get started refer to `README.md` files in respective sub-projects in the `projects` directory.

To learn more about algokit, visit [documentation](https://github.com/algorandfoundation/algokit-cli/blob/main/docs/algokit.md).

### GitHub Codespaces

To get started execute:

1. `algokit generate devcontainer` - invoking this command from the root of this repository will create a `devcontainer.json` file with all the configuration needed to run this project in a GitHub codespace. [Run the repository inside a codespace](https://docs.github.com/en/codespaces/getting-started/quickstart) to get started.
2. `algokit init` - invoke this command inside a github codespace to launch an interactive wizard to guide you through the process of creating a new AlgoKit project

Powered by [Copier templates](https://copier.readthedocs.io/en/stable/).


Below is a professional and well-structured `README.md` for your Algorand smart contract project. It explains the purpose of the contract, how it works, and provides instructions for setting up and using the contract. You can place this `README.md` in the root of your project or in the appropriate subdirectory.

---

# Algorand Bidding Marketplace Contract

Welcome to the **Algorand Bidding Marketplace Contract**! This project is a smart contract built on the Algorand blockchain using the `algopy` framework. It enables a decentralized marketplace where users can bid on digital assets, and the asset owner can accept or reject bids. The contract ensures secure and transparent transactions by leveraging Algorand's blockchain capabilities.

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [How It Works](#how-it-works)
4. [Contract Details](#contract-details)
5. [Contributing](#contributing)
6. [License](#license)

---

## Overview

This smart contract facilitates a decentralized marketplace for digital assets on the Algorand blockchain. The marketplace allows:

- **Asset Owners** to list their digital assets with a floor price.
- **Bidders** to place bids on the listed assets.
- **Asset Owners** to accept or reject bids.
- Secure escrow of funds until the bid is accepted or rejected.

The contract ensures that all transactions are transparent, secure, and trustless.

---

## Features

- **Floor Price**: The asset owner sets a minimum price (floor price) for the asset.
- **Bidding Mechanism**: Users can place bids higher than the current highest bid and the floor price.
- **Escrow**: Funds from bidders are held in escrow until the asset owner accepts or rejects the bid.
- **Refunds**: If a higher bid is placed, the previous highest bidder is refunded automatically.
- **Asset Transfer**: Upon bid acceptance, the asset is transferred to the highest bidder, and funds are transferred to the asset owner.
- **Contract Management**: The asset owner can update the floor price or delete the marketplace to reclaim assets and funds.

---

## How It Works

1. **Market Creation**: The asset owner creates the marketplace by specifying the asset ID and the floor price.
2. **Opt-In**: The asset owner opts into the asset to be sold.
3. **Bidding**: Users place bids by sending payments to the contract. The contract ensures that bids are higher than the current highest bid and the floor price.
4. **Bid Acceptance/Rejection**: The asset owner can accept the highest bid, transferring the asset to the bidder and funds to themselves, or reject the bid, refunding the bidder.
5. **Market Deletion**: The asset owner can delete the marketplace, reclaiming any unsold assets and remaining funds.

---

## Getting Started

### Prerequisites

- [AlgoKit](https://github.com/algorandfoundation/algokit-cli)
- Python 3.10 or higher
- Algorand Testnet or Mainnet account with sufficient ALGO for transactions

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/bidding_market.git
   cd bidding_market
   ```


## Contract Details

### Methods

- **`create_application`**: Initializes the marketplace with the asset ID and floor price.
- **`set_floor_price`**: Updates the floor price (only callable by the creator).
- **`opt_in_to_asset`**: Opts the contract into the asset to be sold.
- **`place_bid`**: Allows users to place bids.
- **`accept_bid`**: Accepts the highest bid and transfers the asset and funds.
- **`reject_bid`**: Rejects the highest bid and refunds the bidder.
- **`delete_application`**: Deletes the marketplace and reclaims assets and funds.

### State Variables

- **`assetid`**: The ID of the asset being sold.
- **`floorprice`**: The minimum price for the asset.
- **`highest_bid`**: The current highest bid.
- **`highest_bidder`**: The address of the current highest bidder.

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature`.
3. Commit your changes: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature/your-feature`.
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
