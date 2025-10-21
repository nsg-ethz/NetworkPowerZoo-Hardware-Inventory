# Network Power Zoo Hardware Inventory

This repository contains structured data for router models. The data was aggregated from [NetBox Device Type Library](https://github.com/netbox-community/devicetype-library/tree/master), LLM prompting, and manual curation.

## Router Model Data

This repository is structured as follows:

```
router-models/
├── arista
│   └── <router_model_name>
├── cisco
│   └── <series_name>
│       └── <router_model_name>
└── juniper
    └── <router_model_name>
```

Every router model contains the following files:

```
filtered_netbox.yaml      # Data extracted from NetBox Device Type Library
general_llm.yaml          # Data extracted from Datasheet via LLM prompting
manual.yaml               # Exists if data has been manually checked. Contains manual corrections (if there are any)
```

For Cisco routers, the `cisco/<series_name>/` folder contains series-level information. Whenever there are multiple models in a series, there is a `cisco/<series_name>/<router_model_name>` folder for each model. Additionally, every Cisco related router model contains the following file:

```
date_llm.yaml             # Date information extracted from Cisco Datasheets via LLM prompting
series.yaml               # Series information extracted manually
```

Finally, every router model folder contains all data from all available sources:

```
merged.yaml               # Merged data from all sources, manual overrides others
```

You can download all available router models in a single csv file here.

## How to Contribute

The repository is licensed under the CC0-1.0 license, making it free for public use.

We welcome contributions to expand and improve the data in this repository. Here’s how you can contribute:

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/PowerDB_Datasheets.git
   ```
2. **Navigate to the Appropriate Directory:**
   - For routers, go to `router-vendors/`.
   - For transceivers, go to `transceiver-vendors/`.
3. **Add New Data:**

   - Copy the relevant template file (`router-template.yml` or `transceiver-template.yml`) and fill in the data for the new device model.
   - Ensure that the file name matches the `model_id` of the device.

4. **Submit a Pull Request:**
   - Once your changes are made, submit a pull request. In the future, we may require pull requests for data submission to ensure consistency and accuracy.

## Retrieving Data

You can retrieve data either directly from this repository or via the **NetPowerDB API**.

### From the Repository

Access the YAML files in `router-vendors/` or `transceiver-vendors/` to view individual device power consumption details.

### Using the NetPowerDB API

The NetPowerDB API provides access to a comprehensive database of power consumption data for network devices. For detailed instructions on how to use the API, please visit the [Network Power Zoo API Documentation](https://networkpowerzoo.ethz.ch/).

## License

This project is licensed under the CC0-1.0 License. For more information, see the [LICENSE](LICENSE) file.

## Contact

For questions or suggestions, feel free to open an issue in this repository or contact us through the [Network Power Zoo](https://networkpowerzoo.ethz.ch/) website.

Happy contributing!
