d3-MQTT-Topic-Tree
==================

MQTT topic tree viewer which is fed from a single websocket which outputs a node-red MQTT node subscribed to the top # (all topics).

Websocket output should be in the format of topic|payload

e.g.
MQTT Topic - /tg/message
MQTT Payload - Hello World

Websocket format outout /tg/message|Hello World

-- d3
The Collapasable tree orginally came from here:
http://mbostock.github.io/d3/talk/20111018/tree.html
