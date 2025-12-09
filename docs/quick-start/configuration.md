---
title: "Configuration"
sidebar_position: 2
slug: /quickconfiguration
---

# Configuration

## Initial Setup (Onboarding)

## Step 1: Select Your Business Type

### Store
- Recommended for: Retail shops, boutiques, hardware stores, electronics shops, Bitcoin merchandise stores

### Restaurant
- Recommended for: Restaurants, cafes, food trucks, bars, coffee shops

## Step 2: Create Your Admin Account

This step creates the primary administrator account for your POS system. This account will have full access to all features and settings.

### Required Fields

### User Name

**User Name Example**:
```
Admin
```

### PIN (4-digit)

**PIN Example**:
```
1243
```

### Password

**Password Example**:
```
Ambrosia2025!
```

## Step 3: Enter Your Business Details

This step collects important information about your business that will appear on receipts, reports, and throughout the system.

**Note**: The only required field is `Store Name`.

### Store Name

**Store Name Example**:
```
Lightning Electronics
```

#### Address
#### Phone
#### Email
#### RFC (Tax ID)
#### Currency
#### Store Logo

### Click the Finish button to complete the setup

Congratulations! You've successfully configured your Ambrosia Point of Sale system.

### What Happens Next

After completing the setup wizard:
1. The system saves your configuration
2. Your database is initialized with your business information
3. Your admin account is created
4. You're redirected to the login screen

## First Login

**Login Steps:**

1. **Select Your User**

2. **Enter Your PIN**

3. **Sign In**

## Step 3: Open a channel/Get inbound liquidity
By default, phoenixd will request 2Msat of inbound liquidity from the ACINQ LSP, whenever it runs out of inbound liquidity. This of course includes when you first start the node and receive your very first payment. ACINQ charges 1% of the amount of inbound liquidity requested, which is 20ksat (plus the mining fee). Since 20ksat is about US$20 at the time of writing, and since we don't need this much inbound liquidity for a workshop, we instead configure phoenixd not to request inbound liquidity.

*(Note: if you actually want 2M sats of inbound liquidity, just omit this. If you go this route, you should send ~25ksats as your first payment, most of which will be taken by ACINQ for the fee)*:

Edit the phoenixd config:
```
sudo nano "$(docker inspect -f '{{ range .Mounts }}{{ if eq .Destination "/phoenix" }}{{ .Source }}/.phoenix/phoenix.conf{{ end }}{{ end }}' phoenixd)"
```
Add these two lines to the config file (this should be fine as long as mining fees are lower than 5k):
```
auto-liquidity=off
max-mining-fee=5000
```

Now save and exit (ctrl+s, ctrl+x).

Restart your container to pick up the new settings:
```
docker restart phoenixd
```

Next, we deposit 5ksats into our node:

- On the Dashboard, go to Wallet

- Enter your password

- Enter amount e.g.

```
5000
```

- Add a description (Optional) e.g. 

```
Channel open
```

- Scan it with your lightning wallet and pay
