# DistIN Protocol Documentation - REST API

## URL structure

https://{DistIN domain}/distin/{DistIN action}

## DistIN ID structure

{identiy name}@{DistIN domain}

## Identity attributes

[-> Common attriutes](CommonAttributes.md)

## HTTP Header Parameters

### POST Request Headers
- **DistIN-ID**: The ID of the requesting identity
- **DistIN-Signature**: The signature of the body by the requesting identity
- **DistIN-Token**: The token issued to the requesting identity by the service

### Response Header
- **DistIN-Signature**: The signature of the body by the service

## DistIN Objects

DistIN objects are resource objects targeted by the REST API.

[-> DistIN Objects](Objects.md)

## DistIN Actions

DistIN actions are resource locations (part of the URL) targeted by the REST API.

[-> DistIN Actions](Actions.md)


