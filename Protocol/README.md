## DistIN Protocol Documentation - restful API

# HTTP Header Parameters

### POST Request Headers
- **DistIN-ID**: The ID of the requesting identity
- **DistIN-Signature**: The signature of the body by the requesting identity

### Response Header
- **DistIN-Signature**: The signature of the body by the service

# JSON Objects

### Attribute
~~~
{
  id: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  identity: "alice@id.example.org",
  name: "lastName",
  value: "Peterson",
  signatures: [<AttributeSignatureReference>, ...]
}
~~~

### AttributeSignatureReference
~~~
{
  identity: "alice@id.example.org",
  attribute: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signer: "bob@id.example.org",
  signature: "hdywbecfxztefwynezuxuevuw"
}
~~~

### AttributeSignature
~~~
{
  id: "hdywbecfxztefwynezuxuevuw"
  identity: "alice@id.example.org",
  attribute: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signer: "bob@id.example.org",
  date: "2023/01/30",
  signature: "<---BASE64--->"
}
~~~

# Actions

### [GET] ~/DistIN/attribute
Request URL:
~~~
~/DistIN/attribute?id=alice@id.example.org&attributeName=lastName
or
~/DistIN/attribute?id=alice@id.example.org&attributeId=ndi3xmjoixyjeu42cnhfiwjd32mh3xhf
~~~
Response (Attribute):
~~~
{
  id: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  identity: "alice@id.example.org",
  name: "lastName",
  value: "Peterson",
  signatures: [<AttributeSignatureReference>, ...]
}
~~~

### [POST] ~/DistIN/attributeSignatureReference
Request URL:
~~~
~/DistIN/attribute
~~~
Request Body (AttributeSignatureReference):
~~~
{
  identity: "alice@id.example.org",
  attribute: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signer: "bob@id.example.org",
  signature: "hdywbecfxztefwynezuxuevuw"
}
~~~
Response:
~~~
{ }
~~~

### [GET] ~/DistIN/serviceVerificationState
Request:
~~~
~/DistIN/serviceVerificationState?service=id.example.org
~~~
Response:
~~~
{
  valid: true,
  type: "DNS" // valid values: "DNS" or "BLOCKCHAIN"
}
~~~
