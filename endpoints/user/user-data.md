# Endpoint: /user-data

## 📘 Description

The `/user-data` endpoint returns information about the EA account associated with the authentication token.  
It provides profile details, account status, and connected platforms (such as PSN, Xbox, or Origin).

---

## 🔗 URL

```
GET https://www.ea.com/user-data
```

---

## 🔒 Authentication

✅ **Required** — You must be logged into EA accounts.


## 📤 Method

### **GET /user-data**

Retrieves detailed information about the authenticated user.

#### Response Example

```json
{
  "authenticated": true,
  "originName": "user",
  "age": 25,
  "country": "BR",
  "status": "ACTIVE",
  "pid": 9999999999999,
  "eid": "osdfohgsdhfgkshdfhlg",
  "email": "email@email.com",
  "securityChallengeVerified": false,
  "entitlements": null,
  "connectedPlatforms": [
    { "gamerTag": "user", "platform": "ps" },
    { "gamerTag": "user", "platform": "origin" }
  ],
  "uniqueConnectedPlatforms": [
    { "gamerTag": "user", "platform": "ps" },
    { "gamerTag": "user", "platform": "origin" }
  ],
  "clientAccessToken": "sdfsdfsdfsdfsdfasdjfhposdfn~glsdfgnsldfçg"
}
```

---

## 📋 Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `authenticated` | boolean | Whether the user is authenticated |
| `originName` | string | EA/Origin username |
| `age` | number | User's age |
| `country` | string | Country code (ISO 3166-1) |
| `status` | string | Current EA account status |
| `pid` | number | Internal player ID |
| `eid` | string | Encoded unique identifier |
| `email` | string | Registered email address |
| `securityChallengeVerified` | boolean | Indicates if security challenge has been verified |
| `entitlements` | array/null | List of entitlements or licenses (if any) |
| `connectedPlatforms` | array | Connected platforms (PS, Xbox, Origin, etc.) |
| `uniqueConnectedPlatforms` | array | Unique linked platforms |
| `clientAccessToken` | string | Temporary access token for other EA services |

---

## 🧠 Notes

- This endpoint is available only for users with an active EA session.  
- Some fields (like `entitlements`) may return `null` depending on the account.  
- The `clientAccessToken` can be reused in subsequent calls to game-specific endpoints.

---

© EAFC API Endpoints — unofficial documentation.
