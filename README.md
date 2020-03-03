# Home-Assistant-RD4

## Uitleg

Met deze integratie kun je zien wanneer het afval door RD4 opgehaald wordt. 
Er zijn 4 sensors:
- GFT
- Restafval
- Papier
- Overig (kerstbomen)

## Installatie

**Stap 1:**

Kopieer en plak de code uit gedeelte-configuration.yaml in je eigen configuration.yaml. Belangrijk is om je eigen postcode en huisnummer in te vullen bij resource: https://rd4.syzygy.eu/1234AA/56. Vervang 1234AA door je eigen postcode en 56 door je eigen huisnummer. Doe dit voor alle 4 links in de code.

**Stap 2:**

Check of je config valid is en herstart Home Assistant

**Stap 3:**

Maak een "oogopslag kaart" (of glance card, in het Engels) aan via de GUI. Switch naar de code-editor en plak de volgende code:

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

## Verdere mogelijkheden

Je zou nu een automation kunnen maken. Tussen 0:00 en 3:00 's nachts is de link waarop de informatie van RD4 staat niet beschikbaar. Zelf heb ik een automation staan tussen 0:00 en 4:00. Springt een sensor op 'JA', dan stuurt HA mij een appje. Bij het opstaan zal ik altijd herinnerd worden en nooit meer afval vergeten buiten te zetten!
