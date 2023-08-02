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
  id: "alice@id.example.org",
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  attributeName: "lastName",
  attributeValue: "Peterson",
  signatures: [<AttributeSignatureReference>, ...]
}
~~~

### AttributeSignatureReference
~~~
{
  id: "alice@id.example.org",
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signerId: "bob@id.example.org",
  signatureId: "hdywbecfxztefwynezuxuevuw"
}
~~~

### AttributeSignature
~~~
{
  id: "alice@id.example.org",
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signerId: "bob@id.example.org",
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
  id: "alice@id.example.org",
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  attributeName: "lastName",
  attributeValue: "Peterson",
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
  id: "alice@id.example.org",
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  signerId: "bob@id.example.org",
  signatureId: "hdywbecfxztefwynezuxuevuw"
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
  isValid: true,
  type: "DNS" // valid values: "DNS" or "BLOCKCHAIN"
}
~~~
