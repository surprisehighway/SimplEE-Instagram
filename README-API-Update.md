Instagram API Changes
---------------------

Public access is no longer allowed, so generating new API credentials must be done *WHILE LOGGED IN TO THE CLIENT'S INSTAGRAM ACCOUNT*.

Documentation is [here](https://www.instagram.com/developer/authentication/). Or just follow the steps below.

### Get Client ID, Access Token, and User Id

1. Register for developer access. [https://www.instagram.com/developer](https://www.instagram.com/developer)
   This looks like a contact form, but is just the first step.

2. Click Manage Clients > Register new Client ID
   Fill in form and make sure the use the website url for site and redirect

3. Click Manage (in the new client) to get ID and Secret

4. Update Security tab and UNCHECK Disable Implicit Oauth.

5. Load the following URL, replacing the client id and url, to generate an ACCESS TOKEN
   [https://www.instagram.com/oauth/authorize/?client_id=CLIENT_ID_HERE&redirect_uri=URL_HERE&response_type=token](https://www.instagram.com/oauth/authorize/?client_id=CLIENT_ID_HERE&redirect_uri=URL_HERE&response_type=token)

6. Authorize instagram using the Client ID and Secret from step #2.

7. The url will contain the the access_token param. The USER ID (not client ID) for setting up the feed is the first numbers up to the first dot. e.g. **XXXX**.XXXXXXXXXX

### Plugin tags

Note: This has only been tested with the `exp:simplee_instagram:user` method.

The `user_id` param is required. You can either enter the `client_id` and `access_token` directly as parameters or you can set them in the plugin's `config.php` file instead.

```
{exp:simplee_instagram:user 
	user_id="12345678910" 
	client_id="109876543e2109876543f"
	access_token="12345678910.48f95482.4c45678de3dce12be55ad654321a24b55"
	limit="3"
}
```