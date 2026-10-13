Version: NAFATH-V1
Track: Software

## Overview
A national digital login service allows citizens to access different government services using one account through a website or mobile app. Building this service requires six IT fields to work together. Software engineering connects government applications through secure login protocols and reliable systems. Artificial intelligence can help detect unusual login activity, but its decisions must be tested and monitored. Mobile development protects access to device features by requesting permissions only when needed. Networking supports communication between devices and servers, while technologies such as DNS over HTTPS can improve the privacy of domain lookups. Cybersecurity focuses on protecting accounts against phishing and unauthorized access through stronger authentication methods. Data management ensures that personal information is collected, stored, and processed according to Oman's legal requirements. Together, these fields support a trustworthy and accessible government service, where understanding the difference between OAuth 2.0 and OpenID Connect is essential for secure citizen login.

## Software
OAuth 2.0 is an authorization framework that allows applications to obtain limited access to protected resources without sharing the user's password. OpenID Connect (OIDC) adds an identity layer on top of OAuth 2.0 to authenticate users. OIDC provides an ID Token containing information about the authentication event, while OAuth 2.0 uses access tokens for delegated resource access. For a national digital login service, OIDC is suitable for verifying citizens' identities across connected government applications.

Resource: OpenID Connect Core 1.0 incorporating errata set 2 - https://openid.net/specs/openid-connect-core-1_0-errata2.html

## AI
Before deploying AI to detect suspicious logins, the authority should manage risks using the NIST AI Risk Management Framework. False positives could block legitimate citizens, while false negatives could miss attacks. The model may also introduce bias, privacy risks, and unreliable decisions. The authority should establish accountability, identify affected users, measure accuracy and fairness, and manage identified risks. Human review, ongoing monitoring, and clear procedures for challenging incorrect decisions are important safeguards.

Resource: AI RMF Core - https://airc.nist.gov/airmf-resources/airmf/5-sec-core/

## Mobile
Android separates permissions into categories, and sensitive permissions require user approval at runtime on supported Android versions. A government login app cannot automatically access protected features such as the camera or location simply because it is installed. The app should request a permission when the user starts a feature that needs it, explain its purpose when appropriate, and handle denial gracefully. Developers should request only necessary permissions and avoid blocking unrelated login features when access is refused.

Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting

## Networking
DNS over HTTPS (DoH) sends DNS queries and responses through an encrypted HTTPS connection instead of traditional unencrypted DNS transport. For citizens using the national login service, it helps prevent local network observers from reading or modifying DNS requests in transit. However, DoH does not hide queries from the chosen DNS resolver, conceal all connection metadata, or guarantee that DNS answers are authentic. DNSSEC provides separate protection for DNS data integrity.

Resource: RFC 8484 - DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484

## Cybersecurity
Phishing-resistant authentication prevents attackers using fake login websites from obtaining reusable authentication secrets or valid responses. It cryptographically binds authentication to the legitimate website or communication channel. FIDO2/WebAuthn security keys and appropriately configured passkeys can provide phishing-resistant multi-factor authentication. Smart cards using client-authenticated TLS can also qualify. In contrast, passwords combined with SMS codes, email codes, or authenticator-app one-time passwords are not phishing-resistant because attackers can trick users into entering or relaying those codes.

Resource: NIST SP 800-63B - Authenticators - https://pages.nist.gov/800-63-4/sp800-63b/authenticators/

## Data
Under Oman's Personal Data Protection Law, the authority must identify its lawful basis for processing citizens' data and obtain explicit consent where required, recognizing applicable legal exceptions. It must explain processing purposes, protect confidentiality, assess risks, apply technical and organizational safeguards, and appoint a data protection officer. Citizens have rights concerning access, correction, and erasure, subject to legal conditions. The authority must also document processing and report qualifying personal data breaches to the ministry and affected individuals according to applicable rules.

Resource: Royal Decree 6/2022 - Personal Data Protection Law (Consolidated) - https://decree.om/2022/l20220006/

## Misconception in My Track
A common misconception is that OAuth 2.0 is a user authentication protocol and can independently prove who has logged in. In reality, OAuth 2.0 primarily provides delegated authorization to access protected resources. OpenID Connect adds an identity layer to OAuth 2.0 and introduces the ID Token to communicate authentication information. This distinction matters for a national digital login service because government applications must reliably identify citizens, not merely receive permission to access resources. The OpenID Connect Core 1.0 specification, in Section 1, "Introduction," describes OpenID Connect as an identity layer on top of OAuth 2.0.

## Open Question
How can a national digital login service securely manage OpenID Connect sessions across multiple government applications while allowing citizens to sign out safely from all connected services?
