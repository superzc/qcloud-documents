## 1. API Description

This API (SetTopicAttributes) is used to modify the attributes of a message topic. <font color="red">Please note that the topic name cannot be modified</font>

Domain for public network API request: <font style="color:red">cmq-topic-region.api.qcloud.com</font>

Domain for private network API request: <font style="color:red">cmq-topic-region.api.tencentyun.com</font>

> Whenever (including during alpha test) any public network downstream traffic is generated from the use of a public network domain, a fee will be charged. It is strongly recommended that users whose services are on the Tencent Cloud use **private network** domains, because no fee will be charged for the traffic consumed in the private network.

- region should be replaced with a specific region: gz (Guangzhou), sh (Shanghai), or bj (Beijing). The region value in the common parameters should be consistent with the region value of the domain. If there is an inconsistency, the request will be sent to the region specified by the domain.
- Public network domain requests both support http and https. Private network requests only support http.
- Some of the input parameters are optional. If not specified, the default value will be taken.
- All the output parameters will be returned to the user when the request is successful; otherwise, at least code, message, and requestId will be returned.

## 2. Input Parameters

The following request parameter list only provides API request parameters. For other parameters, refer to [Common Request Parameters](https://cloud.tencent.com/doc/api/431/5883).

| Parameter Name | Required | Type | Description |
|---------|---------|---------|---------|
| topicName | Yes | String| Topic name. It is unique under the same account in one region. The topic name is a string of no more than 64 characters, which can contain letters, numbers, and hyphens (-) and must begin with a letter. |
| maxMsgSize | No | Int | Maximum message length. Value range is 1024-65536 Bytes (1-64 K). Default is 65536. |


## 3. Output Parameters

| Parameter Name | Type | Description |
|---------|---------|---------|
| code | Int | 0: Succeeded; 4440: Topic does not exist. For the meanings of other returned values, please refer to [Error Codes](/doc/api/431/5903). |
| message | String | Error message. |
| requestId | String | ID of the request generated by server. When there is an internal error on the server, users can submit this ID to the backend to locate the problem. |


## 4. Example

Input:

```
 https://domain/v2/index.php?Action=SetTopicAttributes
 &topicName=test-Topic-123
 &maxMsgSize=1024
 &<Common request parameters>
```

Output:

```
{
"code" : 0,
"message" : "",
"requestId":"14534664555"
}
```







