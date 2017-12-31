I used to do security in a former life, and here are some musings on the topic, which will eventually be disected into various essays. 

For now it’ll be confusing as I’m brain dumping to various audiences with various knowledge (end users, architects, CEOs, designers)

<!-- TOC -->

- [Good Security](#good-security)
    - [Single Sign On: One account to rule them all.](#single-sign-on-one-account-to-rule-them-all)
    - [0.0.1.2. Great design: Microsoft Authenticator](#0012-great-design-microsoft-authenticator)
    - [0.0.1.3. Git tools, personal access tokens](#0013-git-tools-personal-access-tokens)
    - [0.0.1.4. Googles OTP reset codes](#0014-googles-otp-reset-codes)
    - [0.0.1.5. Multi Factor Authentication](#0015-multi-factor-authentication)
    - [0.0.1.6. Full Device Encryption (Bitlocker, TPM, Truecrypt)](#0016-full-device-encryption-bitlocker-tpm-truecrypt)
    - [0.0.1.7. Public Key sign in via SSH](#0017-public-key-sign-in-via-ssh)
    - [0.0.1.8. Live sign in for windows](#0018-live-sign-in-for-windows)
    - [0.0.1.9. Single Payment System: Paypal, Amazon, Google Express](#0019-single-payment-system-paypal-amazon-google-express)
- [0.0.2. Bad Security](#002-bad-security)
    - [0.0.2.1. E-mail password resets](#0021-e-mail-password-resets)
    - [0.0.2.2. SMS Password reset tools  weakness](#0022-sms-password-reset-tools--weakness)
- [0.0.3. Funny](#003-funny)
    - [0.0.3.1. Can’t unlock the door w/Amazon Alexa](#0031-cant-unlock-the-door-wamazon-alexa)
- [0.0.4. Uncategorized](#004-uncategorized)
    - [0.0.4.1. Apple Pay](#0041-apple-pay)
    - [0.0.4.2. Chip and PIN and tap in rest of world](#0042-chip-and-pin-and-tap-in-rest-of-world)
    - [0.0.4.3. Credit card vs Debit Card security](#0043-credit-card-vs-debit-card-security)
    - [0.0.4.4. Account vs Identity](#0044-account-vs-identity)
    - [0.0.4.5. The end of privacy](#0045-the-end-of-privacy)
    - [0.0.4.6. ICloud vs OneDrive: Why do I need to login](#0046-icloud-vs-onedrive-why-do-i-need-to-login)
    - [0.0.4.7. YubiKey: Proof of human](#0047-yubikey-proof-of-human)
    - [0.0.4.8. RSA Secure ID](#0048-rsa-secure-id)
    - [0.0.4.9. Secure Boot](#0049-secure-boot)

<!-- /TOC -->
### Good Security

We’ve made lots of stride in the security world, here are some of the ideas that have really stood out. 

#### Single Sign On: One account to rule them all. 
Perhaps better articulated as a small number of accounts to run them all.

Single sign in allows users to use a single account to login into many web sites, which means you don’t need to great a new account for every product you use. 

Google, Facebook, Twitter, and Microsoft have excellent single sign on solutions. 

**SSO vs Identity**
Sign can be orthogianl to identity. For example, multiple SSO services can provide the same identity. For example, FB can be configured to provide a google e-mail identity, just as google does.  Users can register multilple SSO services for the same identity - which is ideal in the case of service providers avoiding dependance on a single SSO provider. 

**Why doesn’t everyone use SSO?**
I suspect a few things, many of which I disagree with. 

* Dependant on a SSO providers:  Transient downtime, out of business.

If the SSO provider is down, users can’t login - this is a unfixable experience.

Far worse, if a SSO provider goes out of business, and they are the only identity of the users in the service’s system, the service team will need to have an emergency scramble to re-create user accounts. This would be a nightmare scenario as it can be very difficult to contact all users. 

* Cheaper to run your own AuthN system then build SSO

I believe this belief is an outdated myth.  In the past, before the standardization of OAUTH, and the excellent libraries that support it, using OATH is significantly cheaper to implement.

Moreover, when you look at the total cost of password system ownership, like secure password storage, password resets, and security leaks, I believe rolling your own AuthN system very quickly becomes the higher cost solution. 

#### 0.0.1.2. Great design: Microsoft Authenticator
The best authenticor applicaiton I’ve seen is Microsoft’s for iOS. In this solution, when you a user logs into a service with Microsoft SSO on any device, they are presented with a 2 digit number on the device accessing the service, **and** a notification pops up on the user’s mobile device to open Microsoft Authenticator. 

On the users mobile device, in Microsoft Authenticator, a choice of 2 digit numbers are presented. When the user clicks on the matching 2 digit number the users is logged into the service. 

Notice, the user completes the sign on flow cross device without needing to return to the source application.

**Why don’t more authenticators use this model?** 

I’m not sure, I suspect a few things: 
* Architects don’t think of pushing the boundaries in their auth systems. 
* It ties the authN to the authenticator app. 
  This sounds odd, but the auth model where you can enter a 6 digit number allows the SSO provider to use multiple transport channels to provide the 6 digit number (e.g. SMS, E-mail, etc)


#### 0.0.1.3. Git tools, personal access tokens
#### 0.0.1.4. Googles OTP reset codes
#### 0.0.1.5. Multi Factor Authentication
#### 0.0.1.6. Full Device Encryption (Bitlocker, TPM, Truecrypt)
#### 0.0.1.7. Public Key sign in via SSH
#### 0.0.1.8. Live sign in for windows
#### 0.0.1.9. Single Payment System: Paypal, Amazon, Google Express
### 0.0.2. Bad Security
#### 0.0.2.1. E-mail password resets
#### 0.0.2.2. SMS Password reset tools  weakness
### 0.0.3. Funny
#### 0.0.3.1. Can’t unlock the door w/Amazon Alexa
### 0.0.4. Uncategorized
#### 0.0.4.1. Apple Pay
#### 0.0.4.2. Chip and PIN and tap in rest of world
#### 0.0.4.3. Credit card vs Debit Card security
#### 0.0.4.4. Account vs Identity
#### 0.0.4.5. The end of privacy
#### 0.0.4.6. ICloud vs OneDrive: Why do I need to login
#### 0.0.4.7. YubiKey: Proof of human
#### 0.0.4.8. RSA Secure ID
#### 0.0.4.9. Secure Boot