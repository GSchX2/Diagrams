```mermaid
sequenceDiagram
    Actor John
    Participant Shop
    Participant Server
    Participant Account
    John->>+Shop: Open shop page
    Shop->>+Server: Request shop data
    Server-->>-Shop: Sending data
    Shop->>Shop: Load shop
    John->>Shop: Clicked buy
    Shop->>John: Request payment form and account
    John-->>Shop: Info Payment and a account
    Shop->>+Account: Request account and funds
        Account->>Account: Validating account and funds information
    alt Account validated
        Account-->>Shop: Information Validated
        Shop->>+Server: Request products disponibility
        alt Produt Available
            Server-->>Shop: Disponibility checked
            Shop-->>Shop: Display message: transaction completed succefully message
        else Produto Unavailable
            Server-->>-Shop: Disponibility failed
            Shop-->>Shop: Display message: transaction incompleted product unavailable
        end
    else Account invalidated
        Account-->>-Shop: Information Invalidated
        Shop-->>-Shop: Display message: Invalid Account ou funds information
    end
```