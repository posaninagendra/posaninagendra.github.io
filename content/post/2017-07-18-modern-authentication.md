---
title: The AAs of security, Authentication & Authorization
date: 2017-07-18
description: "Hows and whats of Authentication and Authorization"
tags: [
    "protocol",
    "development",
    "security"
]
---
Authentication and Authorization are the two fundamentals of security that we are dealing today. With rapid increase of the usage of computers, cell phones and other smart devices like tablets, smart watches and other IoT devices, applications authenticating its users on various devices has become a crucial problem. Also, now-a-days many companies are coming up with multiple related yet independent software products and authenticating their users on each of these applications and granting authorization access to the resources has become a challenging problem.

A best solution to the above mentioned problems is by implementing Single Sign On (SSO) standards. SSO is an access control mechanism that lets the users to authenticate and grant permissions to access the resources that they own. With this standard user logs in to the system with single user id and password to access all the connected systems.

There are different ways by which one can go about to implement this mechanism, the popular protocols that define this standards are given below.

1. Security Assertion Markup Language (SAML)
2. OpenID
3. OAuth

These above mentioned protocols have few overlapped mechanisms, but they all are different, it is often confusing to know what each protocol does. I try to explain this in this article.

The one liner definition of each of these protocols are given below.

1. SAML: Single Sign On for enterprise users.
2. OpenID: Single Sign On for consumer users.
3. OAuth: Authorization between applications.

## Authentication: Single Sign On  

As we know that the increasing trend of having multiple related yet independent software products
demands the use of Single Sign On standards. A good example to see why this is so important is, consider Google, they have a lot of related software products like Gmail, Google Docs, Google Photos, Google Drive etc. If they had planned to use individual user records for each of their products, they will face number of problems to start with, it is a bad user experience to prompt user to authenticate to use the products after logging in to one of the products and say if you are an employee of the company and you get privileged access to all these products and when you leave the company they have to delete your user record in each of these products.

Instead Single Sign On proposes a centralized user record management and one time user authentication to access across the applications. The prime benefits of this standard is given below.

1. Mitigate risk for access to 3rd-party sites (user passwords not stored or managed externally)
2. Reduce password fatigue from different user name and password combinations
3. Reduce time spent re-entering passwords for the same identity
4. Reduce IT costs due to lower number of IT help desk calls about passwords  

There are two popular protocols that implements the SSO, 1. SAML and 2. OpenID.

**Security Assertion Markup Language (SAML)** encompasses profiles, bindings and constructs to achieve the following.

1. Single Sign On
2. Identity management
3. Federation

Some key specifications of SAML are given below.

1. SAML is an XML based, open-standard data formatted exchange of authentication and authorization between parties.

2. It started in 2001 and got continuously updated to the latest standards. The latest version SAML 2.0 is released in 2005.

3. A SAML protocol describes how certain SAML elements (including assertions) are packaged within SAML request and response elements, and gives the processing rules that SAML entities must follow when producing or consuming these elements.

4. A SAML *binding* is a mapping of a SAML protocol message onto standard messaging formats and/or communications protocols. There is a brand new binding specification in SAML 2.0 that defines the following standalone bindings:
  * SAML SOAP Binding (based on SOAP 1.1)
  * Reverse SOAP (PAOS) Binding
  * HTTP Redirect (GET) Binding
  * HTTP POST Binding
  * HTTP Artifact Binding
  * SAML URI Binding

5. A SAML *profile* describes in detail how SAML assertions, protocols, and bindings combine to support a defined use case.
  * Web Browser SSO Profile
  * Enhanced Client or Proxy (ECP) Profile
  * Identity Provider Discovery Profile
  * Single Logout Profile
  * Name Identifier Management Profile

6. SAML mandates XML Signature and XML Encryption to enforce data integrity and confidentiality.  

![img1](/post/assets/authentication/saml.png)

The Web Browser SSO use case is shown in the image above. As we have seen, SAML defines three roles.

1. Identity Provider (IDP): This role will validate the identity of the user who asks for the service
2. Service Provider (SP): This role provide the service to the user
3. Principle: The is typically a user asking for service from SP and getting validated by IDP.

**OpenID** is an open standard and decentralized authentication protocol. The OpenID standard provides a framework for the communication that must take place between the identity provider and the OpenID acceptor (the relying party). This standard is seen as Single Sign On for consumers.

In the above scenario, we discussed Single Sign On for enterprise, where a company has multiple software products and to authenticate the users they maintain just one user record and a centralized authentication mechanism to authenticate and authorize. Whereas OpenID standard is seen in users perspective, where a user has accounts in multiple unrelated software applications like Google Photos, Dropbox, Facebook, Twitter etc and to get validated by these applications the user have to authenticate on corresponding systems by remembering multiple user ids and passwords, instead, openid protocol provides a way to the user to create just one account with openid and use it as authentication credential with the list of acceptors, the acceptor third party system validates this record with openid and grants access to the resource.

The term OpenID may also refer to an identifier as specified in the OpenID standard; these identifiers take the form of a unique Uniform Resource Identifier (URI), and are managed by some 'OpenID provider' that handles authentication.

A list of OpenID acceptors are AOL, Blogger, Flickr, France Telecom, Google, Amazon.com, Canonical (provider name Ubuntu One), LiveJournal, Microsoft (provider name Microsoft account), Mixi, Myspace, Novell, Orange, Sears, Sun, Telecom Italia, Universal Music Group, VeriSign, WordPress, Yahoo!, the BBC, IBM, PayPal, and Steam.


**SAML vs OpenID**

Some of the features that distinguished SAML vs OpenID

| Feature                         	| OpenId                        	| SAML                                   	|
|---------------------------------	|-------------------------------	|----------------------------------------	|
| Service provider-initiated SSO  	| Yes                           	| Yes                                    	|
| Identity provider-initiated SSO 	| No                            	| Yes                                    	|
| Identity provider discovery     	| Configured per user           	| Configured per account                 	|
| Just-in-time provisioning       	| Via back-channel SReg request 	| Directly, in the same user SSO request 	|
| Performance                     	| Slower                        	| Faster                                 	|
| Audience                        	| Consumer                      	| Enterprise                             	|

## Authorization

OAuth is an open standard authorization protocol where users grant access to websites or applications to their information on other websites instead of passing user credentials like username and password. This mechanism is used by many companies like Google, Facebook, Twitter, to share their profile information to many third party websites or applications.

OAuth is complementary to and distinct from OpenID, as here it just deals about authorization. It simply delegates the access to other websites which posses the user information.     
