# <a name="delete-message"></a>删除邮件

删除邮件。
## <a name="prerequisites"></a>先决条件
需执行此 API 之一以下**范围**︰ *Mail.ReadWrite* 
## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
DELETE /me/messages/<id>
DELETE /users/<id | userPrincipalName>/messages/<id>
DELETE /me/mailFolders/<id>/messages/<id>
DELETE /users/<id | userPrincipalName>/mailFolders/<id>/messages/<id>
```
## <a name="request-headers"></a>请求标头
| 名称       | 类型 | 说明|
|:---------------|:--------|:----------|
| 授权  | string  | 持有者<token>。 必需。 |

## <a name="request-body"></a>请求正文
请不要提供此方法请求正文。


## <a name="response"></a>响应
如果成功，此方法返回`204, No Content`响应代码。 它不返回任何响应正文中。

## <a name="example"></a>示例
##### <a name="request"></a>请求
下面是示例请求。
<!-- {
  "blockType": "request",
  "name": "delete_message"
}-->
```http
DELETE https://graph.microsoft.com/v1.0/me/messages/<id>
```
##### <a name="response"></a>响应
这里是响应的示例。 
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Delete message",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->