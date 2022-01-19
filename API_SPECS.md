# Lithoverse API Spec

### Lithoverse database API to fetch NFTs and Collections

### https://api.lithoverse.xyz

#### _Response type_: application/json

---

---

## **_Types_**

- ### **TokenId**

_Description_: [collectionId, seriesId, serialNumber]

_Example_: `[ 90, 2, 1 ]`

---

- ### **Metadata**

_Description_: IPFS CID

_Example_:

`"QmS4VNxRoybsMYUXBLFiUSHQv43usFtYQUYzrhh6kRn7PT"`

---

- ### **NFT**

_Description_: Object containing NFT Data

_Example_:

`{ "attributes": [ { "Text": "Red" }, "Text": "Square" ], "copies": 1, "listingId": 24, "metadata": "QmS4VNxRoybsMYUXBLFiUSHQv43usFtYQUYzrhh6kRn7PT", "showOne": true, "tokenId": [ 90, 2, 1 ] }`

---

- ### **Collection**

_Description_: Array of NFTs

---

---

## **_Endpoints_**

- ### **/assets**

_Description_: Returns array of NFTs based on query paramaters

_Query Params_:

- owner: Address of owner of NFTs e.g. `?owner=5Cm9UPHSbDfzJiffXBkcqUoaiZJatRJAxqHu4UDL43sKV8Uv`
- token_ids: Range of Token Ids to search for e.g. `?token_ids=1&token_ids=100`
- collection_id: Limit responses to NFTs part of one collection e.g. `?collection_id=93`
- limit: Limit number of collections returned e.g. `?limit=100`

---

- ### **/collections**

_Description_: Returns array of NFT collections

_Query Params_: (Optional)

- limit: Limit number of collections returned e.g. `?limit=100`

---

- ### **/collections/{collection_id}**

_Description_: Returns a singular collection of NFTs by collection id

---

- ### **/collections/{owner_address}**

_Description_: Returns array of collections where owner owns at least one asset

_Query Params_: (Optional)

- limit: Limit number of collections returned e.g. `?limit=10`
