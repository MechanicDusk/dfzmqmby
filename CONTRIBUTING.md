# 🤝 Contributing to Solana Sniper Bot

First off, thank you for considering contributing to Solana Sniper Bot! It's people like you that make this tool better for everyone.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Bug Reports](#bug-reports)
- [Feature Requests](#feature-requests)
- [Community](#community)

---

## 📜 Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors, regardless of experience level, gender, gender identity, sexual orientation, disability, appearance, race, ethnicity, age, religion, or nationality.

### Our Standards

**✅ Positive Behavior:**
- Using welcoming and inclusive language
- Being respectful of differing viewpoints
- Gracefully accepting constructive criticism
- Focusing on what's best for the community
- Showing empathy towards other members

**❌ Unacceptable Behavior:**
- Trolling, insulting comments, or personal attacks
- Public or private harassment
- Publishing others' private information without permission
- Other unethical or unprofessional conduct

### Enforcement

Violations can be reported to support@solanasniperbot.com. All complaints will be reviewed and investigated promptly and fairly.

---

## 🎯 How Can I Contribute?

### 1. 🐛 Report Bugs

Found a bug? Help us fix it!

**Before submitting:**
- Check [existing issues](https://github.com/yourusername/solana-sniper-bot/issues) to avoid duplicates
- Verify you're using the latest version
- Test if the bug is reproducible

**Submit via:**
- [GitHub Issues](https://github.com/yourusername/solana-sniper-bot/issues/new?template=bug_report.md)

**Include:**
- Clear descriptive title
- Steps to reproduce
- Expected vs actual behavior
- Screenshots/logs if applicable
- System information (OS, version, RPC, etc.)

### 2. 💡 Suggest Features

Have an idea to make the bot better?

**Before submitting:**
- Check if the feature already exists
- Review [roadmap](./README.md#-roadmap-2026) to see if it's planned
- Search [discussions](https://github.com/yourusername/solana-sniper-bot/discussions) for similar ideas

**Submit via:**
- [GitHub Discussions](https://github.com/yourusername/solana-sniper-bot/discussions/new?category=ideas)

**Include:**
- Clear description of the feature
- Use cases and benefits
- Mockups or examples (if UI-related)
- Technical considerations

### 3. 📝 Improve Documentation

Documentation improvements are always welcome!

**Areas to contribute:**
- Fix typos and grammar
- Add missing sections
- Improve clarity
- Translate to other languages
- Add code examples
- Create video tutorials

### 4. 💻 Submit Code

Want to contribute code? Awesome!

**Good first issues:**
- Look for issues labeled [`good first issue`](https://github.com/yourusername/solana-sniper-bot/labels/good%20first%20issue)
- These are beginner-friendly and well-documented

**Areas needing help:**
- Bug fixes
- Performance optimizations
- New DEX integrations
- UI improvements
- Test coverage
- Refactoring

---

## 🛠️ Development Setup

### Prerequisites

- **Node.js** 18+ (for build tools)
- **Rust** 1.70+ (for core bot)
- **Git** for version control
- **Windows 10/11** for testing (or VM)
- **Solana CLI** tools (optional but recommended)

### Clone and Setup

```bash
# 1. Fork the repository on GitHub
# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/solana-sniper-bot.git
cd solana-sniper-bot

# 3. Add upstream remote
git remote add upstream https://github.com/yourusername/solana-sniper-bot.git

# 4. Install dependencies
npm install         # JavaScript dependencies
cargo build         # Rust dependencies

# 5. Copy example config
cp config-template.json config.json

# 6. Run in development mode
npm run dev
# or
cargo run --release
```

### Project Structure

```
solana-sniper-bot/
├── src/
│   ├── core/           # Core trading engine (Rust)
│   ├── ui/             # User interface (Electron/React)
│   ├── utils/          # Utility functions
│   └── config/         # Configuration handling
├── assets/             # Images, icons, banners
├── docs/               # Documentation
├── tests/              # Test files
├── strategies/         # Strategy presets
└── scripts/            # Build and deployment scripts
```

### Running Tests

```bash
# Run all tests
npm test

# Run specific test suite
npm test -- --grep "Trading Engine"

# Run with coverage
npm run test:coverage

# Rust tests
cargo test
```

### Building

```bash
# Development build
npm run build:dev

# Production build
npm run build:prod

# Create distributable
npm run dist
```

---

## 📏 Coding Standards

### General Principles

- **DRY (Don't Repeat Yourself)** - Avoid code duplication
- **KISS (Keep It Simple, Stupid)** - Favor simplicity over cleverness
- **YAGNI (You Aren't Gonna Need It)** - Don't add unnecessary features
- **Write self-documenting code** - Clear variable and function names
- **Comment the "why", not the "what"**

### Rust Code Style

```rust
// ✅ Good
pub async fn execute_trade(
    &self,
    token_address: &Pubkey,
    amount: u64,
) -> Result<Signature, TradingError> {
    // Validate inputs first
    self.validate_trade_params(token_address, amount)?;
    
    // Build transaction
    let transaction = self.build_transaction(token_address, amount)?;
    
    // Send with retry logic
    self.send_transaction_with_retry(transaction).await
}

// ❌ Bad
pub async fn trade(ta:&Pubkey,amt:u64)->Result<Signature,TradingError>{let tx=self.build(ta,amt)?;self.send(tx).await}
```

**Rust Guidelines:**
- Follow official [Rust Style Guide](https://doc.rust-lang.org/style-guide/)
- Use `cargo fmt` before committing
- Run `cargo clippy` to catch issues
- Add error handling with `Result<T, E>`
- Prefer `async/await` for I/O operations

### JavaScript/TypeScript Style

```javascript
// ✅ Good
async function fetchTokenData(tokenAddress) {
  try {
    const response = await api.getTokenInfo(tokenAddress);
    return parseTokenResponse(response);
  } catch (error) {
    logger.error('Failed to fetch token data', { tokenAddress, error });
    throw new TokenFetchError(`Failed to fetch data for ${tokenAddress}`);
  }
}

// ❌ Bad
async function ftd(ta){return await api.get(ta);}
```

**JavaScript Guidelines:**
- Use `async/await` over Promises
- Prefer `const` over `let`, avoid `var`
- Use template literals for strings
- Add JSDoc comments for public functions
- Follow [Airbnb Style Guide](https://github.com/airbnb/javascript)

### Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| **Files** | kebab-case | `trading-engine.rs` |
| **Functions** | snake_case (Rust) / camelCase (JS) | `execute_trade()` / `executeTrade()` |
| **Variables** | snake_case (Rust) / camelCase (JS) | `token_address` / `tokenAddress` |
| **Constants** | SCREAMING_SNAKE_CASE | `MAX_SLIPPAGE` |
| **Classes** | PascalCase | `TradingEngine` |
| **Interfaces** (TS) | PascalCase with I prefix | `ITradingStrategy` |

---

## 📝 Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, no logic change)
- **refactor**: Code refactoring
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Build process, dependencies, tooling

### Examples

```bash
# Feature
git commit -m "feat(ui): add dark mode toggle to settings panel"

# Bug fix
git commit -m "fix(trading): correct slippage calculation for CLMM pools"

# Documentation
git commit -m "docs(readme): update installation instructions for Windows 11"

# Performance
git commit -m "perf(rpc): implement connection pooling for faster requests"

# Breaking change
git commit -m "feat(api): redesign strategy configuration API

BREAKING CHANGE: Strategy config now uses new JSON schema.
Migration guide: see docs/MIGRATION.md"
```

---

## 🔄 Pull Request Process

### Before Submitting

1. **Create feature branch:**
   ```bash
   git checkout -b feat/your-feature-name
   ```

2. **Make your changes:**
   - Write clean, documented code
   - Follow coding standards
   - Add tests if applicable

3. **Test thoroughly:**
   ```bash
   npm test
   cargo test
   npm run build
   ```

4. **Update documentation:**
   - README if adding features
   - CHANGELOG with your changes
   - Code comments where needed

5. **Commit with conventional commits:**
   ```bash
   git add .
   git commit -m "feat: your feature description"
   ```

6. **Push to your fork:**
   ```bash
   git push origin feat/your-feature-name
   ```

### Submitting PR

1. **Go to GitHub** and create Pull Request from your fork

2. **Fill out PR template** with:
   - **Title:** Clear, concise description
   - **Description:** What changed and why
   - **Related Issues:** Link to relevant issues
   - **Testing:** How you tested the changes
   - **Screenshots:** If UI-related

3. **Checklist (in PR description):**
   - [ ] Code follows project style guidelines
   - [ ] Self-review completed
   - [ ] Comments added to complex code
   - [ ] Documentation updated
   - [ ] No new warnings generated
   - [ ] Tests added/updated and passing
   - [ ] Dependent changes merged

### Code Review Process

1. **Automated checks** run (tests, linting, build)
2. **Maintainers review** your code
3. **Address feedback** - make requested changes
4. **Re-request review** after changes
5. **Approval** - maintainer approves
6. **Merge** - maintainer merges to main branch

### PR Guidelines

**✅ DO:**
- Keep PRs focused and small (<500 lines if possible)
- Write clear commit messages
- Respond to feedback promptly
- Be respectful and professional

**❌ DON'T:**
- Mix multiple unrelated changes
- Submit untested code
- Ignore review feedback
- Force-push after review started (unless requested)

---

## 🐛 Bug Reports

### Before Reporting

1. **Search existing issues** - might already be reported
2. **Try latest version** - might already be fixed
3. **Verify reproducibility** - can you consistently reproduce it?

### Bug Report Template

```markdown
**Bug Description**
Clear, concise description of what the bug is.

**To Reproduce**
Steps to reproduce:
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

**Expected Behavior**
What you expected to happen.

**Actual Behavior**
What actually happened.

**Screenshots**
If applicable, add screenshots.

**Environment:**
- OS: [e.g. Windows 11 64-bit]
- Bot Version: [e.g. v3.8.2]
- RPC: [e.g. Helius Premium]
- Wallet: [e.g. Phantom]

**Logs**
```
Paste relevant log output here
```

**Additional Context**
Any other information about the problem.
```

---

## 💡 Feature Requests

### Feature Request Template

```markdown
**Feature Description**
Clear description of the feature you'd like.

**Problem It Solves**
What problem does this feature address?

**Proposed Solution**
How you envision the feature working.

**Alternatives Considered**
Other solutions you've considered.

**Use Cases**
Examples of when you'd use this feature.

**Priority**
Low / Medium / High / Critical

**Additional Context**
Mockups, examples, or references.
```

---

## 👥 Community

### Communication Channels

- **Discord:** [discord.gg/solanasniper](https://discord.gg/solanasniper) - General discussion, support
- **GitHub Discussions:** [Discussions](https://github.com/yourusername/solana-sniper-bot/discussions) - Ideas, Q&A
- **GitHub Issues:** [Issues](https://github.com/yourusername/solana-sniper-bot/issues) - Bug reports, feature requests
- **Twitter:** [@SolanaSniperBot](https://twitter.com/solanasniperbot) - Announcements

### Getting Help

**For contributors:**
- #contributors channel on Discord
- Tag @maintainers in discussions
- Email: dev@solanasniperbot.com

**For users:**
- #support channel on Discord
- Check [FAQ](./FAQ.md)
- Email: support@solanasniperbot.com

### Recognition

Contributors are recognized in:
- **CONTRIBUTORS.md** - List of all contributors
- **Release notes** - Mentioned in relevant releases
- **Discord** - Special contributor role
- **README** - Hall of fame section (for major contributions)

---

## 🏆 Contributor Levels

### First-Time Contributor
- Submit your first PR
- Get special Discord role
- Listed in CONTRIBUTORS.md

### Regular Contributor (5+ PRs)
- Trusted community member
- Early access to beta features
- Input on roadmap decisions

### Core Contributor (20+ PRs or major feature)
- Direct commit access (with approval process)
- Vote on major decisions
- Collaborate closely with maintainers

---

## 📜 License

By contributing, you agree that your contributions will be licensed under the same [MIT License](./LICENSE) that covers the project.

---

## 🙏 Thank You!

Every contribution, no matter how small, makes a difference. Whether it's a bug report, documentation fix, or major feature - we appreciate you taking the time to make Solana Sniper Bot better for everyone.

**Happy contributing! 🚀**

---

<div align="center">

[![Contributors](https://img.shields.io/github/contributors/yourusername/solana-sniper-bot?style=for-the-badge)](https://github.com/yourusername/solana-sniper-bot/graphs/contributors)

[⬆ Back to README](./README.md)

</div>
