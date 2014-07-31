# scripts-dyndns

This package provides scripts that assist with updating a DynDNS hostname and
other related tasks.

The scripts are packaged using `npm` for convenience, so you'll need to
[install Node.js](https://github.com/joyent/node/wiki/Installation)
if you haven't already.

## Installation

Install `curl` and the following Perl modules (for example, using your package
manager or
[CPAN Minus](https://github.com/miyagawa/cpanminus)):

- `Getopt::Long::Descriptive`
- `LWP::UserAgent`
- `Net::DNS::Resolver`

Then:

    sudo npm install -g scripts-dyndns

Similarly, to uninstall:

    sudo npm rm -g scripts-dyndns

## Scripts

### update-dyndns

Updates the IP address associated with a DynDNS hostname.

```
update-dyndns [-?dhipuv] [long options...]
        -v --verbose      Show debug output
        -u --username     DynDNS username
        -p --password     DynDNS password
        -i --ip           New IP address
        -d --domain       Domain to update
        -? -h --help      Show usage information
```

Example usage:

```
update-dyndns \
    -u dyndnsuser \
    -p dyndnspass \
    -i `get-external-ip` \
    -d mydomain.com
```

### get-external-ip

Retrieves the current IP address from an external server.
