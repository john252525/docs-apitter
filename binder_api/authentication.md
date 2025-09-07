## Base URL
`https://bapi88.apitter.com/api/v1`

## Aутентификация

**на выбор через:**
- url параметр: `?key=api_key`
- заголовок: `X-Api-Key: api_key`

**Требование:** Предварительная регистрация referer в системе. Необходимо добавить домен клиента в конфиг.

---

Ответ при ошибке аутентификации
`403 Unauthorized`
```json
{
	"ok": false,
	"message": "Unauthorized",
	"errors": [
		"Authorization error",
		""
	]
}
```
