## Notes about using VerneMQ with (m)TLS

This short guide is for a simplified path to a containerized VerneMQ with TLS and Mutual TLS Auth support.

### TLS version

VerneMQ supports TLS v1.2, but connecting to a TLS-enabled VerneMQ using modern TLS v1.3 current fails.
As TLS comes with a performane and security impact (see notes below), 
support for TLS v1.3 can be an notable improvement.

See [VerneMQ-Issue-936](https://github.com/vernemq/vernemq/issues/936) for details


### Docker composition for TLS-enabled VernemQ

```
...
```

### Testing (m)TLS

```
mosquitto_sub --tls-version tlsv1.2 \
  --cert $CERT_PATH \
  --key $KEY_PATH \
  --cafile $CA_PATH \
  -h localhost -p 8883 -t '#' -d
```


### References:

- https://docs.vernemq.com/guides/not-a-tuning-guide#a-note-on-tls
- https://github.com/vernemq/vernemq/issues/936

