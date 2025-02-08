# Online Learning Applications (OLA)

## Authors
- **Alberto Eusebio** - 10970712
- **Gianluigi Palmisano** - 10782779
- **Martina Riva** - 10756775

## Overview
This project explores online learning strategies for **pricing and bidding** in stochastic and adversarial environments. It employs **Multi-Armed Bandits (MAB) algorithms** and **primal-dual approaches** to optimize decision-making in digital advertising and auction-based pricing models.

## Requirements
### **Requirement 1: Stochastic Pricing & Bidding**
- **Pricing**:
  - Environment: Stochastic Pricing with a continuous price range \([0,1]\)
  - **Algorithm**: Gaussian Process Upper Confidence Bound (**GPUCB**)
  - **Observations**:
    - Sampled prices concentrate near the optimal price
    - Uncertainty is lower near optimal prices
    - GPUCB can overfit, causing instability
  
- **Bidding**:
  - **Auction Model**: Second-price auctions (truthful mechanism)
  - **Algorithm**: UCB-like algorithm (**UCBBidding**)
  - **Observations**:
    - Bids oscillate before stabilizing
    - Sublinear cumulative regret (**Õ(√T)** under specific conditions)
  
- **Multiplicative Pacing (MP) Strategy**:
  - **Algorithm**: Primal-dual approach
  - **Observations**:
    - The algorithm explores initially
    - Once the optimal bid is identified, cumulative regret decreases

- **Simulation Parameters**:
  - **Advertisers**: 4
  - **Product valuation**: 0.8
  - **Click-through rate (CTR)**: 0.4
  - **Budget**: 2000
  - **Time steps**: 10,000
  - **Users per day**: 1000

### **Requirement 2: Non-Stationary Pricing & Bidding**
- **Bidding**:
  - Environment: **Highly non-stationary (adversarial)**
  - **Auction Model**: Generalized First-Price Auction (pay = bid)
  - **Algorithm**: Full-Feedback Multiplicative Pacing (**FFMP**)
  - **Observations**:
    - Achieved sublinear regret

- **Pricing**:
  - **Algorithm**: EXP3 (η=√(logK/KT)) for a Bernoulli environment
  - **Observations**:
    - Handles adversarial MAB problems
    - Sublinear regret achieved

- **Simulation Parameters**:
  - **Days**: 100
  - **Users per day**: 1000
  - **Arms**: 5

### **Requirement 3: Non-Stationary Pricing with Sliding Window & CUSUM**
- **Pricing**:
  - **Environment**: Non-stationary, divided into 5 intervals
  - **Algorithm**: 
    - **Sliding Window UCB (SWUCB)**: Continuously explores and adapts
    - **CUSUM-UCB**: Two-phase approach (**estimation** & **detection**)
  - **Observations**:
    - **CUSUM-UCB** performs better than SWUCB (lower cumulative regret)

- **Bonus**: 
  - **Double Gaussian Process UCB Agent** used for a **2-item stochastic pricing environment**
  - Achieved sublinear regret

### **Requirement 4: Generalized First-Price Auction (Non-Truthful)**
- **Agents Considered**:
  - **0-1**: UCB Bidding Agents
  - **2-3**: Multiplicative Pacing Agents (Truthful Auctions)
  - **4-5**: Full Feedback Multiplicative Pacing Agents (Non-Truthful Auctions)

- **Auction Slots & Performance**:
  - **1-slot auction**: Best performers are **MP Agents**, followed by **UCB Agents**
  - **2-slot auction**: **FF MP Agents** outperform MP, while **UCB Agents** start winning after MP budget depletion
  - **3-slot auction**: FF MP remains dominant, **UCB gains advantage** when MP depletes budget earlier

- **Simulation Parameters**:
  - **Users**: 1000
  - **Budget**: 100
  - **Random valuations**

## Key Findings
- **MP and FF MP strategies** outperform UCB in **most** auction settings.
- **UCB Agents** perform better when MP **exhausts** its budget.
- **CUSUM-UCB** is **more efficient** than SWUCB in non-stationary pricing environments.
- **EXP3** handles **adversarial pricing** better than traditional UCB-based approaches.
