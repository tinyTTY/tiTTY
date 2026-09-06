# tiTTY
**ti**ny**T**ele**TY**pe

⁍ Peer to Peer chat with iroh-gossip

⁍ Uses QUIC protocol, TLS 1.3

⁍ End to End encrypted chat

⁍ E2E file transfer planned

⁍ MacOS and iOS native apps

⁍ Web version planned

⁍ Data between users is direct

⁍ Global usernames with identiTTY server


## Architecture

```python
#### Chat
SwiftUI -> App Events -> FFI Bridge -> Rust Runtime -> Iroh Gossip

#### IdentiTTY
SwiftUI <- GraphQL -> centralized username registration (identiTTY) backed by private key challenge
private key stored on device is the guarantor for API usage which involves username validation
```

