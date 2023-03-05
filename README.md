### DEPRECATED AND ARCHIVED

Bulb Energy nearly collapsed and went into 'Special Administration' in late 2021. As of early 2023, all customers were being moved over to Octopus Energy.

Consequently, this repository is now being archived. Use https://github.com/BottlecapDave/HomeAssistant-OctopusEnergy instead if you are now an Octopus Energy customer.

## About 

A Home Assistant custom component to retrieve your current [Bulb Energy](http://bulb.co.uk) tariff, based on postcode and payment plan.

## Installation
Copy the contents of this repository into your Home Assistant custom_components/bulb_energy directory.

Place this into configuration.yaml, edited appropriately:

```
sensor:
  - platform: bulb_energy
    postcode: "SA1 1AZ" # UK postcode
    payplan: "monthly" # or legacyPrepay or smartPayg
    eco7: false # or true
```
Reload Home Assistant.

Your tariff will now be available as a sensor, called ```sensor.kwh_rate```. This is usable in the Home Assistant Energy Dashboard.

## How It Works
Takes your postcode and payment plan, submits it via the bulb.co.uk GraphQL API at https://join-gateway.bulb.co.uk/graphql and returns the current tariff. No personal data other than what you provide in the above configuration is sent to Bulb.

To avoid impacting the Bulb API, this component only checks on startup and then every 12 hours thereafter.

## Credit

All the heavy lifting Bulb/GraphQL code is done by https://github.com/Shellywell123/Cost_2_Mine/

I just wrapped some of it in an HA sensor.
