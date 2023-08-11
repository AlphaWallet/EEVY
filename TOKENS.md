# Tokens in eevy.xyz

Understanding the project begins with its primary components - the tokens. In eevy.xyz, tokens either represent off-chain tokens, materialized by attestations in the SmartLayer Network, or on-chain tokens, materialized on a public blockchain.

| Token Name | Description & Use | Owner |
|------------|------------------|-------|
| ETT (Event Ticket NFT, ERC721/1155 and ERC5169) | Ownership of the event ticket. Tickets in this project are NFTs, catering to the crypto-savvy user base. | Ticket Holders |
| EOT (Event Organiser NFT, ERC721/1155 and ERC5169) | Admin "keys" or ownership of the event. Only authorized event organizers can conduct events. ETTs are issued based on ATTp, signed by EOT token holders. | Event Organiser |
| USDC ($, ERC20) | Payment token/currency. | Ticket Buyer |
| ATTp (Permission to Buy Ticket Attestation token) | Token-gated event access. This attestation ensures that tickets are only purchased after obtaining an ATTp from the dapp. | Ticket Buyer |
| ATTe (Email ID Attestation token) | Proof of email ID ownership with crypto wallet. Refers to individuals who've switched wallets and wish to reassign ownership of their old NFTs. | Wallet Loser[^1] |
| ATTr (Refund Cheque Attestation token) | Refund mechanism. Refunds are processed using an attestation, eliminating the need for dapps to hold cryptocurrency. | Ticket Holders |
| EVT (eevy token, ERC20) | Loyalty points. A loyalty token, rewarding EEVY.xyz users with points. | Ticket Holders and Event Organisers |

[^1]: It's not just bad luck; it's someone who swapped wallets and probably misplaced the old one, and wanting to reassign ownership of their old NFTs.

For clarification, all off-chain attestation tokens begin with "ATT". While we often use this naming convention, it's not mandatory. Token issuers or users can convert an off-chain token to an on-chain one if they wish.

## NFT tokens

First let's look at the 2 NFT tokens at work.

Both ETT and EOT don't necessarily have to be NFT tokens. However, in this project, they are. This is because our users are crypto-savvy and expect tickets to be NFTs. These 2 tokens are linked.

EOT serves as an token of power. Only official events are permitted. Organizers need top-level authorization to conduct events. This is done by giving the Event Organisers EOT tokens. The smart contract issuing ETTs has a mechanism in it to ensure that an ETT can only be minted if the corresponding EOT exists.

## Attestation Tokens

Now let's take a closer look at the two attestation tokens specific to this project:

An ATTp is an authorization that allows an ETT to be issued to a ticket holder. This is done by the ticket holder initiating a mint transaction with the ATTp included. This mechanism ensures that tickets can't be purchased without first obtaining an ATTp from the Dapp. This setup is beneficial for several reasons:

  - Users are expected to follow a specific purchase flow on the website. We don't want them bypassing steps, like agreeing to terms and conditions.
  - Event organizers might prefer selling tickets on their Dapp rather than directing users to a universal ticket-selling platform. Different Dapp issue ATTp tokens, each signed by their respective organizers.
  - Each event's ATTp can contain specific data, like price, location, and date. This flexibility allows the ATTp to store token data used later for minting ETTs, rather than forcing organizers to provide all event details to the smart contract upfront.

ATTr exists because refunds aren't processed by Dapp initiating a transaction. Instead, they use another attestation, allowing the ticket holder to request a refund. This approach is chosen because event organizers' Dapp websites prefer not to hold cryptocurrency, which would be needed to cover gas fees for refunds.

