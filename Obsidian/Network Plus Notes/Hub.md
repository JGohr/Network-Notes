### Definition of a hub: 
"A network hub is a node that broadcasts data to every computer or Ethernet-based device connected to it." - https://www.techtarget.com/searchnetworking/definition/hub

Hubs operate at Layer 1 (Physical Layer) because all the device is doing is taking incoming transmissions and repeating them out to any clients connected to itself. If this device used any type of filtering it would not be considered a layer 1 device.
***
Hubs have a singular collision domain since all traffic is being repeated to every device & a singular broadcast domain for the same reason.

Hubs operate in "Half-Duplex mode", this means traffic can only be communicated when no other devices are communicating across the same medium. If two devices were communicating at the same time, this would cause a collision. A great representation of this collision is to imagine if two walkie talkies tried to communicate over the same channel at the same time.