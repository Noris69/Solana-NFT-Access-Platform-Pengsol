# **PengSol AI Tools**

A **Web3 NFT-gated tools platform** built with **Next.js**, **React**, **TypeScript**, and **Solana**.

The application allows users to connect with **Discord**, connect a **Solana wallet**, verify NFT ownership, check NFT ranking, and unlock access to the platform based on wallet eligibility.

---

# **Project Purpose**

The purpose of this project is to provide a Web3 access platform for the **PengSol** ecosystem.

The application checks whether a connected wallet owns eligible PengSol NFTs or belongs to a list of authorized wallets. Based on this verification, the user can unlock access to the platform.

This project can be used as a foundation for:

- **NFT-gated platforms**
- **Solana wallet dashboards**
- **Minting tools**
- **Web3 community tools**
- **Discord + wallet authentication**
- **NFT ranking systems**
- **Token-gated applications**
- **Solana dApps**
- **Cross-chain Web3 experiments**

---

# **Technologies Used**

## **Frontend**

- **Next.js 12**
- **React 17**
- **TypeScript**
- **Tailwind CSS**
- **DaisyUI**
- **Material UI**
- **Ant Design**
- **Styled Components**
- **React Spring**
- **React Toastify**
- **React Modal**
- **React Datepicker**
- **React Countdown**

## **State Management**

- **Zustand**
- **Jotai**
- **Immer**

## **Authentication**

- **NextAuth**
- **Discord Authentication**

## **Solana / Web3**

- **Solana Web3.js**
- **Solana Wallet Adapter**
- **Solana Wallet Adapter UI**
- **SPL Token**
- **Anchor**
- **Metaplex**
- **NFT token scanning**
- **Wallet-based access control**

## **Additional Blockchain Integrations**

- **Aptos**
- **Aptos Wallet Adapter**
- **Hedera Hashgraph**
- **HashConnect**
- **Blade Web3**
- **Crossmint**

---

# **Main Features**

## **Discord Login**

The app supports Discord authentication using **NextAuth**.

Users must connect their Discord account before accessing the wallet section.

---

## **Solana Wallet Connection**

The app integrates the Solana wallet adapter and displays a wallet connection button.

Users can connect wallets such as:

- **Phantom**
- **Solflare**
- **Backpack**
- **Other Solana-compatible wallets**

---

## **NFT Ownership Verification**

After wallet connection, the app checks the NFTs owned by the connected wallet.

The system can:

- **Fetch wallet token balances**
- **Filter NFTs with positive balance**
- **Compare NFT mint addresses**
- **Determine the best NFT**
- **Calculate NFT rank**
- **Unlock platform access**

---

## **NFT-Gated Access**

The platform grants access if:

- The wallet owns an eligible NFT
- The NFT rank satisfies the platform rules
- The connected wallet is included in the authorized wallet list

When access is granted, the interface displays an unlocked state.

---

## **PengSol NFT Ranking**

The app uses local JSON data files to compare NFT mints and ranks.

Possible data files include:

```text
PengSol_ranks.json
PengSol_king.json
```

These files are used to identify NFT rank and special “king” NFTs.

---

## **Wallet Dashboard**

Once access is granted, the user can see:

- **Unlocked platform status**
- **NFT rank**
- **NFT image**
- **Wallet access state**
- **Disconnect wallet option**

---

## **Minting Tools Foundation**

The current README mentions “minting tools”, so this project can be extended to support:

- **NFT minting**
- **Mint history**
- **Transaction history**
- **Mint settings**
- **Wallet-based mint access**
- **Crossmint integration**

---

# **Project Structure**

```bash
pengtools/
├── public/
│   └── img/
│
├── src/
│   ├── components/
│   │   ├── HomePageConnection/
│   │   ├── HomePageDisplayNFT/
│   │   ├── FormOnBoarding/
│   │   └── helpers/
│   │
│   ├── contexts/
│   │   └── AuthContext/
│   │
│   ├── data/
│   │   ├── PengSol_ranks.json
│   │   └── PengSol_king.json
│   │
│   ├── pages/
│   │   ├── index.tsx
│   │   └── api/
│   │       └── auth/
│   │
│   ├── views/
│   │   └── home/
│   │       └── index.tsx
│   │
│   └── styles/
│
├── package.json
└── README.md
```

---

# **Application Flow**

## **1. Open the Platform**

The user opens the application and reaches the homepage.

The page title is:

```text
PengSol AI Tools
```

---

## **2. Login with Discord**

The user connects their Discord account.

If there is no session, the app displays:

```text
Login with Discord
```

---

## **3. Connect Solana Wallet**

After Discord login, the user connects a Solana wallet using the wallet adapter.

---

## **4. Check NFT Ownership**

The app fetches token balances from the connected wallet and checks eligible NFT mint addresses.

---

## **5. Determine NFT Rank**

The system identifies the best NFT owned by the wallet and calculates the associated rank.

---

## **6. Unlock Platform**

If the user is eligible, the platform displays an unlocked status and grants access.

---

# **Installation**

## **1. Clone the Repository**

```bash
git clone https://github.com/Noris69/pengtools.git
cd pengtools
```

---

## **2. Install Dependencies**

```bash
npm install
```

---

## **3. Create Environment Variables**

Create a `.env.local` file:

```env
NEXTAUTH_SECRET=your_nextauth_secret
NEXTAUTH_URL=http://localhost:3000

DISCORD_CLIENT_ID=your_discord_client_id
DISCORD_CLIENT_SECRET=your_discord_client_secret

NEXT_PUBLIC_SOLANA_RPC_URL=https://api.mainnet-beta.solana.com
```

---

## **4. Run the Development Server**

```bash
npm run dev
```

The application will run on:

```bash
http://localhost:3000
```

---

# **Useful Commands**

## **Run Development Server**

```bash
npm run dev
```

## **Build Project**

```bash
npm run build
```

## **Start Production Server**

```bash
npm start
```

## **Run Lint**

```bash
npm run lint
```

---

# **Configuration Notes**

## **Solana RPC**

The project currently uses a Solana RPC endpoint to fetch wallet token balances.

Recommended improvement:

Move the RPC URL to an environment variable:

```env
NEXT_PUBLIC_SOLANA_RPC_URL=your_solana_rpc_url
```

---

## **Discord Authentication**

To enable Discord login:

1. Create an application in the Discord Developer Portal
2. Add OAuth2 credentials
3. Configure redirect URI
4. Add credentials to `.env.local`

Example redirect URI:

```text
http://localhost:3000/api/auth/callback/discord
```

---

# **Security Recommendations**

- **Do not expose private RPC keys**
- **Do not commit `.env.local`**
- **Move hardcoded wallet addresses to a config file**
- **Move RPC URLs to environment variables**
- **Protect Discord credentials**
- **Avoid exposing sensitive API keys**
- **Validate NFT eligibility server-side for critical actions**
- **Do not rely only on frontend checks for protected features**
- **Use HTTPS in production**

---

# **Git Ignore Recommendations**

```gitignore
node_modules/
.next/
out/
build/
dist/
.env
.env.local
*.log
.DS_Store
.vscode/
.idea/
```

---


# **Author**

Developed by **Noris69**.
