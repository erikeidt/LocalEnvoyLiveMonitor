Local Envoy Live Monitor by Erik Eidt (c) 2025, version 0.1

Project location: https://github.com/erikeidt/LocalEnvoyLiveMonitor

Live at https://erikeidt.github.io/LocalEnvoyLiveMonitor.html

* no advertising
* no internet access used or needed by this web page; 
* no data captured or stored.

Shows energy production/consumption for Solar, Grid, Battery and Home, live.&nbsp; Here's a screen capture.

v0.1
![LELM](https://github.com/user-attachments/assets/2e54d9a9-6a80-41fc-8285-03312339b1a9)

v0.1.7
![LELM](https://github.com/erikeidt/LocalEnvoyLiveMonitor/blob/main/Picture1.png)

Requires CORS override so that this page can make local enquiries into your Envoy (see more below).

For Solar & Battery monitoring, this also requires an easily obtained Entrez Bearer token from Enphase, though Tariff monitoring does not. Your system has to be on your local network, identified as "https://envoy.local".

There are two already existing monitoring methods from Enphase, one is the "Live Status" from the App or Web, and the other is the local Envoy's built-in website at "https://envoy.local".

Compared with the "Live Status" monitor at the Enphase web, this one runs 100% on your local network: no internet services are used or required.  This means it will work when the internet is down at either your end or theirs (Enphase's). Where as "Live Status" has a 15 minute time out (though you can immediately restart it), this one will run until you stop it (or it gets unhandled networking errors).

Compared with the Envoy's built-in website, Enphase Monitor by Erik Eidt provides practically instant updates.  It also shows what power is going where, and tariff information such as schedule period, mode key and upcoming changes.  Instead of reporting tariff rates, this monitor reports the low-level net-effect called "Schedule Mode Key" that the Envoy computes/schedules based on your tariff selection.

A graphical (SVG) display and a textual chart can both be enabled or disabled.

In the graphical display, a - sign indicates power production, e.g. for battery: discharging, for grid: importing power; while a + sign indicates consumption, e.g. for battery: charging, for grid: exporting

Known Tariff Schedule Mode Keys are:

* ID	Idle (i.e. no charge/discharge)
* ZN	Zero Net (i.e. self consumption behavior)
* CG	Charge From Grid
* DG	Discharge to Grid
* ND	No Discharge
* DL	Discharge to Load
* CP	Charge From PV
* HEMS Discharge	
* HEMS Charge	
* FCR	Charge or discharge
* HEMS Charge from Grid

About CORS
----------

CORS is a security feature that prevents one website from going through your browser and using some already open channel to another website for malicious intent, and sadly also for any and all legitimate purposes.  For CORS permission to use https:/envoy.local, we would have to modify https://envoy.local, which isn't going to happen.  Instead, we can use a CORS override addon/extension to the brower.  You can find a CORS override extension from your browser's webstore.

CORS override needs to be configured so that this page has access to the envoy.  I use chrome on my desktop, and install a general CORS override.  To make this more secure, I create a new User Profile added to the browser, and install the CORS override there.  I don't run any other websites or web pages from that User profile except this one.  And I don't install the CORS override extension anywhere except that new User profile.

Even after installing a CORS override extension, you may need to visit https://envoy.local directly from that new User Profile, and if that doesn't help this monitor get access, then also sign in there before using your token with this monitor

If this monitor gets errors, hopefully refreshing the page will fix it.

To make this monitor truly local, you're welcome to download this page to your local machine and run it from there (though of course, it won't automatically update when improvements are made here).

(I'm using "Cross Domain CORS" which disabled CORS and allows this page access to the envoy's local REST server.)


