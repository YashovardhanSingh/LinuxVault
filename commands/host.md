# `host` Command

The `host` command is used to perform DNS lookups and obtain information about DNS records. It queries the DNS server to get details about a domain name or IP address.

## Syntax

```bash
host [options] Domain|IP
```

## Key Usage and Examples

### 1. DNS Lookup

To find the IP address of a domain:

  ```bash
    host example.com
  ```

### 2. Reverse DNS Lookup
To find the domain-name associated with an IP address:
  ```bash
    host XX.XXX.XXX.XX
  ```

### 3. Specific DNS Record Type

You can specify the type of DNS record you want to query with `-t`:
  ```bash
    host -t CNAME example.com # CNAME record
    host -t MX example.com # MX record
  ```


### 4. All Available Information

To display all information available for a domain:

  ```bash
    host -a example.com # Verbose Output + Every Record
  ```

### 5. Query a Specific DNS Server

To query using a specific DNS server:

  ```bash
    host example.com 8.8.8.8
  ```
  This queries Google's public DNS server (8.8.8.8).

### 6. IPv4 and IPv6 Specific Queries

`-4`: Query to only IPv4 addresses.

  ```bash
    host -4 example.com
  ```

`-6`: Query to only IPv6 addresses.

  ```bash
    host -6 example.com
  ```

## Resources
- [Kali Docs](https://www.kali.org/tools/bind9/#host)
- [Host man page](https://linuxcommandlibrary.com/man/host)