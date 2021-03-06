# `SPyBot`
Python wrapper around [Soroush messenger Bot API](https://soroush-app.ir/developer.html). Note that repository is still under development.  


# Build
```sh
/projects $ git clone --depth 1 https://github.com/Pouriya-Jahanbakhsh/spybot && cd spybot
...
/projects/spybot $ sudo python3.5 setup.py install
...
```

# Quick example:
```python

import spybot
import logging

# set up logging (optional):
logging.basicConfig(level=logging.INFO)

def my_event_handler(event):
    if event.is_text:
        replies = []
        for char in event.body:
            reply = spybot.reply.Text(event.sender, char)
            replies.append(reply)
        return replies

bot = spybot.Bot("MY_TOKEN", event_handler=my_event_handler)
bot.run()
```
Place your token in above example and save it in a file named `echobot.py`, then run below command and send text message to your bot:  
```sh
/path/to/your/echobot $ python3.5 echobot.py
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
```

![spybot_screenshot](https://user-images.githubusercontent.com/20663776/46582566-80a3d500-ca38-11e8-9ab8-3f20df22de3d.jpg)

```
INFO:spybot.api:got new event type -> START, from -> LC00..., timestamp -> 1538919421721

INFO:spybot.api:got new event type -> TEXT, from -> LC00..., timestamp -> 1538918596120, body -> Hello😍👍

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> H
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> e
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> l
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> l
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> o
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> 😍
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

INFO:spybot.api:event handler function yielded reply with type -> TEXT, to -> LC00..., body -> 👍
INFO:requests.packages.urllib3.connectionpool:Starting new HTTPS connection (1): bot.sapp.ir
INFO:spybot.api:sent message successfully

```

For more information see [Wiki](https://github.com/Pouriya-Jahanbakhsh/spybot/wiki).  
For contribution see [contribution guide](https://github.com/Pouriya-Jahanbakhsh/spybot/blob/master/CONTRIBUTING.md).
