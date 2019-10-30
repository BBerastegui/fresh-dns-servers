# Automatically refreshed list of DNS resolvers

I set up an scheduled task in Google Cloud that automatically launches ~https://github.com/teknogeek/fresh.py~ https://github.com/vortexau/dnsvalidator on a daily basis and posts the updated resolvers.txt list to this repository.

I'm currently pulling and running through dnsvalidator the following lists (open to add more :D):
- https://public-dns.info/nameservers.txt
- https://raw.githubusercontent.com/blechschmidt/massdns/master/lists/resolvers.txt

So if nothing goes wrong, we are supposed to get a list of reliable DNS servers in this repo.

So you could so something like:

```bash
./bin/massdns -r <(curl -s https://raw.githubusercontent.com/BBerastegui/fresh-dns-servers/master/resolvers.txt) ...
```

Or

```bash
cat domains.txt \
    | zdns ANY \
    --name-servers <(curl -s https://raw.githubusercontent.com/BBerastegui/fresh-dns-servers/master/resolvers.csv)
```

Or whatever you want.

Disclaimer: I know that the .csv file is not a "proper" csv, but it fits the zdns format :)

Let's see if this works!
