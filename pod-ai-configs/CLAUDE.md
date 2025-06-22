# PoD-Protocol Claude Code Configuration

## Project Context

PoD-Protocol (Proof-of-Development Protocol) is a decentralized verification framework for software development contributions. This protocol enables transparent, immutable tracking of development work through cryptographic proofs and blockchain integration.

## Key Information

**Repository:** https://github.com/BlindVibeDev/PoD-Protocol
**Language:** TypeScript/Rust (hybrid architecture)
**Testing:** Vitest framework + Forge (for smart contracts)
**Cryptography:** elliptic, noble-curves, ethers
**Blockchain:** Multi-chain support (Ethereum, Polygon, Arbitrum)

## Critical Development Rules

### 1. Protocol-First - Always Design First
- Research ALL cryptographic dependencies before coding
- Create complete protocol specification with security analysis
- Document thorough implementation plan BEFORE writing code
- Once design complete, implement immediately without waiting

### 2. No Stubs or Incomplete Code
- Never use stubs, fake code, or incomplete implementations
- Continue writing until ALL stubs are replaced with working code
- No proof-of-concepts - only finished, production-ready protocol code
- Iterate until all tests pass and security audits validate

### 3. Cryptographic-Driven Development
- All code must be cryptographically sound and auditable
- Implement comprehensive security tests before functionality tests
- All protocol interactions must be verifiable and immutable
- Use `pod test` commands (crypto, protocol, security, all)

## Protocol Architecture

```
packages/core          - @pod-protocol/core (protocol runtime and types)
packages/crypto        - @pod-protocol/crypto (cryptographic primitives)
packages/blockchain    - @pod-protocol/blockchain (multi-chain integration)
packages/verification  - @pod-protocol/verification (proof verification)
packages/cli           - PoD CLI with node runtime, API, interface
packages/contracts     - Smart contracts (Solidity/Vyper)
packages/sdk           - Developer SDK for integration
```

## Dependency Rules

**CRITICAL:** Everything depends on @pod-protocol/core - NO circular dependencies
- Core cannot depend on other packages
- Use @pod-protocol/core in package code
- Use packages/core in internal references

## Component Types

### Proofs
- Define development contribution verification mechanisms
- Code → Cryptographic Hash → Blockchain → Verification Response

### Validators
- Supply validation logic for proof verification
- Cross-reference commits, timestamps, signatures

### Verifiers
- Post-verification processing and reputation tracking
- Knowledge extraction, contribution scoring, developer reputation

### Nodes
- Manage decentralized network operations
- Consensus mechanisms, peer discovery, data synchronization

### Services
- Enable protocol interaction with external systems
- Blockchain integration, IPFS storage, accessible via getService()

## Architecture Abstractions

### Commit → Proof Mapping
- Git commits become cryptographic proofs
- Hashes signed with developer keys for authenticity

### Repository → Network Mapping
- Repositories become network nodes in protocol
- Decentralized perspective key for all abstractions

## Testing Commands

- `pod test crypto` - Cryptographic primitive tests
- `pod test protocol` - Protocol compliance validation
- `pod test security` - Security audit and vulnerability tests
- `pod test all` - Comprehensive test suite (default)

## Security Standards

- TypeScript for all protocol code
- Comprehensive cryptographic validation required
- All signatures must be verifiable
- Comment security-critical logic extensively
- Never omit code or use "// ..." placeholders

## Claude Code Slash Commands

PoD-Protocol-specific slash commands are available in the `.claude/commands/` directory:

**Main Commands:**
- `/protocol:dev` - Full protocol development workflow
- `/protocol:test` - Comprehensive testing including security
- `/protocol:audit` - Security audit methodology
- `/protocol:validate` - Protocol compliance validation
- `/protocol:deploy` - Deployment and verification standards
- `/protocol:component` - Generic component creation

**Specialized Commands:**
- `/protocol:pod:proof` - Create Proof components
- `/protocol:pod:validator` - Create Validators
- `/protocol:pod:verifier` - Create Verifiers
- `/protocol:pod:node` - Create Network Nodes

See `.claude/COMMANDS.md` for detailed usage examples.

## Cryptographic Requirements

- All proofs must use secp256k1 or ed25519 signatures
- Hash functions: SHA-256, Keccak-256, or Blake3
- All keys must be generated using cryptographically secure random sources
- Multi-signature support for organizational accounts
- Zero-knowledge proof support for privacy-preserving verification

## Blockchain Integration

- Multi-chain deployment strategy
- EVM-compatible smart contracts
- IPFS integration for large data storage
- Layer 2 optimization for cost efficiency
- Cross-chain proof verification support
