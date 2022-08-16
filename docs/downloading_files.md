<!-- ---
hide:
  - navigation
--- -->

# Data File Downloads

Users can download data files associated with a study by downloading the files directly from the Discovery page, or leveraging the CTDS-owned python software development kit (SDK) and the tool “Gen3-client” if the file size exceeds 250 MB.

## Download Data Files from the Explorer Page




## Download Data Files using the Gen3-client

In order to download data files above 250 MB, users will need to utilize the Gen3-client command line tool developed by the University of Chicago’s Center for Translational Data Science.

The current studies that have datasets of more than 250 MB are those with the following project numbers: a) cdcwonder and b) deaarcos1.

Find below a guide to download data files using the Gen3-client:

1.  Log in to the JDC Platform (see how to do this [here](logging-in.md)). 
      
2.  Find and select one or multiple studies of interest on the [Explorer Page](explorer.md). For multiple studies, select "Data Availability" in the top right corner, click “Available”, and choose multiple studies.
  
4.  Click on the button “Download Manifest".

![discovery_select_study_download_manifest](img/discovery_select_study_download_manifest.png)

Select a study of interest, then click on the button “Download Manifest".
     
5.  Create and download an API key from your [Profile Page](https://healdata.org/portal/identity). Note where you save the API key on your local machine.  

![profile_APIkey](img/profile_APIkey.png)
    
Create an API key on the profile page.
    
![profile_APIkey_created](img/profile_APIkey_created.png)

Download the API key as json file and note the directory where the API key was saved for step 6.
     
6.  Download and configure the Gen3-client  
    a. Follow the download instructions of the Gen3-client [here](https://gen3.org/resources/user/gen3-client/#1-installation-instructions). The client can be downloaded [here](https://github.com/uc-cdis/cdis-data-client/releases/latest).  
      
    b. In your terminal, configure your profile using the following command:  
      
    ```shell
    gen3-client configure --profile=<profile_name> --cred=<credentials.json> --apiendpoint=<api_endpoint_url>`
    ```
   
    Mac/Linux:   
    
    ```bash
    gen3-client configure --profile=demo   --cred=~/Downloads/demo-credentials.json --apiendpoint=https://healdata.org/
    ```
    
    Windows:   
    
    ```ps
    gen3-client configure --profile=demo   --cred=C:\Users\demo\Downloads\demo-credentials.json --apiendpoint=https://healdata.org/
    ```
    
    If the command was succesful, you should get the following output:

    ```10:08:20 Profile 'demo' has been configured successfully. ```

    If successfully executed, a configuration file will be stored under the directory the user specified under “cred”. For troubleshooting, refer to the instructions found [here](https://gen3.org/resources/user/gen3-client/#2-configure-a-profile-with-credentials).  
      
    c. Download files by using the following command, which references the manifest file name and its location:  
      
    ```bash
    gen3-client download-multiple --profile=<profile_name> --manifest=<manifest_file> --download-path=<path_for_files>
    ```
    For example:
    ```bash
    gen3-client download-multiple --profile=demo --manifest=manifest.json --download-path=downloads
    ```
    
    
    ```bash 
    2021/06/03 16:48:46 Reading manifest...   200 B / 200 B [===================] 100.00% 0s  
    WARNING: flag "rename" was set to false in "original" mode, duplicated files under "downloads/" will be overwritten   
    Proceed? [y/n]:
    ```

    Enter:

    ```bash
    y
    ```
    
    
    Output:

    ```bash
    2021/06/03 16:48:47 Total number of GUIDs: 1   2021/06/03 16:48:47 Preparing file info for each file, please wait...   1 / 1 [============================================] 100.00% 0s   2021/06/03 16:48:47 File info prepared successfully   arcos_all_washpost.tsv.gz 6.41 GiB / 6.41 GiB [=======================================================] 100.00% 0s
    ```
  

## Download Data Files in Workspaces using the Python SDK

Users can download data files to the workspaces by leveraging the CTDS-owned python software development kit (SDK). Follow instructions below.

1.  Log in to the Data Commons at <https://healdata.org/portal/login>. Link your accounts to FAIR repositories as described [here](platform_request_access.md#linking-access-to-fair-enabled-repositories).  
      
    
2.  Find and select one or multiple studies of interest on the [Discovery Page](https://healdata.org/portal/discovery). Select "Data Availability" in the top right corner and click on “Available” to see all available studies.  
      
    
3.  Select a study and click on "Open in Workspace".  
    ![static_notebook_bacpac](img/static_notebook_bacpac.png)  
      
    
4.  Select a workspace VM and click "Launch". Choose the "(Generic) Jupyter Notebook with R kernel" if you are familiar with setting up Python- or R-based Notebooks, or if you just exported one or multiple studies from the Discovery Page and want to start your custom analysis. Choose a VM with the name of the Notebook if you selected the studies relevant to a specific Notebook and want to work on the Notebook in interactive mode.  
    ![Workspace_flavors](img/workspace_flavors.png)
    
    Available workspaces on the HEAL Platform (top). Users need to link accounts from other repositories (bottom; click [here to see how](platform_request_access.md#linking-access-to-fair-enabled-repositories)).
    
      
      
    
5.  Find all files under /data/healdata.org/ with the ending "PLACEHOLDER". These files can be directly downloaded either in the terminal or in a notebook cell.  
    ![workspace_placeholder](img/workspace_placeholder.png)  
      
    
6.  Click on one file and copy the command and GUID.  
    ![workspace_placeholder_guid](img/workspace_placeholder_guid.png)  
      
    
7.  Open a new terminal under "New". ![workspace_terminal](img/workspace_terminal.png)  
      
    
8.  *   Type in the following command to download the file to the terminal:  
    ```bash
    gen3 drs-pull object "guid"
    ```
          
    ![workspace_terminal_download](img/workspace_terminal_download.png)  
          
        
    *   If you are working in a notebook, type in the following command into a code cell to download the file:  

    > `!gen3 drs-pull object "guid"`  
          
    ![workspace_download_one_file_sdk](img/workspace_download_one_file_sdk.png)  
          
        
    *  If you use the R kernel, change the command into `system("gen3 drs-pull object 'guid'")`  
          
        
    *   Note, that you can also use the manifest.json to download in batches, see below: ![workspace_download_from_manifest_sdk](img/workspace_download_from_manifest_sdk.png)
        
        Download files in batches with a file manifest using the commands shown above.
        
          
          
        
9.  The file(s) should be downloaded and is ready to be worked with in your Notebook.  
    ![workspace_terminal_downloaded](img/workspace_terminal_downloaded.png)
    
    Downloaded files can be found in your home directory.
