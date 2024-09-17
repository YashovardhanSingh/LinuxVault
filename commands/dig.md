# `dig` Command

The `dig` (Domain Information Groper) command in Kali Linux is a network administration tool for querying DNS (Domain Name System) name servers. It is useful for troubleshooting DNS problems and obtaining information like IP addresses and other DNS records for a given domain.

## Syntax

```bash
dig [options] [hostname] [query type] [@server]
```

#### Parameters:
- **hostname**: The domain name to query.
- **query type**: Specifies the type of DNS record to query (default is A record).
- **@server**: Specifies the DNS server to query (optional, default is your configured DNS server).

## Key Usage and Examples

### 1. DNS Lookup

To query the IP address (A record) of a domain:

```bash
dig example.com
```

This will return the A record (IPv4 address) of `example.com`.

### 2. Reverse DNS Lookup
To perform a [reverse DNS lookup](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) (find the domain name associated with an IP address):
  ```bash
    dig -x XX.XXX.XXX.XX
  ```
This will return the domain name associated with the specified IP.

### 3. Query Specific DNS Record Types

You can specify the type of DNS record you want to query:

- **A** (Address Record) - returns the IPv4 address. (default)
  
  ```bash
  dig example.com A
  ```

- **AAAA** (IPv6 Address Record) - returns the IPv6 address.
  
  ```bash
  dig example.com AAAA
  ```

- **CNAME** (Canonical Name Record) - retrieves canonical name for aliases.
  
  ```bash
  dig example.com CNAME
  ```

- **MX** (Mail Exchange Record) - shows the mail servers for the domain.
  
  ```bash
  dig example.com MX
  ```

- **NS** (Name Server Record) - lists the name servers.
  
  ```bash
  dig example.com NS
  ```

- **SOA** (Start of Authority) - administrative details about the domain.
  
  ```bash
  dig example.com SOA
  ```

- **TXT** (Text Record) - returns text records associated with a domain.
  
  ```bash
  dig example.com TXT
  ```

### 4. Query ALL Records

To retrieve all DNS records (A, MX, NS, etc.) for a domain:

  ```bash
    dig example.com ANY
  ```

### 5. Query a Specific DNS Server

To query a domain using a specific DNS server, use the `@` symbol followed by the server address:

  ```bash
    dig example.com @8.8.8.8
  ```
  This queries Google's public DNS server (8.8.8.8).


### 6. Display Short Answer

If you only want to see the short answer (IP address, etc.) without additional information:

  ```bash
    dig example.com +short
  ```

### 7. Specifying Port

To query a DNS server on a non-standard port:

  ```bash
    dig example.com @8.8.8.8 -p 80
  ```

### 8. IPv4 and IPv6 Specific Queries

`-4`: Restricts the query to only IPv4 addresses (A records).

  ```bash
    dig example.com -4
  ```

`-6`: Restricts the query to only IPv6 addresses (AAAA records).

  ```bash
    dig example.com -6
  ```

## Resources
- [Kali Docs](https://www.kali.org/tools/bind9/#dig)
- [Dig man page](https://linuxcommandlibrary.com/man/dig)