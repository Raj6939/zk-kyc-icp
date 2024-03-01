# Overview



![ICP-kyc-widget-flow drawio](https://github.com/Raj6939/zk-kyc-icp/assets/67961128/05d6ce6d-ab48-4dc4-aadd-eeb4f77510f6)





**Description**

**Goal**

The goal of this project is, to how we can build a Reusable KYC credential System on ICP

**User Flow 1**

1. When a user comes to any DApp (Verifier App), to connect with the it and use the DApps services user needs to do KYC. Here User gets redirected to the KYC provider via the `KYC-Widget`.

2. The `KYC-Widget` consists of a few verifications such as Face check(liveliness check), Passport Document Verification, etc.
 
3. At `KYC-Widget` Various Verifications get done and claims of those get sent to the Credential Issuer to issue credentials. The `KYC-widget` further calls the `Credential-issuer` once the KYC is completed at the KYC widget. The `Credential-issuer` gets the KYC credentials claims and issues various types of Credentials in the format of [Verifiable Credentials (VC)](https://github.com/dfinity/internet-identity/blob/main/docs/vc-spec.md#ii-verifiable-credential-spec-mvp) spec. For example: Proof of Personhood, Proof of Age, Proof of Citizenship, etc.

4. These Credentials get stored in the Users `ID-Wallet` and their credential status gets anchored on the Verifiable Credential Status Registry (VDR). This VDR is a canister smart contract on the ICP blockchain.

5. Now once the user has various credentials in his `ID-Wallet`, the Verifier App can request credentials/proof. Whenever required, the user can mint SBT or custom tokens for generated ZK-proofs in his `ID-wallet`. For miniting SBT or NFT, the Verifier App can request credentials from the user.

6. This request is followed by [DIF-Presenation-request](https://identity.foundation/presentation-exchange/spec/v2.0.0/) format. The verifier can request credentials from the user by mentioning `IssuerId` and `credentialSpec`.

6. Once the User gets the request from Verifier, the user can generate zero-knowledge proof of the given credentialSpec. For ex: zero-knowledge-proof for membership or zk-proof of Age to mint NFT and SBT from NFT, SBT canister smart contract.

For Verifying Credential Status Verifier can query VDR Canister Smart contract and check revocation of Credentials.



   
