# Nexus Gaming Protocol

A decentralized gaming protocol built on Stacks blockchain that enables NFT-based asset management, avatar progression, and competitive gameplay with Bitcoin rewards.

## Overview

The Nexus Gaming Protocol creates an immersive gaming ecosystem where players can:

- Mint and trade NFT game assets with varying rarity levels
- Create and level up avatars through gameplay
- Access different virtual worlds with unique requirements
- Compete on leaderboards for Bitcoin rewards
- Earn experience and achievements

## Core Features

### NFT Game Assets

- Unique identifiers and metadata
- Multiple rarity tiers (common, uncommon, rare, epic, legendary)
- Power levels (1-1000)
- Experience and level progression
- World-specific attributes

### Avatar System

- Customizable avatar names
- Level progression (max level 100)
- Experience-based advancement
- Achievement tracking
- Equipment management (up to 5 assets)
- Multi-world access permissions

### Virtual Worlds

- Unique names and descriptions
- Entry requirements
- Active player tracking
- Reward distribution
- Access control mechanisms

### Competitive Leaderboard

- Player scoring system
- Games played tracking
- Total rewards earned
- Achievement tracking
- Rank management

## Technical Specifications

### Constants

#### Experience System

- Maximum Level: 100
- Maximum Experience Per Level: 1,000
- Base Experience Required: 100

#### Protocol Configuration

- Configurable protocol fee
- Adjustable leaderboard size (max 500 entries)
- Total asset, avatar, and world tracking

### Core Functions

#### Asset Management

```clarity
(mint-nexus-asset (name (string-ascii 50))
                  (description (string-ascii 200))
                  (rarity (string-ascii 20))
                  (power-level uint)
                  (world-id uint)
                  (attributes (list 10 (string-ascii 20))))
```

- Mints new game assets
- Validates asset properties
- Assigns metadata and ownership

#### Avatar System

```clarity
(create-avatar (name (string-ascii 50))
               (world-access (list 10 uint)))
```

- Creates new player avatars
- Sets initial stats and access rights
- Links to leaderboard entry

#### Experience Management

```clarity
(update-avatar-experience (avatar-id uint)
                         (experience-gained uint))
```

- Handles experience gains
- Manages level progression
- Validates experience caps

#### World Management

```clarity
(create-game-world (name (string-ascii 50))
                   (description (string-ascii 200))
                   (entry-requirement uint))
```

- Creates new game worlds
- Sets access requirements
- Tracks player activity

### Security Features

#### Access Control

- Admin whitelist system
- Principal validation
- Asset ownership verification
- World access validation

#### Error Handling

- Comprehensive error codes
- Input validation
- Transaction safety checks
- Experience and level caps

## Getting Started

### Prerequisites

- Stacks blockchain environment
- Clarity development tools
- Admin principal for initialization

### Initialization

1. Deploy the contract
2. Initialize protocol parameters:

```clarity
(initialize-protocol entry-fee max-entries)
```

3. Create initial game worlds
4. Set up admin access rights

### Creating Game Assets

1. Call `mint-nexus-asset` with required parameters
2. Assign to appropriate world
3. Set initial attributes and power level

### Managing Players

1. Players create avatars using `create-avatar`
2. Grant world access permissions
3. Track experience and level progression
4. Monitor leaderboard performance

## Error Codes

| Code | Description        |
| ---- | ------------------ |
| u1   | Not authorized     |
| u2   | Invalid game asset |
| u3   | Insufficient funds |
| u4   | Transfer failed    |
| u5   | Leaderboard full   |
| u6   | Already registered |
| u7   | Invalid reward     |
| u8   | Invalid input      |
| u9   | Invalid score      |
| u10  | Invalid fee        |

## Best Practices

### Asset Management

- Validate all asset properties before minting
- Maintain consistent naming conventions
- Use appropriate rarity levels
- Balance power levels across worlds

### Player Experience

- Regular experience updates
- Fair level progression
- Achievement tracking
- Balanced reward distribution

### World Management

- Clear entry requirements
- Active player monitoring
- Regular reward distribution
- Fair access controls

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Security Considerations

- Admin access control
- Input validation
- Transaction safety
- Experience caps
- Level limits
- Asset ownership verification
- World access control
