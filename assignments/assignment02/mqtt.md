# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
client = mqtt.Client()
[17:01:00] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [17:01:00] DEBUG | Received CONNACK (0, 0)
2
Enter QoS level (0, 1, 2): 2
[17:01:09] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6520301002/temperature'', ... (1 bytes)
[17:01:09] PUBLISH REQUESTED | QoS=2 | Message='2' | msgid=1
Enter message to publish: [17:01:09] DEBUG | Received PUBREC (Mid: 1)
[17:01:09] DEBUG | Sending PUBREL (Mid: 1)
[17:01:09] DEBUG | Received PUBCOMP (Mid: 1)
[17:01:09] PUBLISHED | msgid=1
```

## Subscriber_qos.py Output

```
 client = mqtt.Client()
[17:00:11] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[17:00:11] DEBUG | Received CONNACK (0, 0)
[17:00:11] Connected with result code 0
[17:00:11] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6520301002', 2)]     
[17:00:11] DEBUG | Received SUBACK
```