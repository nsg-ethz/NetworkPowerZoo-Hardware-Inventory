# Network Power Zoo Hardware Inventory

This repository contains structured data for router models from multiple manufacturers. The data was aggregated from [NetBox Device Type Library](https://github.com/netbox-community/devicetype-library/tree/master), LLM-assisted parsing of datasheets, and manual curation.

## Overview

This repository is structured as follows:

```
router-models/
├── arista
│   └── <router_model_name>
├── cisco
│   └── <series_name>
│       (└── <router_model_name>)
└── juniper
    └── <router_model_name>
```

Files per router model:

```
filtered_netbox.yaml      # Data extracted from the NetBox Device Type Library
general_llm.yaml          # Data extracted from manufacturer datasheets via LLM prompting
manual.yaml               # (Optional) Only exists if data has been manually verified
```

For Cisco router models, `cisco/<series_name>/` contains series-level metadata. If a series has multiple models, each model lives under `cisco/<series_name>/<router_model_name>/`.

Additional Cisco files:

```
date_llm.yaml             # Date information extracted from Cisco datasheets via LLM prompting
series.yaml               # Series information extracted manually
```

Eventually, all data from all available sources is merged into a single file per router model:

```
merged.yaml               # Merged data from all sources, manually extracted data overrides others
```

## Retrieving Data

All router models can be downloaded as a single csv file [here](https://networkpowerzoo.ethz.ch/api/static/router-models.zip).

## Contributing

We welcome contributions to expand and improve the data. Here’s how you can contribute:

1. Clone the repository

   ```sh
   git clone https://github.com/nsg-ethz/NetworkPowerZoo-Hardware-Inventory.git
   ```

2. Add a new router model

   - Create the folder following the layout above.
   - Copy `router-model-template.yml` into the new folder as `manual.yaml`.
   - Fill in accurate attributes for the model.
   - Duplicate `manual.yaml` as `merged.yaml`.

3. Verify or correct an existing model

   - Create (or edit) `manual.yaml` in the model folder.
   - Review `merged.yaml`.
   - If all attributes are correct, keep `manual.yaml` empty.
   - If any attribute is incorrect or missing, add only the changed/missing fields to `manual.yaml` and update `merged.yaml` accordingly.

4. Submit a pull request with your changes.

## Contact

Questions or suggestions? Open an issue here or reach us via the [Network Power Zoo](https://networkpowerzoo.ethz.ch/) website.

## License

CC0-1.0. See [LICENSE](LICENSE).
