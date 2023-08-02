## DistIN Protocol Documentation

# Objects

### AttributeSignatureReference
~~~
{
  id: "bob@id.example.org",
  signatureId: "hdywbecfxztefwynezuxuevuw"
}
~~~

# Actions

### ~/DistIN/attribute
Request:
~~~
{
  id: "alice@id.example.org",
  // for public attributes:
  attributeName: "lastName"
  // or for private attributes:
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf"
}
~~~
Response:
~~~
{
  attributeId: "ndi3xmjoixyjeu42cnhfiwjd32mh3xhf",
  attributeName: "lastName",
  attributeValue: "Peterson",
  signatures: [<AttributeSignatureReference>, ...]
}
~~~

### ~/DistIN/signAttribute
Request:
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

### ~/DistIN/verifyService
Request:
~~~
{
  service: "id.example.org"
}
~~~
Response:
~~~
{
  isValid: true,
  type: "DNS" // valid values: "DNS" or "BLOCKCHAIN"
}
~~~
