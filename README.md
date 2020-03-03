# Home-Assistant-RD4

![HA-Glance](https://github.com/Pr0gr4mm3r/Home-Assistant-RD4/blob/master/HA-glance.png)

## Uitleg / Explanation

Met deze integratie kun je zien wanneer het afval door RD4 opgehaald wordt. 
Er zijn 4 sensors:
- GFT
- Restafval
- Papier
- Overig (kerstbomen)

Using this integration you can see if the trash is going to be picked up.
There are 4 sensors:
- GFT
- Restafval
- Papier
- Overig (kerstbomen)

## Installatie / Instalation

**Stap 1 / Step 1: **

Kopieer en plak de code uit gedeelte-configuration.yaml in je eigen configuration.yaml. Belangrijk is om je eigen postcode en huisnummer in te vullen bij resource: https://rd4.syzygy.eu/1234AA/56. Vervang 1234AA door je eigen postcode en 56 door je eigen huisnummer. Doe dit voor alle 4 links in de code.

Copy / paste the code from gedeelte-configuration.yaml into your own configuration.yaml. It's important to fill in your own postal code and housenumber at resource: https://rd4.syzygy.eu/1234AA/56. Replace 1234AA by your own postal code and 56 by your own housenumber. You have to do this for all the (4) links in the code.

**Stap 2 / Step 2: **

Check of je config valid is en herstart Home Assistant.

Check if your config is valid and reboot Home Assistant.

**Stap 3 / Step 3: **

Maak een "oogopslag kaart" (of glance card, in het Engels) aan via de GUI. Switch naar de code-editor en plak de volgende code:

Create a glance card using the GUI. Switch to the code-editor and paste the following code:

```type: glance
entities:
  - entity: sensor.gft
    icon: mdi:fruit-citrus
  - entity: sensor.overig
    icon: mdi:pine-tree
  - entity: sensor.papier
    icon: mdi:note-outline
  - entity: sensor.restafval
    icon: mdi:delete-empty
title: Afval naar buiten?
```

## Verdere mogelijkheden / More possibilities

Je zou nu een automation kunnen maken. Tussen 0:00 en 3:00 's nachts is de link waarop de informatie van RD4 staat niet beschikbaar. Zelf heb ik een automation staan tussen 0:00 en 4:00. Springt een sensor op 'JA', dan stuurt HA mij een appje. Bij het opstaan zal ik altijd herinnerd worden en nooit meer afval vergeten buiten te zetten!

You can now make an automation which checks if the trash will be picked up. Between 0:00 and 3:00 at night, the link where RD4 updates their trash days is unavailable. Personally I have an automation which checks the states of the sensors between 0:00 and 4:00. If a sensor equals "JA" (this means 'yes' in Dutch), I get a notification from HA. When I get up in the morning, I will never forget to put out the trash anymore

## Donatie / Donation

Vind je dit een leuk project? Beloon mijn werk via bitcoin! Elke bijdrage wordt gewaardeerd, hoe klein dan ook! :-)

Do you like this project? Every (small) donation to my bitcoin address is appreciated! :-)

**BTC address:** 1NVpQZJjvwi4sRKvZWg2zBbxEBAwfgZ8nf
