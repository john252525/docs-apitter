## Endpoint
`GET /crm/status`

## Headers
| Header | Value | Required |
|--------|-------|----------|
| Content-Type | application/json | ✓ |
| X-Api-Key | API key | ✓ |
| Referer | your domain | ✓ |

*Ключ API и реферер могут быть переданы как URL параметры

## Query params

### Field Details
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| crm_url | string | ✓ | CRM instance URL |
| crm_type | string | - | тип CRM* |

* примеры типов CRM: amocrm, bitrix24
> Рекомендуется указывать crm_type, хотя это необязательный параметр, так как не всегда можно определить тип по url. Например, для коробочных версий Bitrix24, размещенных на собственных серверах.


Пример:
```
https://bapi88.developtech.ru/api/v1/crm/status?crm_url=account.amocrm.ru&crm_type=amocrm
```
(пример предполагает, что ключ и реферер переданы в заголовках)

## Response
200 OK
```json
{
	"ok": true,
	"message": "CRM status",
	"data": {
		"crm_url": "account.amocrm.ru",
		"step": {
			"value": 5,
			"description": "CRM is installed and must be fully functional"
		}
	}
}
```
