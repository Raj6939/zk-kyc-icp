# Overview


![New(1)](https://github.com/Raj6939/zk-kyc-icp/assets/67961128/e0e3ad7d-7c62-4024-9947-fd861eb11132)



**Description**

**Goal**
The goal of this project is, to how we can build a Reusable KYC credential System on ICP

**User Flow**

1.   The user can log in to the Credential Manager(wallet).

2.   User can onboard into DApp by providing Internet Identity through Credential Manager.

3.   IF the user's wallet does not have KYCed then, the user goes through the KYC process.

4.   DApp 1 has a canister smart contract that uses Https Outcalls for doing the User's KYC.

     This step uses [ICRC-21](https://github.com/dfinity/wg-identity-authentication/blob/main/topics/icrc_21_consent_msg.md) consent management standard by IC.

     KYC is an off-chain process that happens on the application level. In the User KYC process various types of credentials are issued such as Proof of personhood, Proof of Age, and Proof of Citizenship as per IC [VC](https://github.com/dfinity/internet-identity/blob/main/docs/vc-spec.md#ii-verifiable-credential-spec-mvp) Spec. In this scenario, the DApp 1 is the Credential Issuer and the User is the Holder of the credential.

6. 




   
