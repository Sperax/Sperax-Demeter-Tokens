# Sperax-Demeter-Tokens
Token list for Demeter

## Guide for launch new token
1. Create token folder in "/tokens". The folder name is token address. And it should be lowercase.
2. Upload the token logo in the token folder.
3. Create token.json in the token folder.
4. Set the git commit msg to "XXX token" when commit the changes.

## Guide for "token.json"
1. The template like this
```
{
    "chainId": 42161,
    "address": "0x5575552988a3a80504bbaeb1311674fcfd40ad4b",
    "name": "SPA",
    "symbol": "SPA",
    "logoURI": "logo.svg",  // This value should be same as the name of token logo file.
    "decimals": 18
}
```

2. Setup the price source

#### Fetch price from coingecko and using other network instead of Arbitrum
```
{
    "chainId": 42161,
    "address": "0x5575552988a3a80504bbaeb1311674fcfd40ad4b",
    "name": "SPA",
    "symbol": "SPA",
    "logoURI": "logo.svg",
    "decimals": 18,
    "priceSource": {
        "source": "coingecko",
        "options": {
            "contract": "0xb4a3b0faf0ab53df58001804dda5bfc6a3d59008",   // set value to the token address on the other network
            "platform": "ethereum"  // the platform name. e.g ethereum|arbitrum-one
        }
    }
}
```

#### Fetch price from REST API
```
{
    "chainId": 42161,
    "address": "0x5575552988a3a80504bbaeb1311674fcfd40ad4b",
    "name": "SPA",
    "symbol": "SPA",
    "logoURI": "logo.svg",
    "decimals": 18,
    "priceSource": {
        "source": "REST",
        "options": "http://XXXX"
    }
}
```
