# What it does

Poll a [Yiimp pool] block found result page (usually on /site/found\_results) and post a message to [Discord] chat room.


# System service installation

1. Install depencencies (Python 3.5+)
```
sudo apt install python3-aiohttp python3-bs4 python3-html5lib
```

2. Install script
```
sudo wget https://raw.githubusercontent.com/jdoerrer/yiimp-blocks-found-to-discord/master/yiimp-blocks-found-to-discord.py -O /usr/local/bin/yiimp-blocks-found-to-discord.py
sudo chmod 0755 /usr/local/bin/yiimp-blocks-found-to-discord.py
```

3. Register as a systemd service
```
sudo wget https://raw.githubusercontent.com/eLvErDe/yiimp-blocks-found-to-discord/master/systemd/service -O /etc/systemd/system/yiimp-blocks-found-to-discord.service 
sudo wget https://raw.githubusercontent.com/eLvErDe/yiimp-blocks-found-to-discord/master/systemd/default -O /etc/default/yiimp-blocks-found-to-discord
sudo systemctl daemon-reload
```

4. Edit `/etc/default/yiimp-blocks-found-to-discord` to set the correct pool URL and Discord web hook URL

5. Mark as autostart and start it
```
sudo systemctl enable yiimp-blocks-found-to-discord
sudo systemctl start yiimp-blocks-found-to-discord
```

6. Check application logs
```
sudo tail -n 50 -f /var/log/syslog | grep yiimp-blocks-found-to-discord
```

[Yiimp pool]: https://github.com/tpruvot/yiimp
[Discord]: https://discordapp.com/



