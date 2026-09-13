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

#### Chat

```python
SwiftUI -> App Events -> FFI Bridge -> Rust Runtime -> Iroh Gossip
```
#### IdentiTTY

```python
SwiftUI <- GraphQL -> IdentiTTY
```
The identiTTY server is a centralized username registration service backed by private key challenge
private key stored on device is the guarantor for API usage which involves username validation


## User Experience

#### First Launch

A first time user is prompted to select an identiTTY.

The identiTTY is globally unique and is open for registration. This value is used as a human-readable identifier, which is linked in a coordination server to a public/private key pair, for which the user holds the private key on their device locally.

Now the user has a claim to a human-readable ID, and because this is a gate to the app, further actions in the app are validated by this identiTTY.

Two options:
#### Chat using the coordination server (centralized coordination)
- add 'Jane' as a contact
- send 'Jane' a direct chat request
- The coordination server holds this request in queue
- Jane's device(s) poll the coordination server for requests in queue (when the UI to accept direct chats is open)
- Jane accepts the direct chat request
- EndpointID used

#### Chat using shared tickets (decentralized coordination (after centralized identity validation))
- create a room
- open room details view
- copy room ticket
- send ticket blob to another person through any communication channel (email, sms, somewhere that copying the value to clipboard is easy)
- recipient pastes ticket blob into the Join Room interface
- communication is established without the coordination server. No record or trace that two identiTTYs communicated with one another; but the app has already validated that the app user is who they say they are.


