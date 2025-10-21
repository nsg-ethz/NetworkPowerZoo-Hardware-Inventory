# Network Power Zoo Hardware Inventory

Welcome to the **PowerDB_Datasheets** repository, an open-source project dedicated to collecting and maintaining detailed information about the power consumption of various network devices, including routers and transceivers. This repository is a part of the larger **Network Power Zoo** project, contributing data to the **NetPowerDB** database, which is accessible via an API.

> **Note:** Throughout this repository, the term "router" is used broadly to include both routers and switches.

## Repository Structure

The repository is organized as follows:

- **router-vendors/**  
  This directory contains subfolders for different router vendors. Each subfolder includes YAML files that contain power consumption data for specific router models. The filename of each YAML file corresponds to the `model_id` of the router.

- **transceiver-vendors/**  
  Similar to `router-vendors/`, this directory is structured with subfolders for different transceiver vendors. Each subfolder includes YAML files with power consumption data for specific transceiver models. The filename of each YAML file corresponds to the `model_id` of the transceiver.

- **Templates:**

  - **router-template.yml**  
    This template file outlines the required structure and data types for router information. Contributors should use this template to ensure that their data submissions are correctly formatted.
  - **transceiver-template.yml**  
    This template file provides the structure and data types for transceiver information. Contributors should follow this template when adding new data.

- **LICENSE**  
  The repository is licensed under the CC0-1.0 license, making it free for public use.

## How to Contribute

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
