# faxplus-api
This is the FAX.PLUS API v1 developed for third party developers and organizations. In order to have a better coding experience with this API, let's quickly go through some points:<br /><br /> - This API assumes **/accounts** as an entry point with the base url of **https://restapi.fax.plus/v1**. <br /><br /> - This API treats all date and times sent to it in requests as **UTC**. Also, all dates and times returned in responses are in **UTC**<br /><br /> - Once you have an access_token, you can easily send a request to the resource server with the base url of **https://restapi.fax.plus/v1** to access your permitted resources. As an example to get the user's profile info you would send a request to **https://restapi.fax.plus/v1/accounts/self** when **Authorization** header is set to \"Bearer YOUR_ACCESS_TOKEN\" and custom header of **x-fax-clientid** is set to YOUR_CLIENT_ID

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

You can simply install SDK from pypi repository
```sh
pip install faxplus-api
```

You can also install directly from Github

```sh
pip install git+https://github.com/alohi/faxplus-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/alohi/faxplus-python.git`)

Then import the package:
```python
import faxplus 
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import faxplus
```

## Getting Started

If you haven't already, please follow the [installation procedure](#installation--usage) to install the sdk

There's a sample app located at [sample-app](https://github.com/alohi/faxplus-sample-python.git) folder to get you started. It contains sample code to get access_token and use refresh token to renew access_token. It also contains sample requests to all endpoints and a GUI to view responses easily.
- sample app runs on localhost:8080. so you need to add http://localhost:8080/cb/ to your redirect uris in our website.
- run following commands to install requirements and create a config.json file

```sh
cd sample-app
pip install -r requirements.txt
cp sample.config.json config.json
```
- edit config.json add your client_id and secret
- run `python app.py` to run sample app.

## Documentation for API Endpoints

All URIs are relative to *https://restapi.fax.plus/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountsApi* | [**get_accounts**](docs/AccountsApi.md#get_accounts) | **GET** /accounts | Get account information of all members of your corporate account
*AccountsApi* | [**get_member_details**](docs/AccountsApi.md#get_member_details) | **GET** /accounts/self/member-details/{member_id} | Get member details
*AccountsApi* | [**get_user**](docs/AccountsApi.md#get_user) | **GET** /accounts/{user_id} | Get account information for admin or member
*AccountsApi* | [**update_member_details**](docs/AccountsApi.md#update_member_details) | **PUT** /accounts/self/member-details/{member_id} | Modify member details
*AccountsApi* | [**update_user**](docs/AccountsApi.md#update_user) | **PUT** /accounts/self | Modify account information
*ArchivesApi* | [**delete_fax**](docs/ArchivesApi.md#delete_fax) | **DELETE** /accounts/self/archives/{fax_id} | Delete a fax
*ArchivesApi* | [**get_fax**](docs/ArchivesApi.md#get_fax) | **GET** /accounts/self/archives/{fax_id} | Get a fax record
*ArchivesApi* | [**list_faxes**](docs/ArchivesApi.md#list_faxes) | **GET** /accounts/{user_id}/archives | Get fax records
*ArchivesApi* | [**update_fax**](docs/ArchivesApi.md#update_fax) | **PUT** /accounts/self/archives/{fax_id} | Modify fax record
*FilesApi* | [**get_file**](docs/FilesApi.md#get_file) | **GET** /accounts/self/files/{fax_id} | get a file
*FilesApi* | [**upload_file**](docs/FilesApi.md#upload_file) | **POST** /accounts/self/files | upload a file
*NumbersApi* | [**get_number**](docs/NumbersApi.md#get_number) | **GET** /accounts/self/numbers/{number} | Get number information
*NumbersApi* | [**list_numbers**](docs/NumbersApi.md#list_numbers) | **GET** /accounts/self/numbers | Get your numbers
*NumbersApi* | [**revoke_number**](docs/NumbersApi.md#revoke_number) | **DELETE** /accounts/self/numbers/{number} | Revoke number
*NumbersApi* | [**update_number**](docs/NumbersApi.md#update_number) | **PUT** /accounts/self/numbers/{number} | Assign number
*OutboxApi* | [**delete_outbox_fax**](docs/OutboxApi.md#delete_outbox_fax) | **DELETE** /accounts/self/outbox/{outbox_fax_id} | Delete a fax from outbox
*OutboxApi* | [**get_outbox_fax**](docs/OutboxApi.md#get_outbox_fax) | **GET** /accounts/self/outbox/{outbox_fax_id} | Get an outbox record
*OutboxApi* | [**list_outbox_faxes**](docs/OutboxApi.md#list_outbox_faxes) | **GET** /accounts/self/outbox | Get outbox records
*OutboxApi* | [**send_fax**](docs/OutboxApi.md#send_fax) | **POST** /accounts/self/outbox | Send a fax
*OutboxApi* | [**update_outbox_fax**](docs/OutboxApi.md#update_outbox_fax) | **PUT** /accounts/self/outbox/{outbox_fax_id} | Modify a fax record in outbox


## Documentation For Models

 - [Account](docs/Account.md)
 - [AccountAccountData](docs/AccountAccountData.md)
 - [AccountSettings](docs/AccountSettings.md)
 - [AccountSettingsSendFax](docs/AccountSettingsSendFax.md)
 - [AccountSettingsSendFaxRetry](docs/AccountSettingsSendFaxRetry.md)
 - [Error](docs/Error.md)
 - [Fax](docs/Fax.md)
 - [FaxCostDetails](docs/FaxCostDetails.md)
 - [File](docs/File.md)
 - [MemberDetail](docs/MemberDetail.md)
 - [Number](docs/Number.md)
 - [NumberNotifications](docs/NumberNotifications.md)
 - [Outbox](docs/Outbox.md)
 - [OutboxComment](docs/OutboxComment.md)
 - [OutboxFileChanges](docs/OutboxFileChanges.md)
 - [OutboxFiles](docs/OutboxFiles.md)
 - [OutboxInitiatedFrom](docs/OutboxInitiatedFrom.md)
 - [OutboxStatusChanges](docs/OutboxStatusChanges.md)
 - [PayloadFaxModification](docs/PayloadFaxModification.md)
 - [PayloadNumberModification](docs/PayloadNumberModification.md)
 - [PayloadOutbox](docs/PayloadOutbox.md)
 - [PayloadOutboxComment](docs/PayloadOutboxComment.md)
 - [PayloadOutboxModification](docs/PayloadOutboxModification.md)
 - [PayloadOutboxOptions](docs/PayloadOutboxOptions.md)
 - [PayloadOutboxOptionsRetry](docs/PayloadOutboxOptionsRetry.md)
 - [ResponseAccountList](docs/ResponseAccountList.md)
 - [ResponseArchive](docs/ResponseArchive.md)
 - [ResponseArchiveData](docs/ResponseArchiveData.md)
 - [ResponseNumberList](docs/ResponseNumberList.md)
 - [ResponseOutboxList](docs/ResponseOutboxList.md)


## Documentation For Authorization


## fax_oauth

- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: https://accounts.fax.plus/login?response_type=code&client_id=YOUR_CLIENT_ID&redirect_uri=http://localhost&scope=all
- **Scopes**: 
 - **all**: for now when a user grant permission, all grants will be permitted


## Considerations
- PayloadOutbox and Fax models contain a field named "from" but from is a reserved keyword in python. Use "from_number" instead of "from" for those models.



