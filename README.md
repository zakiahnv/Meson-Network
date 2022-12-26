# Meson-Network
# Register
https://dashboard.meson.network/register

# Setup Port
sudo apt update && sudo ufw allow 443 && sudo ufw enable

# Download
wget 'https://staticassets.meson.network/public/meson_cdn/v3.1.x/meson_cdn-linux-amd64.tar.gz' && tar -zxf meson_cdn-linux-amd64.tar.gz && rm -f meson_cdn-linux-amd64.tar.gz && cd ./meson_cdn-linux-amd64 && sudo ./service install meson_cdn

# Set token and config
sudo ./meson_cdn config set --token=YOURTOKEN --https_port=443 --cache.size=20 && sudo ./service restart meson_cdn

# Param List:
-token=your token              # you can find out your token in nodes page
-https_port=443                # default is 443, support for custom server ports
-cache.size=20                 # minimum: 20G, default: 30G
-cache.folder=xxxx

# Start Service
sudo ./service start meson_cdn

# Check Node Running Status
sudo ./service status meson_cdn

# Stop & Remove
sudo ./service stop meson_cdn && sudo ./service remove meson_cdn

# Commands Reference
sudo ./service install meson_cdn              # install node
sudo ./service start meson_cdn                # start node
sudo ./service status meson_cdn               # check node running status
sudo ./service stop meson_cdn                 # stop node
sudo ./service remove meson_cdn               # remove node
sudo ./service restart meson_cdn              # restart node
sudo ./meson_cdn log                          # check logs
./meson_cdn -h  
