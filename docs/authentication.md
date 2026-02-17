# Authentication

Requests made to the Ma Radio Groove API require a valid API key, which can be generated in the Ma Radio Groove Developer Dashboard. 

!!! important
    Keep your API key secure. Do not expose it in public repositories.

## Use an API Key in a Request

You need to include the API key in the `Authorization` header: 


```bash
curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/djs
```


!!! note
    Requests made without a valid API key return a `401 Unauthorized` response. For more information, see the [Troubleshooting section](troubleshooting.md#troubleshooting). 
