---
description: Use this guide to integrate the OneField platform with DJI Cloud or FlightHub.
---

# DJI integration guide

## 📋 **Prerequisites**

* DJI drone (e.g., Mavic 3, Matrice 300 RTK)
* DJI Developer Account: developer.dji.com
* Access to DJI Cloud API or FlightHub 2
* OneField account with admin privileges
* Internet-connected ground station or mobile device

***

## Setup and Sync

You can setup and sync with the OneField platform using a Cloud API key.

### 🔐 **Step 1: Obtain DJI API Credentials**

1. Log in to your DJI Developer account.
2. Create a new application under **Cloud API**.
3. Note your:
   * `App Key`
   * `App Secret`
   * `Webhook URL` (optional for event push)
4. Enable the following scopes:
   * `drone.read`
   * `drone.control`
   * `mission.upload`
   * `telemetry.stream`

***

### 🔗 **Step 2: Connect DJI to OneField**

1. In the OneField dashboard, go to **Integrations > DJI**.
2. Click **Connect DJI Account**.
3. Enter your DJI `App Key` and `App Secret`.
4. Authorize OneField to access your DJI drone data.
5. Once connected, your DJI drones will appear under **Fleet > Drones**.

***

### 🧭 **Step 3: Sync Flight Data & Missions**

* OneField will automatically pull:
  * Drone status (battery, GPS, firmware)
  * Flight logs and telemetry
  * Live video (if supported)
* You can now:
  * Upload pre-programmed missions from OneField to DJI drones
  * Monitor live telemetry and video feeds
  * Trigger remote override commands

***

### 🔄 **Step 4: Enable OTA Updates**

1. Navigate to **Fleet > Settings > OTA Updates**.
2. Enable **Auto-Update** or schedule updates manually.
3. OneField will push firmware updates via DJI’s OTA system.

***

### 🧪 **Step 5: Test the Integration**

* Create a test mission in OneField.
* Assign it to a DJI drone.
* Launch the mission and monitor it via **Live View**.
* Use the **Remote Override** feature to test manual control.

***

## 🛟 Troubleshooting

* **Drone not appearing?** Ensure it’s online and linked to your DJI account.
* **Live feed not working?** Check camera permissions and network settings.
* **API errors?** Verify your DJI credentials and scopes.
