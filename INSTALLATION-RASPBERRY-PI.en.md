# Installing Sally Home Connect on a Raspberry Pi

🇫🇷 [Version française](INSTALLATION-RASPBERRY-PI.md)

Sally lives on a Raspberry Pi: a small box that stays on day and night, with no screen or keyboard, and uses very
little power.

Installing requires **no commands**: you write Sally to a micro-SD card, put the card in the Raspberry Pi, plug it in,
and that's it.

## What you need

- a **Raspberry Pi 4** (2 GB of memory or more) or a **Raspberry Pi 5**, with its official power supply;
- a **micro-SD card** of 16 GB or more (32 GB recommended), and a card reader for your computer;
- a **network cable** to connect it to your router (required: Wi-Fi cannot be set up from this image yet);
- your Zigbee or EnOcean **USB sticks**, if you have devices to control:

| Technology | Supported USB sticks |
|---|---|
| Zigbee | Sonoff ZBDongle-P, Sonoff ZBDongle-E, ConBee II |
| EnOcean | EnOcean USB 300 |

## 1. Download

1. In the [**Releases**](../../releases/latest) tab, download the latest version's file:

   ```text
   sally-home-connect-2.0.0-raspberry-pi.img.xz
   ```

   Do not unzip it: the software in the next step does that.
2. Install **Raspberry Pi Imager**, the free official software from the Raspberry Pi Foundation:
   https://www.raspberrypi.com/software/

## 2. Write Sally to the card

1. Put the micro-SD card in your computer. If Windows offers to format it: **decline**.
2. Open **Raspberry Pi Imager**.
3. **Device**: choose your Raspberry Pi model.
4. **Operating system**: scroll to the bottom and choose **"Use custom"**, then the downloaded
   `sally-home-connect-…-raspberry-pi.img.xz` file.
5. **Storage**: choose your micro-SD card. Careful: everything on it will be erased.
6. If Imager offers to **customise** the system, skip it: there is nothing to set.
7. Confirm, then wait for writing and verification to finish (5 to 10 minutes).

## 3. Start

1. Put the card in the Raspberry Pi.
2. Plug in the **network cable** to your router, your **USB sticks**, then the **power supply** last.
3. Wait **3 minutes**: on first start, the Raspberry Pi sets itself up.

## 4. Open Sally

On a computer or phone connected to the same router, open:

```text
https://sally.local
```

The first time, your browser shows a warning: this is normal, Sally has its own certificate, created at your home.
Choose **"Advanced"** then **"Continue"**.

**If the address does not open** (some antivirus software and phones do not know `.local` addresses):

- try the **fixed address** Sally sets for itself: your network ending in **.200**, most often
  `https://192.168.1.200` (or `https://192.168.0.200`, depending on your router);
- or look at your **router's device list** (its phone app or settings page): the Raspberry Pi appears there as
  **sally**, with its address (for example `192.168.1.39`). Then type `https://` followed by that address;
- if you tried Sally on Windows: **Settings → My Raspberry Sally → Search**, then **Open**.

Then keep that address in your bookmarks.

## 5. First start

Sally welcomes you with a short wizard:

1. the **language**;
2. **bring over the home from your Windows trial** (if you tried Sally on your computer): on the computer,
   **Settings → My Raspberry Sally → Send my home**. Rooms, devices, routines, Zigbee network and access codes move
   to the Raspberry Pi: no need to pair your devices again. Then unplug the USB sticks from the computer, plug them
   into the Raspberry Pi, and restart it (**Settings → Raspberry Pi → Restart**);
3. otherwise, your **access code**: without it, nobody can control your home, even on your Wi-Fi. Write down the
   **backup code** Sally shows: you need it if you forget your code;
4. your **home's name**;
5. **Sally's address**, to keep. On your phone, open it then **"Add to Home screen"**: Sally then opens like an app.

Next: **Settings → Add a device**. Sally's **Help** tab explains every feature.

## Controlling your home from outside

Sally needs no online service to be controlled from outside: your phone connects straight to your router through a
**VPN**, an encrypted tunnel. You need a router that can act as a "VPN server" (the Freebox, for example).

1. **Ask your internet provider for a fixed IP address.** Without it, your router's address changes from time to time
   and the VPN can no longer find it. With Free: subscriber area → **Ma Freebox** → **Demander une adresse IP fixe V4
   full-stack** (free of charge), then restart the router.
2. In Sally: **Settings → Raspberry Pi → Fixed address for remote access** must be on. Write down the address shown
   (for example `https://192.168.1.200`).
3. In your router's page, open **VPN server** (careful: not "VPN client", which does the opposite), choose
   **WireGuard**, turn it on, then create one user per phone.
4. On the phone, install the free **WireGuard** app, tap **+** then **Scan from QR code**, and scan the user's code
   shown by the router.
5. When you are out: turn on the VPN in WireGuard, then open the address from step 2 (`sally.local` does not work
   through the VPN).

## Shutting down safely

Do not unplug the Raspberry Pi while it is writing: **Settings → Raspberry Pi → Shut down**, wait until its small
green light stops blinking, then unplug it.

## Trial and licence

Sally works fully for a **30-day free trial**. Each Raspberry Pi has its own **installation code**: its licence is
made for it. Online sales open soon; until then, to keep using Sally after the trial, write to
**sallyhomeconnect@gmail.com**.

## Updates

If you allow Sally to go online (**Settings → Internet**), it tells you about a new version in **Settings → Updates**.
Tap **Install the update**: Sally checks it, installs it and restarts (about one minute). If the new version does not
start, it goes back to the previous one by itself.

## Privacy

Nothing leaves your home: no online account, no cloud, and Sally works even when the Internet is down. SSH access to
the Raspberry Pi is off.

## Troubleshooting

- **Sally does not open after 5 minutes**: check that the Raspberry Pi's green light blinks from time to time, that
  the network cable is plugged into the router, then unplug and plug the power supply back in.
- **A question**: sallyhomeconnect@gmail.com
