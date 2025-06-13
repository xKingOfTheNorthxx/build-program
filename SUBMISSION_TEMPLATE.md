# Partisia Blockchain Build Program - Submission Template

Thank you for your submission! Please fill in the sections below to ensure your project is reviewed accurately.

> **Important:** To submit your project:
>
> 1. Fill out this template
> 2. Submit your project through our [Monday Board](https://forms.monday.com/forms/a23209ca08d9c6b6cb9c08cb0a30466f?r=euc1)
> 3. Create a GitHub Issue in this repository with your progress updates

---

## 0. Legal Requirements

By submitting to this program, I confirm that:

- [x] I am over 18 years old or the age of majority in my jurisdiction of residence, or I am a business entity
- [] I am not a resident of, citizen of, or located in:
  - [x] United States
  - [x] Any geographic area subject to UN sanctions
  - [x] Any geographic area subject to US sanctions
  - [x] Any geographic area subject to EU sanctions
  - [x] Any geographic area subject to Swiss sanctions
  - [x] Any geographic area subject to any other sovereign country sanctions or embargoes

---

## 1. Project Information

- **Project Title:**
  _Privotto_
- **Project Tier:**
  - [ ] Beginner (Easy) – Reward up to $2,000
  - [x] Intermediate (Medium) – Reward $2,000–$4,000
  - [ ] Advanced (Hard) – Reward $4,000+
        _(Select the tier that best fits your project)_
- **Reward:**
  $3000
- **Estimated Timeline:**
  2-3 weeks of actaul dev time 
- **GitHub Repository Link:**
https://github.com/nerds-cooking/partisia-lottery/tree/main
- **Contact Info:**
 josh.robson@nerds.cooking
- **Team Members:**
Team Members: (Jamie Bell - CTO) (Simon Gatenby - Tech Architect) (Josh Robson - Product Owner)

---

## 2. Project Brief

Objective:
To build a privacy-preserving lottery dApp where users can buy tickets and participate in draws without exposing their identity, ticket count, or compromising fairness — powered by Partisia’s MPC technology.

Key Features:

-Private ticket purchases using a credit-based system
-Fair and tamper-proof winner selection using MPC-generated randomness
-MPC20 token integration for payments and prize pools
-Clear lottery lifecycle (create → enter → draw → claim)
-React frontend with Parti wallet support for seamless UX

Use of Partisia MPC:

-MPC ensures private credit balances and ticket purchases
-Winner selection combines entropy from multiple parties via MPC
-Sensitive operations (like verifying winners and updating balances) are done without revealing private data
-No participant data or ticket quantities are exposed on-chain

Target Users:

Web3 developers or DAOs needing transparent but private raffle mechanics
Communities or platforms running reward-based games, contests, or fundraisers

End users who value fairness and privacy when participating in draws

Unique Value Proposition:

Unlike typical blockchain raffles that expose all participants and can be gamed, our solution keeps the entire draw process private — without sacrificing verifiability. It shows off the real-world power of MPC by solving a simple but widely applicable problem: how to run a fair, private, and abuse-proof lottery.

---

## 3. Technical Description

### 3.1 Detailed Overview

_(Provide a detailed explanation of your architecture, including any flow diagrams or system architecture charts.)_
https://github.com/nerds-cooking/partisia-lottery/blob/main/readme.md

### 3.2 Technical Approach

MPC Integration:

We use Partisia’s MPC to manage secret user balances and perform a private, tamper-proof winner selection. Randomness is generated using secret inputs from the creator and participants, then combined securely. Only the final winning result is revealed.

Core Functionality:

Users buy private credits with MPC20 tokens
Credits are used to enter lotteries without exposing ticket counts
Lottery creators set rules and fund prizes
Winner is picked via MPC after deadline
Only winner’s ID is revealed, prize is claimable

Testing & Verification:

Smart contract unit tested via Partisia tooling
End-to-end tests across backend, frontend, and wallet flow
All lottery edge cases tested locally

Security Considerations:

Credit balances and ticket purchases are hidden
Winner selection is MPC-secured and verifiable
No leakage of ticket quantity or participant identities
Performance Metrics:

Lightweight contract and frontend setup
MPC draw completes in seconds
Optimized for minimal on-chain state and efficient flow

### 3.3 Development Stack

Frontend: _(React + Vite)
Backend: (NestJS)
Smart Contracts: (Rust + Partisia)
Other Tools: (Coffee)

---

## 4. Deliverables

List all the deliverables included with your submission:

- Source code: https://github.com/nerds-cooking/partisia-lottery/tree/main
- Comprehensive README: https://github.com/nerds-cooking/partisia-lottery/blob/main/readme.md
- Deployment instructions: see above 
- Demo video: 
- Link to the deployed project: https://lottery.partisia.nerds.cooking/ 
- Test: https://github.com/nerds-cooking/partisia-lottery/blob/main/java-run-tests.sh


---

## 5. Project Timeline

Initial Exploration
Start date: April (~1 week)
We began prototyping the first version of the smart contract while still getting familiar with Partisia’s tooling and constraints.
This early work helped clarify the logical flow, but we realised a number of technical limitations (especially around secret handling and state updates) that required a significant rethink.

Full Restart & Redesign:
Start Date: May 27, 2025
We restarted with a clean slate, rebuilding the smart contract and overall system based on what we’d learned. This version was designed to align tightly with Partisia’s MPC model and the bounty’s goals.
Milestone 1:
Description: Rewritten smart contract and credit abstraction layer to support privacy-preserving ticketing and draws
Target Date: June 3, 2025
Milestone 2:
Description: Backend and frontend fully integrated, with Parti wallet support, draw logic, and complete user flow
Target Date: June 10, 2025
Final Submission Date: June 13, 2025

Buffer Time:
We realistically estimated 2 weeks end-to-end if working full-time. However, due to part-time capacity and delays from external feedback, bug resolution, or waiting on responses, we ended up with around a 1-week buffer in actual development time.

--

## 6. Additional Information

Include any additional details that you believe are important:
Additional Notes & Considerations

Known Issues & Limitations

Partial Privacy on User Actions: While balances and ticket counts are protected via MPC, it’s currently not possible to achieve full user privacy. Each secret update (e.g., purchasing tickets) alters the secret ID, which leaves a detectable footprint tied to the user.

ZK Struct Limitations: Ideally, user entries would be stored in a shared array-like structure using ZK to fully anonymize balances and entry activity — but this isn’t currently possible due to ZK stack constraints on array handling.

Workaround in Place: We’ve implemented a credit abstraction layer to reduce visibility into individual ticket purchases, but full obfuscation isn’t yet technically viable.

Future Improvements

- Transition to ZK array models when supported
- Enhance Parti wallet support to allow direct secret balance visibility (logic is already implemented and ready to activate)



---

## 7. Acknowledgment

By submitting this project, I confirm that:

- The work is my own or properly credited.
- I agree to release the project under an approved open-source license.
- I accept the evaluation rubric and community voting process.
- I will provide weekly progress updates through GitHub Issues in this repository.
- I understand that the project must be completed within the estimated timeline.
- I will actively engage with the community and respond to feedback.
- I understand that my project will be subject to community voting on [CrowdSnap](https://www.crowdsnap.ai/), which contributes 10% to the final evaluation score.

---

_Thank you for your submission! We look forward to reviewing your project and will be in touch with feedback._
