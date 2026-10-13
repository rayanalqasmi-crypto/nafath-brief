Version: NAFATH-V1
Track: Software

## Overview
A national digital login service allows citizens to access different government services using one account through a website or mobile app. Building this service requires six IT fields to work together. Software engineering connects government applications through secure login protocols and reliable systems. Artificial intelligence can help detect unusual login activity, but its decisions must be tested and monitored. Mobile development protects access to device features by requesting permissions only when needed. Networking supports communication between devices and servers, while technologies such as DNS over HTTPS can improve the privacy of domain lookups. Cybersecurity focuses on protecting accounts against phishing and unauthorized access through stronger authentication methods. Data management ensures that personal information is collected, stored, and processed according to Oman's legal requirements. Together, these fields support a trustworthy and accessible government service.

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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
