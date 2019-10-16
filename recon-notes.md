Snippets, options and other stuff i tend to forget while doing recon 


## ASNs 

#### amass 

###### Find ASNs 
`amass intel -org OrgName`

###### Find domains on ASN
`amass intel -active -asn 123,456,789`

#### ipinfo.io
`curl http://ipinfo.io/127.0.0.1`

#### ASNLookup.com 
`curl http://asnlookup.com/api/lookup?org=OrgName`

## Subdomains 

###### crt.sh oneliner (thanks @nahamsec)
`curl -s "https://crt.sh/?q=%25.org.com&output=json" | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u`

###### dns. bufferover.run
`curl -s "http://dns.bufferover.run/dns?q=.org.com" | jq -r ".FDNS_A[],.RDNS[]" | cut -d',' -f2 | sort -u`
