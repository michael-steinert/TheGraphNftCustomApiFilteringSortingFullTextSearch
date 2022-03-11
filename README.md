# TheGraph a NFT custom API with Filtering, Sorting and Full Text Search

* TheGraph is a Web3 Protocol that allows to build and deploy open APIs called Subgraphs to a decentralized Network for Indexing and Querying all EVM-compatible Blockchain Networks
* The Reason why TheGraph is necessary is that by Default it is not easy to Interact with Data beyond basic Read  Operation directly to a Smart Contract
* TheGraph allows to subscribe the Data as well as the Smart Contract that should be indexed by the Protocol (TheGraph)
* After Subscribing the Data will be indexed and served from a GraphQL Endpoint
* The GraphQL Endpoints gives the modern Queries that are expected by most Users in modern Applications

## TheGraph

### Types of Subgraphs

* Subgraph Studio allow deploying Subgraphs into the decentralized Network
* Hosted Service is a centralized Version of TheGraph

### Useful Commands

* Initialize TheGraph: `graph init --from-contract 0x5180db8f5c931aae63c74266b211f580155ecac8 --contract-name Token --network mainnet --index-events`
* Generate Code: `graph codegen`
* Authenticate local CLI to custom API: `graph auth`
* Deploy Subgraph: `yarn deploy`

### Example Queries

#### Querying

```graphql
{
    tokens(first: 5) {
        id
        tokenID
        tokenURI
        externalURL
        image
        name
        description
        type
        sun
        moon
        rising
        updatedAtTimestamp
        owner {
            id
        }
    }
}
```

#### Filtering

```graphql
{
    tokens(
        where: {
            sun_contains: "capricorn"
        }
    ) {
        sun
        name
    }
}
```

#### Full text search

```graphql
{
    covenSearch(
        text: "'CRUSH PEARLS IN YOUR FISTS'"
    ) {
        id
        name
        description
    }
}
```
