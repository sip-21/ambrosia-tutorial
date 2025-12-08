---
title: "Quick Start"
sidebar_position: 2
slug: /quickstart
---

## Installation

### Minimum Requirements
- **OS**: Linux (Ubuntu 20.04+, Debian 10+), macOS 10.15+, or Windows 10/11
- **RAM**: 2GB minimum, 4GB recommended
- **Disk Space**: 2GB free space
- **Network**: Internet connection

## Step 1: Install Docker

### For Linux (Ubuntu/Debian)

Open your terminal and run the following commands:

```bash
# Update package list
sudo apt update

# Install Docker
sudo apt install curl docker.io

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Add your user to the docker group (allows running Docker without sudo)
sudo usermod -aG docker $USER

# Refresh your user session to apply group changes
su - $USER
```

### For macOS

1. Download Docker Desktop for Mac from [docker.com](https://www.docker.com/products/docker-desktop)
2. Open the downloaded `.dmg` file
3. Drag Docker to your Applications folder
4. Launch Docker from Applications
5. Follow the setup wizard
6. Docker will start automatically

### For Windows

1. Download Docker Desktop for Windows from [docker.com](https://www.docker.com/products/docker-desktop)
2. Run the installer
3. Follow the installation wizard
4. Restart your computer when prompted
5. Launch Docker Desktop from the Start menu
6. Wait for Docker to start (you'll see a green icon in the system tray)

### Verify Docker Installation

After installing Docker, verify it's working correctly:

```bash
docker --version
```

You should see output like:
```
Docker version 28.2.2, build 28.2.2-0ubuntu1
```

If you see the version number, Docker is installed correctly!

## Step 2: Install Git (If Not Already Installed)

Git is needed to download the Ambrosia source code from GitHub.

### Check if Git is Installed

```bash
git --version
```

If you see a version number, Git is already installed. Skip to Step 3.

### Install Git

**For Linux (Ubuntu/Debian):**
```bash
sudo apt install git
```

**For macOS:**
```bash
brew install git
```
(Requires Homebrew. If you don't have Homebrew, download Git from [git-scm.com](https://git-scm.com))

**For Windows:**
Download and install from [git-scm.com](https://git-scm.com/download/win)

## Step 3: Clone the Ambrosia Repository

Now we'll download the Ambrosia source code from GitHub.

### Navigate to Your Preferred Directory

First, decide where you want to install Ambrosia. For example:

```bash
# Option 1: Install in your home directory
cd ~

# Option 2: Install in a specific projects folder
cd ~/projects
```

### Clone the Repository

Run the following commands to download Ambrosia:

```bash
# Clone the repository from GitHub
git clone https://github.com/olympus-btc/ambrosia.git

# Navigate into the project directory
cd ambrosia
```

### Verify the Files

Check that you're in the correct directory with the project files:

```bash
ls
```

You should see files including:
- `docker-compose.yml` (Docker configuration)
- `README.md` (Project documentation)
- Various folders like `server`, `client`, etc.

## Step 4: Build and Start the Containers

From the `ambrosia` directory, run:

```bash
docker-compose up -d
```

**This process may take 3-5 minutes on first run**, especially on slower internet connections. Subsequent starts will be much faster.

## Step 5: Access Ambrosia

1. Open your web browser (Chrome, Firefox, Safari, Edge, etc.)
2. Navigate to: **http://localhost:3000**
3. You should see the Ambrosia onboarding screen

### Stopping Ambrosia

When you're done using Ambrosia, you can stop the containers:

```bash
# Stop all containers
docker-compose stop
```

## Configuration

## Initial Setup (Onboarding)

**What You'll Need**:
- Your business information (name, address, phone, email)
- Your tax ID (RFC) if applicable
- A business logo image (optional but recommended)
- A secure password for your admin account

## Step 1: Select Your Business Type

### Store
- Recommended for: Retail shops, boutiques, hardware stores, electronics shops, Bitcoin merchandise stores
- Focus: Product-based sales with inventory management
- Features optimized for: SKU tracking, stock management, product categories

### Restaurant
- Recommended for: Restaurants, cafes, food trucks, bars, coffee shops
- Focus: Food service and hospitality
- Features optimized for: Table management, order modifications, kitchen workflow

## Step 2: Create Your Admin Account

This step creates the primary administrator account for your POS system. This account will have full access to all features and settings.

### Required Fields

#### User Name
- Enter your full name or the name of the primary administrator
- This will appear in the system and on reports
- Can be changed later in the Users section

**User Name Example**: `Admin`

#### PIN (4-digit)
- Create a secure 4-digit PIN code
- This PIN allows quick access to the system during daily operations
- Will be used every time you log in

**PIN Example**: `1243`

**Important**: Choose a PIN that's:
- Easy for you to remember
- Not obvious (avoid 0000, 1234)
- Unique to this account
- Kept confidential

#### Password
- Create a strong password for your admin account
- This provides an additional layer of security
- Used for accessing sensitive settings and features
- Used to access your wallet

**Password Requirements**:
- Minimum 8 characters
- Must include at least one uppercase letter (A-Z)
- Must include at least one lowercase letter (a-z)
- Must include at least one number (0-9)
- Must include at least one special character (!@#$%^&*)

**Password Example**: `Ambrosia2025!`

## Step 3: Enter Your Business Details

This step collects important information about your business that will appear on receipts, reports, and throughout the system.

### Required Fields

#### Store Name
- Enter your official business name
- This appears on receipts and customer-facing materials

**Store Name Example**: `Lightning Electronics`

#### Address
- Enter your complete business address
- Include street, number, city, state, and postal code
- Used for receipts and official documentation

**Address Example**: `123 Main Street, Guadalajara, Jalisco, 44100`

#### Phone
- Enter your business contact phone number
- Include country code if applicable
- Customers may use this to contact you

**Phone Example**: `(555) 123-4567`

#### Email
- Enter your business email address
- Used for system notifications and customer contact
- Must be a valid email format

**Email Example**: `contact@yourstore.com`

#### RFC (Tax ID)
- Enter your Mexican tax identification code (RFC)
- Must be exactly 13 characters
- Format: 4 letters + 6 numbers + 3 alphanumeric characters
- Example: `XAXX010101000`
- Required for tax compliance and official receipts

**Email Example**: `XAXX010101000`

#### Currency
- Select your primary business currency
- Default: MXN (Mexican Peso)
- This is the currency displayed in prices throughout the system
- Bitcoin prices convert automatically based on this currency

**Available Currencies**:
- MXN (Mexican Peso) - Default
- USD (US Dollar)
- EUR (Euro)
- Other currencies may be available depending on your configuration

#### Store Logo (Optional)
- Upload an image file representing your business
- This logo appears on receipts and in the interface
- Creates a professional appearance
- If no logo is uploaded then the `Ambrosia` logo will be deafult

## Step 4: Review Your Setup Summary

This final step shows you all the information you've entered, allowing you to verify everything is correct before completing the setup.

### Click the Finish button to complete the setup

## Setup Complete!

Congratulations! You've successfully configured your Ambrosia Point of Sale system.

### What Happens Next

After completing the setup wizard:
1. The system saves your configuration
2. Your database is initialized with your business information
3. Your admin account is created
4. You're redirected to the login screen

### First Login

Now it's time to access your system for the first time.

**Login Steps:**

1. **Select Your User**
   - You'll see a list with your admin user
   - Click on your username to select it
   - This is the account you just created

2. **Enter Your PIN**
   - A PIN pad will appear
   - Enter the 4-digit PIN you created during setup
   - Make sure to enter it correctly

3. **Sign In**
   - Click the **Sign In** button
   - The system will verify your credentials
   - You'll be authenticated and logged in

## Products Management

# Managing Products

Learn how to add, edit, and manage your inventory in Ambrosia's Point of Sale system.

## Overview

The Products section is where you manage your entire inventory. You can add new products, organize them by categories, set prices, track stock levels, and upload product images. This is the foundation of your POS system - everything you sell starts here.

## Processing Sales (Cart)

Learn how to use the Cart system to process sales and accept payments, including Bitcoin Lightning Network payments.

## Overview

The Cart is where all sales transactions happen. It's your main Point of Sale interface where you can browse products, add items to a customer's order, adjust quantities, select payment methods, and complete transactions. The Cart supports multiple payment methods including Cash, Credit Card, Debit Card, and Bitcoin via Lightning Network.

## Other Features