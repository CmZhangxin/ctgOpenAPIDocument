#  customer_controller
## 1. getCustomerDetail
  根据客户Id查询客户详情，包括客户基本信息，客户联系信息以及客户属性。
### 1.1 描述
   根据您指定的客户Id查询客户，如果存在客户，会返回精确匹配该客户Id的客户基本信息，客户联系信息以及客户属性；如果不存在此客户，会返回“【C0300103-XXXX】客户信息为空！”的提示信息。
### 1.2 请求参数
   **HTTP动作**：get  
  
   **资源地址**：/customer/{custId}
     
|Type|Name|Description|Schema|
|---|---|---|---|
|**Header**|**X-APP-ID**  <br>*required*|China Telecom's APP-ID|string|
|**Header**|**X-APP-KEY**  <br>*required*|China Telecom's APP-KEY|string|
|**Header**|**X-CTG-Request-Id**  <br>*optional*|Request-Id|string|
|**Path**|**custOrderId**  <br>*required*|custOrderId|string|
   
### 1.3 返回参数  
|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[CommonResult](#commonresult)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|

### 1.4 示例

#### **样例1：查询客户id为123的客户**


#### 请求示例

    GET /api/customer/123

#### 返回示例
    200
    Content-Type: application/json
       { 
	     "id": "123",
	     "href": "/customer/123", 
	     "custName": "zhangsan",  
	     "custAddr": "番禺区", 
	     "custSubType": "1",
	     "custAreaGrade": "2" ,
	     "enterDate": "2018-03-21T09:41:32.102Z",
	     "distributorId": 0,
	     "secrecyLevel": "1",
	     "isInstead": 0,
	     "isRealName": 0,
	     "statusCd": "1",
	     "lastOrderItemId": 0,
	     "partyId":2,
	     "custAttr": [
	      {
		    "custAttrId":13
		    "attrId": 2,
		    "attrValueId": 2,
		    "attrValue": "saaa"
	      },
	      {
		    "custAttrId":14
		    "attrId": 3,
		    "attrValueId": 3,
		    "attrValue": "ccc"
	      }
	     ]  
       }

####**样例2：查询客户id为123的客户,只要输出custName,renterDate,custAttr字段**

#### 请求示例

    GET /api/customer/123/?fields=custName,enterDate,custAttr

#### 返回示例
    200
    Content-Type: application/json
	   { 
	     "id": "123",
	     "href": "/customer/123", 
	     "custName": "zhangsan",  
	     "enterDate": "2018-03-21T09:41:32.102Z",
	     "custAttr": [
	      {
		    "custAttrId":13
		    "attrId": 2,
		    "attrValueId": 2,
		    "attrValue": "saaa"
	      },
	      {
		    "custAttrId":14
		    "attrId": 3,
		    "attrValueId": 3,
		    "attrValue": "ccc"
	      }
	     ]  
       }


### 1.5 错误码
  
|HTTP Code|Description|Schema|
|---|---|---|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|