# Arfon's Fantastic Exoplanets

This is a test repository for the MAST Lists service. This repository contains a `List` definition, `list.yaml` which defines the properties of the List, together with the available properties for `Things` in the `List`:

```YAML
name: "Arfon's Fantastic Exoplanets"
description: "Arfon's list of exoplanet candidates. Hand-picked just for you."
properties:
  - name: "Name"
    kind: "String"
    units: ""
    required: "true"
    group: "Default"
    key: "default_name"
```

`List` items (known as `Things`) are in the `things` folder and follow a format of one `Thing` per YAML file. `Thing` definition files can follow any naming convention. The filename for a `Thing` is not special but in this case we're using the filename to make it more straightforward to identify the exoplanet candidate we're describing (e.g. `wasp-14-b.yaml`)

`Thing` YAML definitions may only contain properties that are already defined on the parent `List` in `list.yaml`:

```YAML
properties:
  - property_key : "default_name"
    property_value: "WASP-14 b"
    origin: "http://arxiv.org/abs/1402.6534"
  - property_key : "default_star_name"
    property_value: "WASP-14"
    origin: ""
  - property_key : "orbital_parameters_planet_mass"
    property_value: "7.69"
    origin: "http://adsabs.harvard.edu/abs/2006ApJ...646..505B"
```

## Data Validation

[![Build Status](https://travis-ci.org/arfon/exoplanet_list.svg?branch=master)](https://travis-ci.org/arfon/exoplanet_list)

This List repository knows how to validate itself by running the tests in `list_test.rb`. Any modifications to the `Thing` YAML files or the `List` definition in `list.yaml` will be tested by Travis-CI.
