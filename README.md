# effective-mobile-devops-test# 🚀 Тестовое задание Effective Mobile (DevOps)

## 📌 Описание

Проект представляет собой простое веб-приложение, развернутое с использованием **Docker** и **Docker Compose**.

В качестве backend используется Python HTTP-сервер, который возвращает:

```
Hello from Effective Mobile!
```

Перед backend расположен **Nginx**, который работает как reverse proxy.

---

## 🏗 Архитектура

```
[ Client ]
     |
     v
[ Nginx :80 ]
     |
     v
[ Backend :8080 ]
```

* **Nginx**

  * слушает порт **80**
  * проксирует запросы в backend
* **Backend**

  * работает на порту **8080**
  * доступен только внутри Docker-сети

---

## ⚙️ Используемые технологии

* Docker
* Docker Compose
* Nginx
* Python (http.server)

---

## ▶️ Запуск проекта

```bash
docker compose up --build
```

---

## ✅ Проверка работы

Открыть в браузере:

```
http://localhost
```

или выполнить:

```bash
curl http://localhost
```

Ожидаемый результат:

```
Hello from Effective Mobile!
```

---

## ❤️ Проверка healthcheck

```bash
curl http://localhost/health
```

---

## 🔐 Особенности реализации

* backend не пробрасывает порт наружу
* используется внутренняя docker-сеть
* nginx — единственная точка входа
* добавлены healthcheck'и
* backend запускается не от root пользователя

---

## 👨‍💻 Автор

Кандидат на позицию DevOps (Junior)
