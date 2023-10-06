# DistIN resource objects
The following are the resource objects that can be addressed via the REST interface.

## PublicKey
~~~
{
  identity: "alice@id.example.org",
  key: "<---BASE64--->",
  algorithm : "DILITHIUM",
  date: "2023/01/30",
  signature: "<---BASE64--->"
}
~~~

## Attribute
~~~
{
  id: "ndi3xmj...",
  name: "lastName",
  mimeType: "text/plain",
  value: "Peterson",
  identity: "alice@id.example.org",
  signatures: [<AttributeSignatureReference>,..]
}
~~~

## AttributeSignatureReference
~~~
{
  identity: "alice@id.example.org",
  attribute: "ndi3xmj...",
  signer: "bob@id.example.org",
  signature: "hdywbecfxztefwynezuxuevuw"
}
~~~

## AttributeSignature
~~~
{
  id: "hdywbecfxztefwynezuxuevuw"
  identity: "alice@id.example.org",
  attribute: "ndi3xmj...",
  signer: "bob@id.example.org",
  date: "2023/01/30",
  signature: "<---BASE64--->"
}
~~~

## ServiceVerificationState
~~~
{
  valid: true,
  type: "DNS"
}
~~~
