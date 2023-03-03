# esphome
These are some example yaml files that I am using in my home. I use esphome to flash my esp8266 nodes. I use docker compose to create docker container to flash


Run Esphome Dashboard in Docker, not `--device` is the usb port that node device is connecte to

```sh
sudo docker run --rm --net=host --device=<usb_port> -v </path/to/config>:/config -it esphome/esphome
```
ie
```sh
sudo docker run --rm --net=host --device=/dev/ttyUSB0 -v "${PWD}":/config -it esphome/esphome
```

Run Esphome Dashboard in Docker with no node device connected, ie if you want to OTA update

```sh
sudo docker run --rm --net=host -v "${PWD}":/config -it esphome/esphome
```

Access dashboard - `ip_addr` is the ip address of the machine where the dashboard docker container is running
```sh
http://<ip_addr>:6052/
```


## Reference
https://esphome.io/