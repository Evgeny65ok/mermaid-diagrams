```markdown
### Приготовление чая
```mermaid
flowchart TD
    A([Начало]) --> B[Кипячение воды]
    B --> C{Есть ли чай?}
    C -->|Да| D[Заварить чай]
    C -->|Нет| E[Купить чай]
    E --> D
    D --> F[Пить чай]
    F --> G([Конец])

### Заказ такси
```mermaid
sequenceDiagram
    participant Клиент
    participant Приложение
    participant Сервер
    participant Водитель

    Клиент->>Приложение: Вызывает такси
    activate Приложение
    Приложение->>Сервер: Отправляет запрос
    activate Сервер
    Сервер->>Водитель: Ищет свободного водителя
    activate Водитель
    Водитель->>Сервер: Принимает заказ
    deactivate Водитель
    Сервер->>Приложение: Водитель найден
    deactivate Сервер
    Приложение->>Клиент: Уведомляет клиента
    deactivate Приложение
    Водитель->>Клиент: Забирает клиента
```



### Библиотечная система
```mermaid
classDiagram
    class Book {
        -String title
        -String author
        -String ISBN
        -Boolean isAvailable
        +borrow() void
        +return() void
    }

    class User {
        -String name
        -String userId
        -List~Book~ borrowedBooks
        +borrowBook(book: Book) void
        +returnBook(book: Book) void
    }

    class Library {
        -List~Book~ books
        -List~User~ users
        +addBook(book: Book) void
        +registerUser(user: User) void
    }

    User "*" --> "0..*" Book : borrows
    Library "1" o-- "*" Book : contains
    Library "1" o-- "*" User : manages
```

### Разработка мобильного приложения
```mermaid
gantt
    title Разработка мобильного приложения
    dateFormat YYYY-MM-DD
    section Подготовка
    Анализ требований :a1, 2024-01-01, 5d
    section Дизайн
    UI/UX дизайн :a2, after a1, 7d
    section Разработка
    Фронтенд-разработка :a3, after a2, 10d
    Бэкенд-разработка :a4, after a1, 12d
    section Тестирование
    Тестирование :a5, after a3 a4, 5d
```
### Веб-приложение
```mermaid
graph TB
    subgraph "Frontend"
        A[React]
        B[Redux]
        C[Router]
    end

    subgraph "Backend"
        D[Node.js]
        E[Express]
        F[MongoDB]
    end

    subgraph "Внешние сервисы"
        G[Stripe]
        H[SendGrid]
    end

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    E -- Платежи --> G
    E -- Email --> H
```

### Заказ в интернет-магазине
```mermaid
stateDiagram-v2
    [*] --> Новый
    Новый --> Подтвержденный
    Подтвержденный --> Оплаченный
    Подтвержденный --> Отмененный

    state Оплаченный {
        [*] --> Ожидание_оплаты
        Ожидание_оплаты --> Оплата_успешна
        Ожидание_оплаты --> Оплата_неуспешна
    }

    Оплаченный --> Отправленный
    Отправленный --> Доставленный
    Доставленный --> Возвращенный
    Доставленный --> [*]
    Отмененный --> [*]
    Возвращенный --> [*]
```

### Покупка билетов в кино
```mermaid
journey
    title Покупка билетов в кино
    section Поиск фильма
      Просмотр афиши: 5
      Выбор фильма: 4
    section Выбор сеанса
      Выбор времени: 4
      Выбор кинотеатра: 3
    section Выбор мест
      Выбор места: 3
      Оплата мест: 2
    section Оплата
      Ввод данных: 1
      Подтверждение: 2
    section Получение
      Получение билета: 5
      Сохранение: 4
```

### Социальная сеть
```mermaid
erDiagram
    USERS {
        int id PK
        string имя
        string email
    }

    POSTS {
        int id PK
        string содержание
        int автор_id FK
    }

    COMMENTS {
        int id PK
        string содержание
        int пост_id FK
        int автор_id FK
    }
    LIKES {
        int пользователь_id FK
        int пост_id FK
    }
    SUBSCRIPTIONS {
        int кто_подписан FK
        int на_кого_подписан FK
    }
    USERS ||--o{ POSTS : создает
    USERS ||--o{ COMMENTS : пишет
    POSTS ||--o{ COMMENTS : имеет
    USERS }o--o{ POSTS : лайкает
    USERS }o--o{ USERS : подписывается
```

### Сервис доставки еды
```mermaid
flowchart TD
    A([Начало]) --> B[Выбор ресторана]
    B --> C[Выбор блюд]
    C --> D[Оформление заказа]
    D --> E[Оплата]
    E --> F[Приготовление]
    F --> G[Доставка]
    G --> H[Получение]
    H --> I([Конец])
```

### Автомобили в России
```mermaid
pie title Автомобили на российском рынке
    "Иномарки" : 45
    "Отечественные" : 35
    "Совместное производство" : 20
```