d3-MQTT-Topic-Tree
==================

MQTT topic tree viewer which is fed from a single websocket which outputs a node-red MQTT node subscribed to the top # (all topics).

Websocket output should be in the format of topic|payload

e.g.
MQTT Topic - /tg/message
MQTT Payload - Hello World

Websocket payload format: /tg/message|Hello World

The above formatting can be achieved in Node-Red utilising a simple flow such as:

```
[{"id":"a7c99df.f58366","type":"mqtt-broker","broker":"localhost","port":"1883","clientid":""},{"id":"86fbd2ea.79043","type":"websocket-listener","path":"/ws/pa","wholemsg":"false"},{"id":"f65c6f03.09a39","type":"websocket out","name":"","server":"86fbd2ea.79043","x":390.8888854980469,"y":308.8888854980469,"z":"3d8bd56a.c2742a","wires":[]},{"id":"161e0785.e9e1f8","type":"template","name":"","field":"payload","template":"{{& topic}}|{{& payload}}","x":253.88888549804688,"y":304.8888854980469,"z":"3d8bd56a.c2742a","wires":[["f65c6f03.09a39"]]},{"id":"f65f4f4c.09a0b","type":"mqtt in","name":"","topic":"#","broker":"a7c99df.f58366","x":123.88888549804688,"y":297.8888854980469,"z":"3d8bd56a.c2742a","wires":[["161e0785.e9e1f8"]]}]
```



-- d3
The Collapasable tree orginally came from here:
http://mbostock.github.io/d3/talk/20111018/tree.html
