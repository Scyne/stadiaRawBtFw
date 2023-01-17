# Stadia Bluetooth Mode Firmware

![](https://raw.githubusercontent.com/Scyne/stadiaRawBtFw/main/img/Finish_Bluetooth_enabled.svg)

So I pulled the bin files from the google updater because I want to make sure it's saved somewhere...

...and also because I REALLY want haptics but I'm too smooth brained to edit the firmware myself.

## What I saw...

It looks like when you do the initial verification, chrome has you enter a manual bootloader flash mode:

### How to unlock bootloader on the Stadia Controller

- First Press and hold the option (three dots) button on the controller while you connect the controller to a computer.
  ![](https://raw.githubusercontent.com/Scyne/stadiaRawBtFw/main/img/Unlock_Option_Plug.svg)

- Next you press the option, assistant, A, and Y buttons at the same time
  ![](https://raw.githubusercontent.com/Scyne/stadiaRawBtFw/main/img/Unlock_Four_buttons.svg)

- Finaly the webapp has you select the controller. The Stadia Controller name should be “SP Blank RT Family”. The webapp states that the name could instead read as “Stadia Controller” or “USB COMPOSITE DEVICE”.
  ![](https://raw.githubusercontent.com/Scyne/stadiaRawBtFw/main/img/Chrome_dialog_Verify_en-US.svg)

### The flash process

At that point the bootloader is "unlocked" and chrome downloads the following two `.bin` files:

- [bruce_pvt_a_prod_signed.bin](https://github.com/Scyne/stadiaRawBtFw/blob/main/bruce_pvt_a_prod_signed.bin)
- [restricted_ivt_flashloader.bin](https://github.com/Scyne/stadiaRawBtFw/blob/main/restricted_ivt_flashloader.bin)

At that point you get the message telling you that the download was complete and tells you to select the device again as noted above, with the added distinction that the device should be displayed as “USB COMPOSITE DEVICE”. At this point then following `.bin` is fetched and executed:

- [flashloader_fcb_get_vendor_id.bin](https://github.com/Scyne/stadiaRawBtFw/blob/main/flashloader_fcb_get_vendor_id.bin)

It looks like all of those files can be fetched from: [https://stadia.google.com/controller/data/](https://stadia.google.com/controller/data/)`filename`

## Where do we go from here?

I dont know... Man I'm just someone that realy likes the controller and thinks that someone smarter than me will beable to fork this repo and build a standalone flash tool so that future users can update old controlers for years to come...

I was an all in user of [OnLive](https://en.wikipedia.org/wiki/OnLive) and when Sony killed it I was devistated, ever since I've been careful around cloud services like this to avoid getting burned. When Stadia came around I realy wanted it to be thee thing, but googlee never wanted to give this service a chance... It's a shame that it's pasionate and innovative developers were never realy given the chance to create something truely great. meh... at least we got a free, great feeling controller out of the deal.

My dream is that with time new features can get added to the code like haptics and audio over BT. I dont know what you can or cannot see in the firmware or what the hardware can or cannot control but hopefully I've done my part to help.

Anyway, See y'all.
