## For Users:

### 1. Buy Ticket from Stepn Event 1 (se1) Flow:

This flow represents the process a user goes through to purchase a ticket for an event.

```mermaid
graph TB
  A[Connect Wallet 0xAa & Input Email Address_A]
  B[Select Stepn Event 1]
  C["Pass Token Gating & Generate Attestation ATTp[se1] on both 0xAa and a Commitment of Address_A"]
  D[Check Out & Make Payment with 50 USDC]
  E["Receive ETT[se1,001] NFT in Wallet"]
  A --> B
  B --> C
  C --> D
  D --> E
```

### 2. Access User Portal:

This flow shows how a user accesses the portal after purchasing a ticket.

```mermaid
graph TB
  A["Connect Wallet with ETT[se1,001]"]
  B[Access Portal]
  A --> B
```

### 3. Using Ticket at the Event Venue:

This flow demonstrates how a user uses their ticket at the event venue.

```mermaid
graph TB
  A[Generate QR Code]
  B[Event Admins Scan QR]
  C[Mark Ticket as Used in eevy Database]
  A --> B
  B --> C
```
Note that the event venue must be connected to the public blockchain to check if the key in the QR code is a holder of ETT token. The eevy Database is not on chain. The QR code is the Ethereum address as well as the signed current time, so it can change once a few seconds.

### 4. Ticket Recovery:

This flow outlines the steps a user takes to recover their ticket. Note that this flow is slightly incorrect as the key leading to the Pederson Commitment of `Address_A` is not mentioned. Will fix soon.

```mermaid
graph TB
  A[Go to eevy & Click Ticket Recovery]
  B[Connect New Wallet 0xBb & Input Email Address_A]
  C[Claim ATTe_A from attestation.id]
  D[Make Smart Contract Call & Attach ATTe_A]
  E["Update Ownership of ETT[se1,001]"]
  A --> B
  B --> C
  C --> D
  D --> E
```

### 5. Transfer/Resell:

This is a standard NFT transfer or resale process with an added attestation-based DvP and potential royalty.

### 6. Refund:

This flow depicts the process a user follows to get a refund.

```mermaid
graph TB
  A["Get ATTr[se1,001] using a web based refund process"]
  B["Make TX with Attached ATTr[se1,001]"]
  C["Burn ETT[se1,001] NFT"]
  D[Refund % of 50 USDC to User A]
  A --> B
  B --> C
  C --> D
```

### 7. Get eevy token (EVT):

This process is still to be confirmed (TBC). It involves getting attestations from eevy and then claiming EVT from a smart contract using those attestations.

## For Event Organizer:

### 1. Create Stepn Event 1 (se1) Flow:

This flow represents the process an event organizer follows to create an event.

```mermaid
graph TB
  A[Connect Wallet & Input Email_V]
  B[Input Event Details & Deploy Event Contract]
  A --> B
```

### 2. Access Admin Portal:

This flow shows how an event organizer or admin accesses the admin portal.

```mermaid
graph TB
  A[Connect Wallet with Admin Access]
  B[Access Admin Portal]
  A --> B
```

### 3. Check-in Users at Venue:

This flow demonstrates how event organizers or admins check in users at the event venue.

```mermaid
graph TB
  A[Install AlphaWallet & Have Admin Access]
  B[Scan User's QR Code]
  A --> B
```

### 4. Claim Money:

This flow outlines the steps an event organizer or admin takes to claim money after the event.

```mermaid
graph TB
  A[Call Claim Function in Smart Contract]
  B[Money Transferred to 0xevent0x]
  A --> B
```

### 5. Admin Recovery:

This flow depicts the recovery process for event organizers or admins.

```mermaid
graph TB
  A[Go to eevy.xyz & Click Admin Recovery]
  B[Connect New Wallet & Input Email Address_V]
  C[Claim ATTe_V from attestation.id]
  D[Make Smart Contract Call & Attach ATTe_V]
  E[Update Admin Access]
  A --> B
  B --> C
  C --> D
  D --> E
```

### 6. Get eevy token (EVT):

Similar to the user flow, this process is still to be confirmed (TBC). It involves getting attestations from eevy and then claiming EVT from a smart contract using those attestations.
