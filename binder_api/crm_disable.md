## Endpoint
`POST /crm/disable`

## Headers
| Header | Value | Required |
|--------|-------|----------|
| Content-Type | application/json | ✓ |
| X-Api-Key | API key | ✓ |
| Referer | your domain | ✓ |

*Ключ API и реферер могут быть переданы как URL параметры

## Body params

### Field Details
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| uuid | string | ✓ | Messenger UUID |

> UUID аккаунта мессендера.


Пример:
```json
{
	"uuid": "96d1c48e-dbb1-4d40-ac5a-4327bdd78592"
}
```


## Response
200 OK
```json
{
	"ok": true,
	"message": "Integration disabled",
	"data": [
		{
			"diabled_binds_count": 2, // количество отключенных связей, должно быть 2 и больше
			"delete_amocrm_sources": [
				// информация об удалении источников Amocrm
			],
			"delete_webhook": true // был ли удален вебхук из Tauch-api
		}
	]
}
```
