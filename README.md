## Use Domeneshop domain API to automatically issue cert

First you need to add `dns_domeneshop.sh` to the acme.sh `dnsapi` folder.

```
cp dns_domeneshop.sh ~/.acme.sh/dnsapi/
```

Then you'll have to get a Domeneshop API key and secret (https://api.domeneshop.no/docs/).

```
export Domeneshop_Token="1234567890"
export Domeneshop_Secret="1234567890abcdefghijklmnopqrstuvw"
```


Ok, let's issue a cert now:
```
acme.sh --issue --dns dns_domeneshop -d example.com -d www.example.com
```

The `Domeneshop_Token` and `Domeneshop_Secret` will be saved in `~/.acme.sh/account.conf` and will be reused when needed.