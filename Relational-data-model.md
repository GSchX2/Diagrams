```mermaid
erDiagram
    Channels_users||..|{ Videos : has
    Channels_users||..o{ Subscription : has
    Channels_users}|..o{ notification : send
    Channels_users||..o{ comments : make
    Videos||..o{ comments : has
    Channels_users||..o{ Playlist : has
    Playlist}o..|{ Videos : has
    Videos||..o{ Likes : has
    Channels_users||..o{ Likes : gives
```
