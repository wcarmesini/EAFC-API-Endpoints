# Endpoint: /api/fc/clubs/info

## 📘 Description

The `/api/fc/clubs/info` endpoint retrieves detailed information about one or more FC Pro Clubs by their IDs.  
It includes club name, identifiers, region, team, and custom kit configuration.

---

## 🔗 URL

```
GET https://proclubs.ea.com/api/fc/clubs/info?platform=<platform>&clubIds=<clubIds>
```

---

## 🔒 Authentication

⚙️ **May require authentication** — depending on API access and EA session.

---

## 📤 Method

### **GET /api/fc/clubs/info**

Retrieves metadata and visual customization info for one or more clubs.

#### Query Parameters

| Parameter | Type | Required | Description |
|------------|------|-----------|-------------|
| `platform` | string | ✅ | Game platform (`common-gen5`, `ps5`, `xbsx`, etc.) |
| `clubIds` | string | ✅ | One or more club IDs, separated by commas |

#### Example Request

```http
GET https://proclubs.ea.com/api/fc/clubs/info?platform=common-gen5&clubIds=387444
```

#### Example Response

```json
{
  "387444": {
    "name": "PORTUGOAL",
    "clubId": 387444,
    "regionId": 4543827,
    "teamId": 73,
    "customKit": {
      "stadName": "Tier 3 Stadium",
      "kitId": "598020",
      "seasonalTeamId": "131397",
      "seasonalKitId": "1076404224",
      "selectedKitType": "0",
      "customKitId": "7509",
      "customAwayKitId": "7509",
      "customThirdKitId": "7511",
      "customKeeperKitId": "5005",
      "kitColor1": "15921906",
      "kitColor2": "592397",
      "kitColor3": "592397",
      "kitColor4": "592397",
      "kitAColor1": "592397",
      "kitAColor2": "15921906",
      "kitAColor3": "15921906",
      "kitAColor4": "15921906",
      "kitThrdColor1": "12706617",
      "kitThrdColor2": "33627",
      "kitThrdColor3": "396864",
      "kitThrdColor4": "2164288",
      "dCustomKit": "0",
      "crestColor": "-1",
      "crestAssetId": "99160227"
    }
  }
}
```

---

## 📋 Response Fields

| Field | Type | Description |
|--------|------|-------------|
| `<clubId>` | object | Object keyed by the club ID |
| `name` | string | Club name |
| `clubId` | number | Unique club identifier |
| `regionId` | number | Region identifier |
| `teamId` | number | Team base ID used for kit and formation data |
| `customKit` | object | Customization details for kits and stadium |

### Inside `customKit`

| Field | Type | Description |
|--------|------|-------------|
| `stadName` | string | Stadium name |
| `kitId` | string | Current kit ID |
| `seasonalTeamId` | string | Seasonal team identifier |
| `seasonalKitId` | string | Seasonal kit identifier |
| `selectedKitType` | string | Selected kit variation type |
| `customKitId` | string | Home kit ID |
| `customAwayKitId` | string | Away kit ID |
| `customThirdKitId` | string | Third kit ID |
| `customKeeperKitId` | string | Goalkeeper kit ID |
| `kitColor1..4` | string | Primary kit color values |
| `kitAColor1..4` | string | Away kit color values |
| `kitThrdColor1..4` | string | Third kit color values |
| `crestColor` | string | Crest color |
| `crestAssetId` | string | Crest asset identifier |
| `dCustomKit` | string | Custom kit toggle |

---

## 🧠 Notes

- Multiple club IDs can be passed separated by commas.  
  Example: `clubIds=12345,67890`
- This endpoint does **not** return player stats or match data (use `/api/fc/clubs/stats` or `/api/fc/clubs/matches` for that).
- Color fields are numeric representations of RGB codes used in the game’s internal color system.

---

© EAFC Pro Clubs API — Unofficial documentation.
