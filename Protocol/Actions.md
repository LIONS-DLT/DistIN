
# DistIN actions

## GET actions

| GET | INPUT | RESPONSE |
|----|----|----|
| publicKey | id | [PublicKey] |
| attribute | id, atributeId | [Attribute] |
| attribute | id, attributeName | [Attribute] |
| attributeSignature | id | [AttributeSignature] |
| serviceVerificationState | service | [ServiceVerificationState] |
| authenticate | id, challenge | [Signature] |
| signatureRequests | - | [SignatureRequest][] |

## POST actions

| POST | INPUT | RESPONSE |
|----|----|----|
| attribute | [Attribute] | [Attribute] |
| attributeSignatureReference | [AttributeSignatureReference] | [AttributeSignatureReference] |
| attributeSignature | [AttributeSignature] | [AttributeSignature] |
| signatureResponse | [Signature] | - |

## PUT actions

| PUT | INPUT | RESPONSE |
|----|----|----|
| publicKey | [PublicKey] | [PublicKey] |
| attribute | [Attribute] | [Attribute] |
| attributeSignature | [AttributeSignature] | [AttributeSignature] |

## DELETE actions

| DELETE | INPUT | RESPONSE |
|----|----|----|
| attribute | id, attributeId | - |
| attributeSignature | id, signatureId | - |

 # Resource permissions

| RESOURCE | GET | POST | PUT | DELETE |
|----|----|----|----|----|
| publicKey | all | - | owner | - |
| attribute | all | owner | owner | owner |
| attributeSignatureReference | - | all | - | - |
| attributeSignature | all | owner | owner | owner |
| serviceVerificationState | all | - | - | - |
| authenticate | all | - | - | - |
| signatureRequests | owner | - | - | - |
| signatureResponse | - | owner | - | - |
 
