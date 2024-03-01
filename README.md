# Overview



![New-12](https://github.com/Raj6939/zk-kyc-icp/assets/67961128/42d75420-b682-408e-97d3-27b205593633)




**Description**

**Goal**
The goal of this project is, to how we can build a Reusable KYC credential System on ICP

**User Flow 1**

1.   The user can log in to the Credential Manager(wallet).

2.   User can onboard into DApp by providing Internet Identity through Credential Manager.

3.   IF the user's wallet does not have KYCed then, the user goes through the KYC process.

4.   DApp 1 has a canister smart contract that uses Https Outcalls for doing the User's KYC.

     This step uses [ICRC-21](https://github.com/dfinity/wg-identity-authentication/blob/main/topics/icrc_21_consent_msg.md) consent management standard by IC.

     KYC is an off-chain process that happens on the application level. In the User KYC process various types of credentials are issued such as Proof of personhood, Proof of Age, and Proof of Citizenship as per IC [VC](https://github.com/dfinity/internet-identity/blob/main/docs/vc-spec.md#ii-verifiable-credential-spec-mvp) Spec. In this scenario, the DApp 1 is the Credential Issuer and the User is the Holder of the credential.

6. KYC credentials are issued to the Holder.
7. The DApp issuer gets the KYC credential and converts it to a Verifiable credential(VC) format, for Proof of personhood, Proof of Age, and Proof of Citizenship.
8. The Prepared VC is then sent to the Holder Credential Manager to store.
9. Upon credential storing, the credential Manager gives a response to the DApp 1 Issuer
10. The response is then further conveyed to the Https Outcalls and canister, for Credential Attestation(VC ID) anchoring on smart contract.
11. Credential Attestation is anchored to the smart contract.
12. Smart contract gives response to DApp1 for Credential Attestation Confirmation.

**User Flow 2**

Now the user has few Verifiable credentials in his Credential Manager. Users can now go to DApp 2 and use the Same KYC-Credential in a reusable way

14. The user logged in to DApp 2 by Internet Identity, through Credential Manager.
15. Since DApp 2 already knows and trusts on Issuer, no credential Manifest is required. It directly requests the Holder for credential Type (ex: Proof of Age), through a [DIF-Presentation Request Exchange](https://identity.foundation/presentation-exchange/spec/v2.0.0/).
16. User Prepare Verifiable Presentation and share it by generating Zero-Knowledge Proof with the DApp 2.
17. DApp 2 calls its own smart contract 2 and it further calls the Issuers smart contract.
18. smart contract 2 requests for verification of the proof to the issuer's smart contract 1 where the Credential Attestation is anchored.
19. Issuer smart contract sends a response after verifying proof to the Smart contract 2.
20. Smart contract 2 confirms the verification and sends success response to the DApp2 and further to the Holder




   
