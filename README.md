                                    END-TO-END DEEP LEARNING PROJECT    
This is project classifies the type of chicken disease based on image classification.
---------------------------------------------------------------------------------------------------------------------
Set up a virtual environment to install necessary packages used for this project.
Clone this project to github thorugh the command "fir clone {github repo link}"
Create the project template ie., the files so that unlike manual creation this helps to automate.
The project uses modular coding.

Logging code is implemented in constructor file of src since it is the main package

1. Update config.yaml
2. Update params.yaml
3. Update the entity
4. Update the configuration manager in src config
5. Update the components
6. Update the pipeline
7. Update the main.py
8. Update the dvc.yaml

---------------------------------------------------------------------------------------------------------------------
                                                CONFIG.YAML
This file contains key value pairs where 
* keys: some variable which stores the path
* values: Paths
---------------------------------------------------------------------------------------------------------------------
                                                    DATA INGESTION
 
-> Simply follow the workflows.
-> In the first step update the config.yaml
   * So the config.yaml contains key value pairs
        => keys: some variable which stores the path
        =>values: Paths
-> Update the params, As of data ingestion there is no need of params so
   simply write a default key-value pair so that the file is not empty.
-> update entity 
   * The entity contains the user defined rturn type which is created by Dataclass
-> update the configuration management 
   * The configuration.py is responsible for reading the config.yaml.
   * config.yaml consists the data path from web.
   * (The location of config.yaml, params.yaml is stored in the constants.)
   * Since it contains the paths it creates the folders and maps the data_paths to the new folders(where the data is stored).
   * So finally configuration.py holds the data_paths.
-> Now create a data_ingestion in components 
   * In data ingestion all the required paths are availble by importing the data_configuration 
   * This is responsible to download
-> Now create a pipeline stage_01_data_ingestion which calls the functions of components(data_integration) to install the  data
-> main.py calls the pipeline -> pipeline calls the data_integraion and download starts.