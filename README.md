# markdown
# 8481

## Задание 1
```mermaid
flowchart TD
    A([Начало]) --> B[Кипячение воды]
    B --> C{Есть ли чай?}
    C -->|Да| D[Заварить чай]
    C -->|Нет| E[Купить чай]
    E --> D
    D --> F[Пить чай]
    F --> G([Конец])
```

## Задание 2
```mermaid
sequenceDiagram
    participant Клиент
    participant Приложение
    participant Сервер
    participant Водитель
    
    Клиент->>Приложение: Вызов такси
    Приложение->>Сервер: Запрос на такси
    Сервер->>Водитель: Поиск водителя
    Водитель->>Сервер: Подтверждение
    Сервер->>Приложение: Водитель найден
    Приложение->>Клиент: Такси едет
    Водитель->>Клиент: Забирает клиента
```

## Задание 3
```mermaid
classDiagram
    class Book {
        -String title
        -String author
        -String ISBN
        -Boolean isAvailable
        +borrow()
        +return()
    }
    
    class User {
        -String name
        -String userId
        -List~Book~ borrowedBooks
        +borrowBook()
        +returnBook()
    }
    
    class Library {
        -List~Book~ books
        -List~User~ users
        +addBook()
        +registerUser()
    }
    
    User "*" --> "0..*" Book : borrows
    Library "1" o-- "*" Book : contains
    Library "1" o-- "*" User : manages
```

## Задание 4
```mermaid
gantt
    title Разработка мобильного приложения
    dateFormat YYYY-MM-DD
    section Подготовка
    Анализ :a1, 2024-01-01, 5d
    section Дизайн
    Дизайн :a2, after a1, 7d
    section Разработка
    Фронтенд :a3, after a2, 10d
    Бэкенд :a4, after a1, 12d
    section Тестирование
    Тестирование :a5, after a3 a4, 5d
```

## Задание 5
```mermaid
graph TB
    subgraph Frontend
        A[React]
        B[Redux]
        C[Router]
    end
    
    subgraph Backend
        D[Node.js]
        E[Express]
        F[MongoDB]
    end
    
    subgraph Внешние сервисы
        G[Stripe]
        H[SendGrid]
    end
    
    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    E --> G
    E --> H
```

## Задание 6
```mermaid
stateDiagram-v2
    [*] --> Новый
    Новый --> Подтвержденный
    Подтвержденный --> Оплаченный
    Подтвержденный --> Отмененный
    Оплаченный --> Отправленный
    Отправленный --> Доставленный
    Доставленный --> [*]
    Отмененный --> [*]
```

## Задание 7
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
      Оплата: 2
    section Получение
      Получение билета: 5
      Сохранение: 4
```

## Задание 8
```mermaid
erDiagram
    USERS {
        int id
        string имя
        string email
    }
    
    POSTS {
        int id
        string содержание
        int автор_id
    }
    
    COMMENTS {
        int id
        string текст
        int пост_id
        int автор_id
    }
    
    LIKES {
        int пользователь_id
        int пост_id
    }
    
    SUBSCRIPTIONS {
        int кто_подписан
        int на_кого_подписан
    }
    
    USERS ||--o{ POSTS : создает
    USERS ||--o{ COMMENTS : пишет
    POSTS ||--o{ COMMENTS : имеет
    USERS }o--o{ POSTS : лайкает
    USERS }o--o{ USERS : подписывается
```

## Задание 9
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

## Задание 10
```mermaid
pie title Автомобили в России
    "Иномарки" : 45
    "Отечественные" : 35
    "Совместное производство" : 20
```
