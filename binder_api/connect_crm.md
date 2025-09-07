## Endpoint
`POST /crm/connect`

## Headers
| Header | Value | Required |
|--------|-------|----------|
| Content-Type | application/json | ✓ |
| X-Api-Key | API key | ✓ |
| Referer | your domain | ✓ |

*Ключ API и реферер могут быть переданы как URL параметры 

## Request Body

### Field Details
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| touchapi_source | string | ✓ | source аккаунта Touch-api |
| touchapi_token | string | ✓ | token аккаунта Touch-api |
| touchapi_login | string | ✓ | Platform login |
| crm_url | string | ✓ | CRM instance URL |
| crm_type | string | - | тип CRM* |
| touchapi_main | boolean | - | Main connection flag |
| touchapi_name | string | - | Custom connection name |
* примеры типов CRM: amocrm, bitrix24
> Рекомендуется указывать crm_type, хотя это необязательный параметр, так как не всегда можно определить тип по url. Например, для коробочных версий Bitrix24, размещенных на собственных серверах.


Пример 1 (только обязательные параметры):
```json
{
    "touchapi_source": "whatsapp",
    "touchapi_token": "uuid-token-format",
    "touchapi_login": "username",
    "crm_url": "domain.amocrm.ru"
}
```

Пример 2:
```json
{
    "touchapi_source": "whatsapp",
    "touchapi_token": "uuid-token-format",
    "touchapi_login": "username",
    "crm_url": "domain.amocrm.ru",
    "touchapi_main":true,
	"touchapi_name": "Имя аккаунта"
}
```
> Для Amocrm рекомендуется передавать "touchapi_name", так как этот параметр используется для формирования имени источника в Amocrm. Иначе в имя источника будет подставлено имя по умолчанию - если у аккаунта есть 'connected_phone', то [connected_phone] ([source]), если нет, то [login] ([source])