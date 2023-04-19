# CapturePhoneTraffic

A simple application, to capture your traffic from your phone.

## Usage

1. Create a wi-fi hotspot from your computer.

2. Launch the `docker-compose.yml` file with the corresponding command:
    ```bash
    docker-compose up -d
    ```

3. Connect with your phone to the corresponding wi-fi hotspot

Add a manual proxy:
Retrieve the IP of your wi-fi network. You can perform that with `ip a` on Linux.

- Server URL: `<wi-fi_network_ip>`
- Port: `3128`

4. Retrieve the logs and see the connect

```bash
docker compose logs -f squid
```

Example :
```bash
squidwebproxy-squid-1  | 1681829667.930   1305 192.168.16.1 TCP_TUNNEL/200 7430 CONNECT inappcheck.itunes.apple.com:443 - HIER_DIRECT/17.36.202.159 -
squidwebproxy-squid-1  | 1681829668.067    825 192.168.16.1 TCP_TUNNEL/200 6065 CONNECT www.googleapis.com:443 - HIER_DIRECT/216.58.214.170 -
squidwebproxy-squid-1  | 1681829668.101    851 192.168.16.1 TCP_TUNNEL/200 5943 CONNECT www.googleapis.com:443 - HIER_DIRECT/216.58.214.170 -
squidwebproxy-squid-1  | 1681829674.407   7841 192.168.16.1 TCP_TUNNEL/200 7461 CONNECT inbox.google.com:443 - HIER_DIRECT/216.58.214.165 -
squidwebproxy-squid-1  | 1681829674.407   7839 192.168.16.1 TCP_TUNNEL/200 15042 CONNECT chat.google.com:443 - HIER_DIRECT/142.250.179.78 -
squidwebproxy-squid-1  | 1681829674.407   6767 192.168.16.1 TCP_TUNNEL/200 6019 CONNECT notifications-pa.googleapis.com:443 - HIER_DIRECT/142.250.179.74 -
squidwebproxy-squid-1  | 1681829674.407   7754 192.168.16.1 TCP_TUNNEL/200 6923 CONNECT notifications-pa.googleapis.com:443 - HIER_DIRECT/142.250.179.74 -
squidwebproxy-squid-1  | 1681829675.443   1197 192.168.16.1 TCP_TUNNEL/200 5512 CONNECT gs-loc.apple.com:443 - HIER_DIRECT/17.57.172.10 -
squidwebproxy-squid-1  | 1681829678.983    273 192.168.16.1 TCP_REFRESH_UNMODIFIED/200 307 GET http://netcts.cdn-apple.com/ - HIER_DIRECT/92.122.188.20 text/html
squidwebproxy-squid-1  | 1681829786.541    603 192.168.16.1 TCP_TUNNEL/200 7502 CONNECT gateway.icloud.com:443 - HIER_DIRECT/17.248.176.44 -
squidwebproxy-squid-1  | 1681829847.390  31572 192.168.16.1 TCP_TUNNEL/200 5333 CONNECT iphone-ld.apple.com:443 - HIER_DIRECT/92.122.218.170 -
```