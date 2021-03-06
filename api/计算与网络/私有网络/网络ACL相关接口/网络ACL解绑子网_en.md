## 1. API Description

This API (DeteleSubnetAclRule) is used to unbind network ACLs from subnets.
Domain for API request:<font style="color:red">vpc.api.qcloud.com</font> 
 

## 2. Input Parameters
The following request parameter list only provides API request parameters. Common request parameters need to be added when the API is called. For more information, refer to <a href="/doc/api/372/4153" title="Common request parameters">Common Request Parameters</a>. The Action field for this API is DeteleSubnetAclRule.

| Parameter Name | Required | Type | Description |
|---------|---------|---------|---------|
| vpcId | Yes | String | VPC ID of the subnet, which can be vpcId or unVpcId. unVpcId is recommended. You can query this through API <a href="http://www.qcloud.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E7%A7%81%E6%9C%89%E7%BD%91%E7%BB%9C%E5%88%97%E8%A1%A8" title="DescribeVpcEx">DescribeVpcEx</a>.  |
| networkAclName | Yes | String | Network ACL name, which can be 1-60 Chinese or English characters (uppercase and lowercase). Numbers and underscores are also supported. The name must be unique under the same VPC.  | 
| subnetIds.n | Yes | Array | List of subnet IDs assigned by the system. Both subnetId and unSubnetId are supported. unSubnetId is recommended. You can query it by using the API <a href="http://www.qcloud.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E5%AD%90%E7%BD%91%E5%88%97%E8%A1%A8" title="DescribeSubnetEx">DescribeSubnetEx</a>.  |  


 

## 3. Output Parameters

| Parameter Name | Type | Description |
|---------|---------|---------|
| code | Int | Error code, 0:  Succeeded, other values:  Failed.  |
| message |  String | Error message.  |


  ## 4. Error Code Table
  The following error code list only provides the business logic error codes for this API. For additional common error codes, refer to <a href="https://www.qcloud.com/doc/api/245/4924" title="VPC Error Codes">VPC Error Codes</a>.
 
| Error code | Description |
|---------|---------|
| InvalidVpc.NotFound | Invalid VPC. VPC resource does not exist. Please verify that the resource information you entered is correct. You can query VPCs via the API <a href="http://www.qcloud.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E7%A7%81%E6%9C%89%E7%BD%91%E7%BB%9C%E5%88%97%E8%A1%A8" title="DescribeVpcEx">DescribeVpcEx</a>.  |
| InvalidNetworkAclID.NotFound | Invalid network ACL ID. Network ACL ID does not exist. Please verify that the resource information you entered is correct. You can query network ACL IDs via the API <a href="https://www.qcloud.com/doc/api/245/1441" title="DescribeNetworkAcl">DescribeNetworkAcl</a>.  |



## 5. Example
 
Input
<pre>
  https://vpc.api.qcloud.com/v2/index.php?Action=DeteleSubnetAclRule
  &<<a href="https://www.qcloud.com/doc/api/229/6976">Common request parameters</a>>
  &vpcId=vpc-erxok83l
  &networkAclId=acl-e9dbyl8s
  &subnetIds.0=subnet-i6mdq6ra

</pre>

Output
```

{
    "code": 0,
    "message": ""
}

```


