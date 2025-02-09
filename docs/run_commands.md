# Setting up the environment (Python 3.7.4):
Two ways to setting up environment:

## Using setup.sh:
- Run setup file as: `sh setup.sh`

## Using requirements.txt:
- Create a virtual enviroment: `python3 -m venv ../NWC_env`
- Active virtual enviroment: `source ../NWC_env/bin/activate`
- Install all dependencies: `pip install -r requirements.txt`

# Running and preparing Engine Data Client:
- Run command: `python -m module.engine_client`
- Intermediate created in data folder by the name: `formatted_engine_data.csv`

# Testing various modules:
- **config_parser**: `python -m tests.test_config_parser`
- **default_discretizer**:	`python -m tests.discretize.test_default_discretizer`
- **denoising_discretizer**: `python -m tests.discretize.test_denoise_discretizer`
- **meanthreshold_binarize**:: `python -m tests.nc_window.test_meanthreshold_binarize`
- **invalid_idx_preprocess**:: `python -m tests.preprocess.test_invalid_idx_preprocess`

# Using configuration file:
- Default configuration and data file in folder module/data
- Can change the `default_config.json` file or provide a custom configuration and 
run as: `python -m module.engine_client --configpath *full path of your configuration file*`
- Details of various configuration parameters present in **config_doc.md**

# Comparison with previous project:
- Some of the outputs might not be comparable to previous results because:
    - In previous project, no unit tests were performed
    - One major issue in previous project was UB pruning of middle nodes, 
    which was happening due to non-propogation of supperpatterncount from parent nodes
    - The above issue was leading to the previous project missing a lot of patterns
    - The current project fixes this issue and contains all possible patterns