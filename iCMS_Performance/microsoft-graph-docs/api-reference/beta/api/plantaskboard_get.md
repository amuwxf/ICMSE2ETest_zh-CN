# <a name="get-plantaskboard"></a>获得 planTaskBoard

检索的属性和关系的 plantaskboard 对象。
## <a name="prerequisites"></a>先决条件
以下**范围**之一是执行此 API 所需的︰
 
Group.Read.All Group.ReadWrite.All

## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
GET /plans/<id>/bucketTaskBoard
GET /plans/<id>/progressTaskBoard
GET /plans/<id>/assignedToTaskBoard
```
## <a name="optional-query-parameters"></a>可选的查询参数
无

## <a name="request-headers"></a>请求标头
| 名称       | 类型 | 说明|
|:-----------|:------|:----------|
| 授权  | string  | 值应该设置为"载体 （访问令牌）" |

## <a name="request-body"></a>请求正文
请不要提供此方法请求正文。
## <a name="response"></a>响应
如果成功，此方法返回`200 OK`响应代码和[planTaskBoard](../resources/plantaskboard.md)对象在响应正文中的。
## <a name="example"></a>示例
##### <a name="request"></a>请求
下面是示例请求。
<!-- {
  "blockType": "request",
  "name": "get_plantaskboard"
}-->
```http
GET https://graph.microsoft.com/beta/plans/<id>/bucketTaskBoard
```
##### <a name="response"></a>响应
这里是响应的示例。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.plantaskboard"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 46

{
  "type": "type-value",
  "id": "id-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get planTaskBoard",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->