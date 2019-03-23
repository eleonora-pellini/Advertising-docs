---
title: GetEditorialReasonsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the reasons why the specified entities failed editorial review and whether the issue is appealable.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# GetEditorialReasonsByIds Service Operation - Campaign Management
Gets the reasons why the specified entities failed editorial review and whether the issue is appealable.

> [!NOTE]
> Editorial rejection reasons and appeals are not yet supported for responsive search ads. Support will be added in a future release e.g., Q1 calendar year 2019. 

## <a name="request"></a>Request Elements
The *GetEditorialReasonsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that contains the specified entities.|**long**|
|<a name="entityidtoparentidassociations"></a>EntityIdToParentIdAssociations|A list of  [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) objects that each contain the unique system identifier of an entity such as ad or keyword, and the identifier of its parent. An ad group is the parent of an ad or keyword.<br/><br/>The list must include all ads or all keywords which failed editorial review. The list cannot include a mix ads and keywords. The list can contain a maximum of 1,000 identifiers.|[EntityIdToParentIdAssociation](entityidtoparentidassociation.md) array|
|<a name="entitytype"></a>EntityType|The type of entities that the entity list contains.|[EntityType](entitytype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetEditorialReasonsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="editorialreasons"></a>EditorialReasons|An array of [EditorialReasonCollection](editorialreasoncollection.md) objects that corresponds directly to the [EntityIdToParentIdAssociation](entityidtoparentidassociation.md) objects that you specified in the request. Each object identifies the reason for the failure and whether it is appealable. Items of the list may be returned as null. For each list index where an [EditorialReasonCollection](editorialreasoncollection.md) was not retrieved, the corresponding element will be null.<br/><br/>If the entity had not failed editorial review, the corresponding item in this collection is NULL. In addition, the item will be NULL if the specified ad or keyword identifier is not valid.|[EditorialReasonCollection](editorialreasoncollection.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br/><br/>The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <Action mustUnderstand="1">GetEditorialReasonsByIds</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetEditorialReasonsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <AccountId>ValueHere</AccountId>
      <EntityIdToParentIdAssociations i:nil="false">
        <EntityIdToParentIdAssociation>
          <EntityId>ValueHere</EntityId>
          <ParentId>ValueHere</ParentId>
        </EntityIdToParentIdAssociation>
      </EntityIdToParentIdAssociations>
      <EntityType>ValueHere</EntityType>
    </GetEditorialReasonsByIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetEditorialReasonsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
      <EditorialReasons d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <EditorialReasonCollection>
          <AdGroupId>ValueHere</AdGroupId>
          <AdOrKeywordId>ValueHere</AdOrKeywordId>
          <AppealStatus>ValueHere</AppealStatus>
          <Reasons d4p1:nil="false">
            <EditorialReason>
              <Location d4p1:nil="false">ValueHere</Location>
              <PublisherCountries d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <a1:string>ValueHere</a1:string>
              </PublisherCountries>
              <ReasonCode>ValueHere</ReasonCode>
              <Term d4p1:nil="false">ValueHere</Term>
            </EditorialReason>
          </Reasons>
        </EditorialReasonCollection>
      </EditorialReasons>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e523="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e523:KeyValuePairOfstringstring>
              <e523:key d4p1:nil="false">ValueHere</e523:key>
              <e523:value d4p1:nil="false">ValueHere</e523:value>
            </e523:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </GetEditorialReasonsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetEditorialReasonsByIdsResponse> GetEditorialReasonsByIdsAsync(
	long accountId,
	IList<EntityIdToParentIdAssociation> entityIdToParentIdAssociations,
	EntityType entityType)
{
	var request = new GetEditorialReasonsByIdsRequest
	{
		AccountId = accountId,
		EntityIdToParentIdAssociations = entityIdToParentIdAssociations,
		EntityType = entityType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetEditorialReasonsByIdsAsync(r), request));
}
```
```java
static GetEditorialReasonsByIdsResponse getEditorialReasonsByIds(
	java.lang.Long accountId,
	ArrayOfEntityIdToParentIdAssociation entityIdToParentIdAssociations,
	EntityType entityType) throws RemoteException, Exception
{
	GetEditorialReasonsByIdsRequest request = new GetEditorialReasonsByIdsRequest();

	request.setAccountId(accountId);
	request.setEntityIdToParentIdAssociations(entityIdToParentIdAssociations);
	request.setEntityType(entityType);

	return CampaignManagementService.getService().getEditorialReasonsByIds(request);
}
```
```php
static function GetEditorialReasonsByIds(
	$accountId,
	$entityIdToParentIdAssociations,
	$entityType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetEditorialReasonsByIdsRequest();

	$request->AccountId = $accountId;
	$request->EntityIdToParentIdAssociations = $entityIdToParentIdAssociations;
	$request->EntityType = $entityType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetEditorialReasonsByIds($request);
}
```
```python
response=campaignmanagement_service.GetEditorialReasonsByIds(
	AccountId=AccountId,
	EntityIdToParentIdAssociations=EntityIdToParentIdAssociations,
	EntityType=EntityType)
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  
