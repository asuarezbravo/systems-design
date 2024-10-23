# 8.4. Token-Based Authentication (JWT, OAuth)

## Introduction

Token-based authentication is a widely used method for securing stateless services and managing user authentication without maintaining server-side session state. In token-based systems, the server issues a token to the client after a successful authentication, and the client includes this token in every subsequent request. This allows the server to authenticate requests without storing session data.

In this section, we will explore two common token-based authentication methods: **JSON Web Tokens (JWT)** and **OAuth**, examining how they work and when to use each approach in stateless systems.

## JSON Web Token (JWT)

### 1. **How JWT Works**

**Definition:** JSON Web Token (JWT) is a compact, URL-safe token format that is used to represent claims between two parties. After a user successfully authenticates, the server issues a signed token containing user information (claims). The client includes this token in the header of every request, allowing the server to verify the user's identity without maintaining a session.

**Token Structure:**
- JWTs are composed of three parts: a **header**, a **payload**, and a **signature**, separated by periods (.). Example: `header.payload.signature`
  - **Header:** Contains metadata about the token, such as the signing algorithm.
  - **Payload:** Contains the claims or data, such as user ID, roles, or expiration time.
  - **Signature:** A cryptographic signature created by the server using a secret key or public/private key pair to verify the authenticity of the token.

### 2. **Benefits of JWT**

- **Stateless Authentication:** The server does not need to store session data, as all the necessary information is embedded in the token.
- **Compact and Portable:** JWTs are small and can be easily transmitted in HTTP headers or stored in client-side cookies.
- **Scalable:** Since JWTs are self-contained, they work well in distributed environments where different service instances may handle requests without sharing session state.
- **Secure:** JWTs can be signed and encrypted, ensuring the data inside the token is tamper-proof and private.

### 3. **Use Case**

JWT is commonly used in **API-based architectures** for user authentication. It is ideal for **microservices** and **single-page applications (SPAs)** where stateless authentication is needed and maintaining session state on the server is not practical.

### 4. **Security Considerations**

- **Token Expiration:** JWTs should include an expiration (`exp`) claim to limit how long the token is valid. This helps reduce the risk if a token is stolen.
- **Encryption:** For sensitive data, it’s recommended to encrypt the JWT to prevent unauthorized access to the token's contents.
- **Token Revocation:** Since JWTs are stateless, invalidating a JWT before it expires requires additional mechanisms (e.g., maintaining a blacklist of tokens).

---

## OAuth (Open Authorization)

### 1. **How OAuth Works**

**Definition:** OAuth is an open standard protocol that allows third-party services to access a user's resources without exposing their credentials. OAuth is often used to grant limited access to user accounts on services such as Google, Facebook, or GitHub without sharing the user’s password.

**Key Components of OAuth:**
- **Resource Owner:** The user who owns the data or resource.
- **Client:** The application requesting access on behalf of the resource owner.
- **Authorization Server:** The server that issues the access tokens after the user authorizes the client.
- **Resource Server:** The server that hosts the protected resources and validates access tokens to grant access to the resources.

### 2. **OAuth Flow**

1. **Authorization Request:** The client directs the resource owner (user) to the authorization server to request permission for access.
2. **User Authorization:** The user grants permission by authenticating with the authorization server.
3. **Token Issuance:** The authorization server issues an **access token** to the client.
4. **API Access:** The client includes the access token in subsequent requests to the resource server, which verifies the token and provides access.

### 3. **Benefits of OAuth**

- **Delegated Access:** OAuth allows clients to act on behalf of users without exposing user credentials, reducing the security risks of password-based authentication.
- **Fine-Grained Permissions:** OAuth allows the resource owner to control which resources the client can access and what actions it can perform, improving security.
- **Third-Party Authentication:** OAuth is commonly used for **single sign-on (SSO)**, allowing users to log into multiple services using their existing accounts (e.g., using a Google or Facebook login).

### 4. **Use Case**

OAuth is widely used for **third-party authorization** where a service needs to access user resources hosted on another platform (e.g., allowing an app to post to a user's Twitter account on their behalf). It is also used for **SSO** scenarios where users can authenticate across multiple services using the same credentials.

### 5. **Security Considerations**

- **Access Token Lifespan:** Access tokens should have a short lifespan to minimize the risk of abuse. In OAuth, **refresh tokens** can be used to request new access tokens without requiring user authentication each time.
- **Scope Restrictions:** OAuth tokens should be issued with limited scope, restricting what actions the client can perform or which resources it can access.
- **Authorization Code Flow:** The **Authorization Code Grant** is the most secure OAuth flow, as it keeps the client’s credentials safe by exchanging a temporary code for an access token.

---

## Conclusion

Token-based authentication is a powerful tool for securing stateless services. **JWT** provides a simple, stateless solution for session management, while **OAuth** offers a robust framework for third-party authorization and access delegation. Both methods play a crucial role in building scalable, secure, and user-friendly applications in distributed environments. By understanding their strengths and security considerations, you can choose the right approach for your authentication needs.

---

[Next: 8.5. Distributed Session Storage](./section_8_5.md)
