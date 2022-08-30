# Bulk-update ESC Accounts

The project bulk-updates ESC accounts using ESC API. Currently features below are available.
1) Account Number
2) Account Name
3) Provider Id
4) Username & Password
5) Date Closed
6) DRS

### Components
- `esc_api.ipynb` : jupyter notebook containing main code 
- `form.csv` : request form that contains esc_account_id, new_account_number, new_account_name, new_provider_id, and etc..
- `form_example.csv` : example of `form.csv`

### Process:
1. ESC API token:
    - if you don't have ESC API, reach out to Data Solution Team or Software Team
    - if you have ESC API token, create a `.env` file in the curruent directory and input values for `token_dev` and `token_prod` using the format below,
        ```
        token_dev = "foo"
        token_prod = "bar"
        token_spg_dev = "foobar"
        token_spg_prod = "baz"
        ```
    
2. Fill out `form.csv`
    - esc_account_id : ESC Account Id that you want to update
    - new_account_name : new ESC Account Name
    - new_account_number : new ESC Account Number
    - new_provider_id : new ESC Provider Id
    - new_username : new Username
    - new_password : new Password
    - new_dateclosed : new Date Closed ("YYYY-mm-dd")
    - new_source : new drs source 
        - "utility_website"
        - "scans"
        - "conservice"
        - "realpage"
        - "sharepoint"
        - "cass"
        - "pending"
    - new_method : new drs method
        - "babl"
        - "cass"
        - "coned"
        - "manual_analyst"
        - "manual_domestic"
        - "manual_foreign"
        - "nwp"
        - "nycdep"
        - "pending"
        - "scraper"
        - "unknown"
        - "urjanet"
        - "urjanet_csv"
        - "urjanet_ftp"
        - "yardi")
    - new_pay_for_data : new drs pay for data
        - "yes"
        - "no"
    - new_transfer_type : new drs transfer type 
        - "allow"
        - "deny"
    - new_retrieval_type : new drs retrieval type
        - "both"
        - "historical"
        - "none"
        - "ongoing"
    - new_billable_department : new drs billable department
        - "Unknown"
        - "Do Not Pay For Data"
        - "Energy Analysis"
        - "Data Team"
        - "ESC Client Billable"
    - site_id : esc site id where you want to create accounts
        
        - ENERGY_KWH
        - ENERGY_THERM
        - WATER_GALLON
        - WATER_KGALLON
        


    *IMPORTANT! For the Date Closed, the new_dateclosed format should be "YYYY-mm-dd"\
    *if you want to update only few of them, leave the unwanted column as blank. (For example, if you only want to update account name and account number, leave the new_provider_id, new_username, new_password columns as blank)
    

3. Run `esc_api.ipynb`

### Requirements:
```
Jupyter Notebook
```

### Install:
```
$ pip install -r requirements.txt
```

### References:
- [ESC API Documentation]('https://brightpower.atlassian.net/wiki/spaces/DEV/pages/5240758689/API+Documentation')
- [ESC API Sample Requests and Responses]('https://brightpower.atlassian.net/wiki/spaces/DEV/pages/5240762737/ESC+API+Sample+Requests+and+Responses')
- [Service Point Group]('https://brightpower.atlassian.net/wiki/spaces/DEV/pages/5240761331/Service+Point+Group+ROBIN+Retrieval+Settings+Domain)