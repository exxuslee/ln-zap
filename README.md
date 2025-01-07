# lndconnect 🌩 [![Build Status](https://travis-ci.com/LN-Zap/lndconnect.svg?branch=master)](https://travis-ci.com/LN-Zap/lndconnect)

Generate a QRCode or URI to connect applications to lnd instances.

For more information take a look at the [specification of the uri format](lnd_connect_uri.md).

## Installing lndconnect

```
go get -d github.com/LN-Zap/lndconnect
cd $GOPATH/src/github.com/LN-Zap/lndconnect
make
```

## Starting lndconnect

```
lndconnect
```

## Application Options

```
-i, --localip               Include local ip in QRCode
-l, --localhost             Use 127.0.0.1 for ip
    --host=                 Use specific host name
    --nocert                Don't include the certificate
-p, --port=                 Use this port (default: 10009)
-j, --url                   Display url instead of a QRCode
-o, --image                 Output QRCode to file
    --invoice               Use invoice macaroon
    --readonly              Use readonly macaroon
-q, --query=                Add additional url query parameters

    --lnddir=               The base directory that contains lnd's data, logs, configuration
                            file, etc.
    --configfile=           Path to configuration file
-b, --datadir=              The directory to find lnd's data within
    --tlscertpath=          Path to read the TLS certificate from
    --adminmacaroonpath=    Path to read the admin macaroon from
    --readonlymacaroonpath= Path to read the read-only macaroon from
    --invoicemacaroonpath=  Path to read the invoice-only macaroon from
```

.\lndconnect.exe --datadir="..\lncm\lnd\data" --tlscertpath="..\lncm\lnd\tls.cert" --adminmacaroonpath="..\lncm\lnd\data\chain\bitcoin\testnet\admin.macaroon"
.\lndconnect.exe -j --datadir="..\lncm\lnd\data" --tlscertpath="..\lncm\lnd\tls.cert" --adminmacaroonpath="..\lncm\lnd\data\chain\bitcoin\testnet\admin.macaroon"

.\lndconnect.exe --url "lndconnect://192.168.1.114:10009?cert=MIICKjCCAdCgAwIBAgIRAMhrGkaIMMt4BtgCOQFLTKswCgYIKoZIzj0EAwIwODEfMB0GA1UEChMWbG5kIGF1dG9nZW5lcmF0ZWQgY2VydDEVMBMGA1UEAxMMNmYwMzlmOTYyMWY1MB4XDTI0MTIyOTE0MDgxOVoXDTI2MDIyMzE0MDgxOVowODEfMB0GA1UEChMWbG5kIGF1dG9nZW5lcmF0ZWQgY2VydDEVMBMGA1UEAxMMNmYwMzlmOTYyMWY1MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEKu_jTnfnr5SKjn7w_HjonxzF9bImYEytZx_n2Fyu-wvRIkU0_HiNqWQnuxkTtWeBPWj3qdSibHAXmi3QcN0gE6OBujCBtzAOBgNVHQ8BAf8EBAMCAqQwEwYDVR0lBAwwCgYIKwYBBQUHAwEwDwYDVR0TAQH_BAUwAwEB_zAdBgNVHQ4EFgQU2FzGlYz3pGTtlt4UA8jSe0Zsh2UwYAYDVR0RBFkwV4IMNmYwMzlmOTYyMWY1gglsb2NhbGhvc3SCA2xuZIIEdW5peIIKdW5peHBhY2tldIIHYnVmY29ubocEfwAAAYcQAAAAAAAAAAAAAAAAAAAAAYcErBIAAzAKBggqhkjOPQQDAgNIADBFAiBJc6uM9zoOoLM50OavykhGxxxr4E7kIBf_rR79--OHPQIhANrCQf6k85K2qKqZG0Jwn-L-ooNlJfRb_s9KcGWa9tVI&macaroon=AgEDbG5kAvgBAwoQyhIJVC2Zm8NSh4grU6gE3RIBMBoWCgdhZGRyZXNzEgRyZWFkEgV3cml0ZRoTCgRpbmZvEgRyZWFkEgV3cml0ZRoXCghpbnZvaWNlcxIEcmVhZBIFd3JpdGUaIQoIbWFjYXJvb24SCGdlbmVyYXRlEgRyZWFkEgV3cml0ZRoWCgdtZXNzYWdlEgRyZWFkEgV3cml0ZRoXCghvZmZjaGFpbhIEcmVhZBIFd3JpdGUaFgoHb25jaGFpbhIEcmVhZBIFd3JpdGUaFAoFcGVlcnMSBHJlYWQSBXdyaXRlGhgKBnNpZ25lchIIZ2VuZXJhdGUSBHJlYWQAAAYgbesjVi8nl9-0Q465VwrnShgNMkGZAGSTa3vlFYgvypY"