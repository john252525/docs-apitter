## Открытие личного кабинета в интерфейсе Amocrm

### Общий флоу открытия iframe

```mermaid
sequenceDiagram
    participant Widget
    participant Amocrm
    participant BinderAPI
    participant ЛичныйКабинет

    Widget->>Amocrm: Отправка запроса с JWT токеном
    Amocrm->>BinderAPI: Передача запроса с токеном
    
    BinderAPI->>BinderAPI: Валидация JWT токена
    alt Токен валиден
        BinderAPI->>BinderAPI: Кодирование данных виджета (AES)
        BinderAPI-->>Widget: Возврат закодированных данных
        Widget->>ЛичныйКабинет: Открытие iframe с параметром data
        ЛичныйКабинет-->>Amocrm: Отображение в интерфейсе
    else Токен невалиден
        BinderAPI-->>Amocrm: Оповещение об ошибке
        Amocrm-->>Widget: Отображение ошибки
    end
```