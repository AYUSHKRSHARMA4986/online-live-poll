# LivePoll

LivePoll is a mini end-to-end Stellar + Soroban dApp: a multi-wallet polling app backed by a deployed Soroban smart contract on Stellar Testnet, with real-time contract event sync, transaction progress feedback, basic caching, and a small automated test suite.

## Level 3 Submission Checklist (fill before submitting)

- Live demo link: https://online-live-poll-liard.vercel.app/
- Test output screenshot (3+ passing tests): ✅ (see below)
- 3+ meaningful commits for Level 3: ✅

## Screenshots

<table width="100%">
  <tr>
    <td align="center" width="50%">
      <strong>🏠 Home Page</strong><br/><br/>
     <img width="1918" height="928" alt="image" src="https://github.com/user-attachments/assets/b4661c6c-e042-48d4-8782-95f38fca39d3" />
    </td>
    <td align="center" width="50%">
      <strong>📝 Create Poll</strong><br/><br/>
   <img width="2848" height="1572" alt="screenshot_visible_2026-04-30_17-14-55" src="https://github.com/user-attachments/assets/1e63b7cd-6ce2-4ef4-a07b-1ecae1771c22" />
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <strong>🗳️ Voting</strong><br/><br/>
   <img width="2848" height="1572" alt="screenshot_visible_2026-04-30_17-17-31" src="https://github.com/user-attachments/assets/b962d4ce-2b4e-42e4-9f8e-29774f78538d" />
    </td>
    <td align="center" width="50%">
      <strong>✅ CI/CD Results</strong><br/><br/>
    <img width="1426" height="830" alt="image" src="https://github.com/user-attachments/assets/ae849647-7b8a-412e-92b8-0fb1532a5c4a" />
    </td>
  </tr>
</table>

## Mobile responsive screenshots

Below is a mobile view screenshot demonstrating the responsive layout on narrow screens. Replace the placeholder with a real phone-sized screenshot captured from the dev tools or a device.

<div align="center">
<img width="389" height="700" alt="2026-04-30_18-25-47" src="https://github.com/user-attachments/assets/23b9e24d-e978-4e81-9db3-dc2976486253" />

</div>

## Verifiable Contract Call

- Deploy tx hash: `9cc1509985bdd889c47f02e0cf5b29b39a4be3c61d363a60e841ffa3b8a10c62`
- Stellar Expert link: https://stellar.expert/explorer/testnet/tx/9cc1509985bdd889c47f02e0cf5b29b39a4be3c61d363a60e841ffa3b8a10c62
- Sample `create_poll` tx hash: `1fd899d9a98e7b262ec7ed357add3d65e7470808d2c715bcb73a94b0b6c69e2d`
- Stellar Expert link: https://stellar.expert/explorer/testnet/tx/1fd899d9a98e7b262ec7ed357add3d65e7470808d2c715bcb73a94b0b6c69e2d

## Live Demo

https://online-live-poll-liard.vercel.app/

## Setup

Run all commands from the project directory.

1. Install dependencies:

```bash
npm install
```

2. Build the Soroban contract:

```bash
npm run contract:build
```

3. Sync the compiled contract WASM into the frontend (used to load the contract spec/ABI at runtime):

```bash
npm run wasm:sync
```

4. Optionally create a local env file:

```powershell
Copy-Item .env.example .env.local
```

5. Start the frontend:

```bash
npm run dev
```

6. Build for production:

```bash
npm run build
```

## Tests

Run the automated tests:

```bash
npm test
```

For submission, include a screenshot of the terminal output showing **3+ tests passing**.

## Environment Variables

```env
VITE_STELLAR_RPC_URL=https://soroban-testnet.stellar.org
VITE_STELLAR_NETWORK_PASSPHRASE=Test SDF Network ; September 2015
VITE_STELLAR_CONTRACT_ID=CBT5GCDC2ZGBVPBOOLHI6DB5UDMX33XBQMOUQAEOJNE3I5I3DCVJKOD4
VITE_STELLAR_READ_ACCOUNT=
VITE_STELLAR_EXPLORER_URL=https://stellar.expert/explorer/testnet
VITE_POLL_CONTRACT_WASM_URL=/contracts/poll_contract.wasm
```

## Testnet Notes

- A connected wallet must be funded on Stellar Testnet before it can send contract transactions
- If a wallet has not been created on Testnet yet, fund it with Friendbot first and then retry
- The app can still read poll data without a funded wallet by using a temporary read account


## Deploy (Vercel / Netlify)

This is a standard Vite build.

- Node.js: use Node `^20.19.0` or `>=22.12.0` (required by Vite 8)
- Build command: `npm run build`
- Output directory: `dist`
- Set the env vars from the section above (at minimum `VITE_STELLAR_CONTRACT_ID` if you deploy a new contract)

