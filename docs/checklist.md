# Smart Contract Security Review Checklist

A comprehensive checklist for conducting thorough security reviews of smart contracts.

---

## Pre-Review Phase

### Documentation Review

- [ ] Read all available documentation
- [ ] Review whitepaper/technical specifications
- [ ] Understand protocol's business logic
- [ ] Identify protocol's intended behavior
- [ ] Review previous audit reports (if any)
- [ ] Understand tokenomics (if applicable)
- [ ] Review deployment plans and target chains

### Scope Definition

- [ ] Identify all in-scope contracts
- [ ] List out-of-scope components
- [ ] Determine review timeline
- [ ] Establish communication channels
- [ ] Set up testing environment
- [ ] Clone repository and verify commit hash

---

## Code Analysis Phase

### Architecture & Design

- [ ] Understand overall system architecture
- [ ] Map contract interactions and dependencies
- [ ] Identify critical functions and entry points
- [ ] Review inheritance hierarchy
- [ ] Analyze state variables and storage layout
- [ ] Check for upgradability patterns
- [ ] Review access control architecture
- [ ] Identify external dependencies

### Access Control

- [ ] Verify proper role-based access control
- [ ] Check for missing access modifiers
- [ ] Review owner/admin privileges
- [ ] Verify multi-sig requirements (if applicable)
- [ ] Check for centralization risks
- [ ] Verify timelock mechanisms (if applicable)
- [ ] Review function visibility (public/external/internal/private)
- [ ] Check for unauthorized state changes

### Reentrancy

- [ ] Identify all external calls
- [ ] Check for checks-effects-interactions pattern
- [ ] Verify reentrancy guards where needed
- [ ] Test for cross-function reentrancy
- [ ] Check for read-only reentrancy
- [ ] Verify state changes before external calls
- [ ] Review callback functions

### Integer Arithmetic

- [ ] Check for overflow/underflow (pre-0.8.0)
- [ ] Verify safe math usage
- [ ] Check for division by zero
- [ ] Review rounding errors
- [ ] Verify precision loss handling
- [ ] Check for type casting issues
- [ ] Review modulo operations

### Oracle Security

- [ ] Identify all oracle dependencies
- [ ] Check for price manipulation vulnerabilities
- [ ] Verify oracle freshness checks
- [ ] Review fallback oracle mechanisms
- [ ] Check for single point of failure
- [ ] Verify price deviation checks
- [ ] Review TWAP implementation (if applicable)

### Flash Loan Safety

- [ ] Identify flash loan attack vectors
- [ ] Check for price manipulation via flash loans
- [ ] Verify oracle resistance to flash loan attacks
- [ ] Review state changes in single transaction
- [ ] Check for economic exploits

### Token Handling

- [ ] Verify ERC20/ERC721/ERC1155 compliance
- [ ] Check for transfer return value handling
- [ ] Review approve/transferFrom patterns
- [ ] Check for fee-on-transfer token compatibility
- [ ] Verify rebasing token compatibility
- [ ] Review token decimals handling
- [ ] Check for token blacklist/whitelist issues

### Logic Errors

- [ ] Verify business logic correctness
- [ ] Check for off-by-one errors
- [ ] Review loop conditions
- [ ] Verify state machine correctness
- [ ] Check for race conditions
- [ ] Review edge cases
- [ ] Verify mathematical formulas

### Gas Optimization

- [ ] Identify gas-intensive operations
- [ ] Check for unbounded loops
- [ ] Review storage vs memory usage
- [ ] Verify efficient data structures
- [ ] Check for redundant operations
- [ ] Review function optimization opportunities

### Front-Running & MEV

- [ ] Identify front-running vulnerabilities
- [ ] Check for transaction ordering dependencies
- [ ] Review slippage protection
- [ ] Verify deadline parameters
- [ ] Check for sandwich attack vectors
- [ ] Review commit-reveal schemes (if applicable)

### Denial of Service

- [ ] Check for block gas limit issues
- [ ] Verify no unbounded loops
- [ ] Review external call failures
- [ ] Check for griefing attacks
- [ ] Verify fallback mechanisms
- [ ] Review emergency pause functionality

### Randomness

- [ ] Verify secure randomness sources
- [ ] Check for blockhash manipulation
- [ ] Review VRF implementation (if applicable)
- [ ] Verify commit-reveal schemes
- [ ] Check for predictable randomness

### Upgradeability

- [ ] Review proxy patterns (if applicable)
- [ ] Check for storage collisions
- [ ] Verify initialization functions
- [ ] Review upgrade authorization
- [ ] Check for selfdestruct in implementation
- [ ] Verify delegatecall safety

### External Interactions

- [ ] Review all external calls
- [ ] Verify safe external call patterns
- [ ] Check for unchecked return values
- [ ] Review delegatecall usage
- [ ] Verify interface compatibility
- [ ] Check for contract existence checks

### Events & Logging

- [ ] Verify critical events are emitted
- [ ] Check for indexed parameters
- [ ] Review event parameter completeness
- [ ] Verify events for state changes

### Error Handling

- [ ] Review require/revert statements
- [ ] Check for informative error messages
- [ ] Verify custom error usage (0.8.4+)
- [ ] Review try-catch blocks
- [ ] Check for silent failures

---

## Testing Phase

### Unit Testing

- [ ] Review existing test coverage
- [ ] Identify untested code paths
- [ ] Write additional tests for edge cases
- [ ] Verify test assertions
- [ ] Check for test quality

### Integration Testing

- [ ] Test contract interactions
- [ ] Verify end-to-end workflows
- [ ] Test external integrations
- [ ] Verify multi-contract scenarios

### Fuzz Testing

- [ ] Define invariants
- [ ] Set up fuzzing environment
- [ ] Run property-based tests
- [ ] Analyze fuzzing results
- [ ] Document discovered issues

### Static Analysis

- [ ] Run Slither
- [ ] Run Aderyn
- [ ] Run Mythril (if applicable)
- [ ] Review tool outputs
- [ ] Investigate true positives

---

## Protocol-Specific Checks

### DeFi Protocols

- [ ] Review liquidity pool mechanics
- [ ] Check for impermanent loss considerations
- [ ] Verify swap calculations
- [ ] Review fee mechanisms
- [ ] Check for economic exploits
- [ ] Verify liquidation logic
- [ ] Review collateralization ratios

### NFT Protocols

- [ ] Verify metadata handling
- [ ] Check for royalty implementation
- [ ] Review minting logic
- [ ] Verify burning mechanisms
- [ ] Check for enumeration issues

### Governance Protocols

- [ ] Review voting mechanisms
- [ ] Check for vote manipulation
- [ ] Verify proposal execution
- [ ] Review timelock mechanisms
- [ ] Check for quorum requirements

### Staking Protocols

- [ ] Review reward calculations
- [ ] Check for reward distribution fairness
- [ ] Verify lock-up mechanisms
- [ ] Review slashing conditions
- [ ] Check for economic exploits

---

## Final Review Phase

### Documentation

- [ ] Document all findings
- [ ] Classify severity levels
- [ ] Write proof of concepts
- [ ] Provide mitigation recommendations
- [ ] Review report for clarity

### Communication

- [ ] Prepare findings presentation
- [ ] Discuss findings with team
- [ ] Clarify any questions
- [ ] Provide guidance on fixes

---

## Post-Review Phase

### Mitigation Review

- [ ] Review all code changes
- [ ] Verify fixes address findings
- [ ] Check for new vulnerabilities
- [ ] Run regression tests
- [ ] Document mitigation status

### Final Report

- [ ] Update findings status
- [ ] Document new findings (if any)
- [ ] Provide final recommendations
- [ ] Deliver final report

---

## Additional Considerations

### Multi-Chain Deployment

- [ ] Verify compatibility with target chains
- [ ] Check for chain-specific issues
- [ ] Review cross-chain bridge security
- [ ] Verify gas costs on different chains

### Compliance & Legal

- [ ] Review regulatory considerations
- [ ] Check for compliance requirements
- [ ] Verify license compatibility

### Operational Security

- [ ] Review key management
- [ ] Check for secure deployment procedures
- [ ] Verify monitoring and alerting
- [ ] Review incident response plans

---

**Checklist maintained by:**  
Volodymyr Stetsenko  
Independent Smart Contract Security Researcher

**Last Updated:** December 2024
