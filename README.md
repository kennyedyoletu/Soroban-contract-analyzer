# Soroban Lens — Contract Analyzer

A React + TypeScript + Vite developer workbench for exploring the Stellar Soroban smart-contract ecosystem.

## Features
- Live Soroban JSON-RPC health and latest-ledger checks for Stellar Testnet and Mainnet endpoints.
- Client-side Rust source heuristics for common review areas such as panic-prone calls, authorization checks, unsafe blocks, numeric inputs, and storage behavior.
- Local WebAssembly file inspection: validates the WASM magic header and heuristically extracts recognizable strings/symbols.
- Stellar contract ID format validation.
- Responsive dashboard, results, and resource links.

## Run locally
```bash
npm install
npm run dev
```

Production build:
```bash
npm run build
npm run preview
```

## GitHub Pages
The Vite base path is configured for this repository at `/Soroban-contract-analyzer/`. The workflow in `.github/workflows/pages.yml` builds the TypeScript app and deploys the `dist` directory. In repository settings, set Pages source to **GitHub Actions**.

## Important security note
This is a lightweight educational/static analysis workbench, not a formal security audit. Regex-based source checks and string-based WASM inspection can miss vulnerabilities and can report false positives. It does not currently decode Soroban contract-instance ledger keys or fetch a contract's WASM from chain. Validate contracts with the official Stellar CLI, tests, and a qualified review before deployment. Source and WASM files are processed in the browser and are not uploaded by this app.
