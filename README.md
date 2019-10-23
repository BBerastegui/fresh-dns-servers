# Automatically refreshed list of DNS resolvers

I set up an scheduled task in Google Cloud that automatically launches https://github.com/teknogeek/fresh.py and posts the updated resolvers.txt list to this repository.

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
