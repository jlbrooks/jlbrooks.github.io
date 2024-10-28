---
layout: post
title: Controlling our heat pump with home assistant
subtitle: 
tags: [home-automation]
comments: true
---

Kaitlin’s office has a heat pump unit for both heating and cooling. It works alright, but during the winter it can take some time to heat up the space in the morning. With temperatures starting to drop, I got around to a project I’ve been meaning to take on for a while now: Integrating the heat pump controls with our Home Assistant setup.

Our heat pump, the Mitsubishi Electric `MSZ-FE18NA`, is controlled by an IR remote. Some cursory googling led me to this Youtube tutorial, and the setup looked similar enough to take a chance on the suggested hardware:

- The tutorial: [https://www.youtube.com/watch?v=2NKnDzTW1Iw](https://www.youtube.com/watch?v=2NKnDzTW1Iw)
- The IR controller: [The Broadlink RM Mini 3](https://www.amazon.com/dp/B07K2DHXB6?th=1)

The Broadlink controller was easy to configure with the app (quickly deleted after the device was connected to wifi and connected to HA). I installed the [SmartIR](https://github.com/smartHomeHub/SmartIR/tree/master) integration, but quickly ran into the first challenge when trying to configure the device for our heat pump: No one had discovered [the codes](https://github.com/smartHomeHub/SmartIR/blob/master/docs/CLIMATE.md#mitsubishi-electric) for this particular model!

I tried a few similar Mitsubishi model codes but they didn't quite work. Some more research led me to this lovely tool: [Broadlink Listener](https://github.com/gpongelli/broadlink-listener). Specifically built for creating SmartIR configurations, it discovers a Broadlink device, puts it into listening mode, prompts you to send various signals using your remote, and spits out a command configuration file.

I found the [user manual](https://www.rfwel.com/downloads/manuals/KMO8C-User-Manual.pdf), set up a template configur ation, started up the tool, and got to work generating the various commands. This proved to be... extremely tedious. Every single unique combination of device settings is its own unique code, and thus must be generated individually. Our heat pump has:
- 27 temperature values (61-88 F)
- 3 modes (auto, cool, heat)
- 4 fan settings (auto, low, medium, high)
- 7 horizontal vane settings (auto, high to low, swing)
- 7 vertical vane settings (left to right, swing)

That's 15,876 unique codes! I'm sure that there is some logical internal coding used, but this tool/SmartIR did not attempt to decode that - it just listed and repeated each individual code.

Luckily we don't really need all of them, so I initially set out to configure:
- 27 temperature values
- 2 modes (cool and heat)
- 4 fan settings
- 7 horizontal vane settings

So... 1,512 codes. This math was done in hindsight, and as I started through the "cool" settings I quickly had regrets. I put on a podcast and powered through, but after finishing "cool" in 30 minutes or so I was not motivated to fully configure "heat". I settled for just configuring all 27 temp values for auto fan and vane settings, which was enough to start using the integration.

I input the configuration and it worked like a charm. It even connected through the HomeKit bridge, though the HomeKit integration isn't perfect - it doesn't know how to handle the discrete fan settings or the vane settings at all.

<figure>
  <img src="{{site.url}}/assets/img/2024-10-27-heat-pump-home/config.png" alt="HA config"/>
  <figcaption>The home assistant config</figcaption>
</figure>

As I didn't complete the SmartIR config the main project won't accept it, but I'll upload my partial config here for posterity: [Github link]()