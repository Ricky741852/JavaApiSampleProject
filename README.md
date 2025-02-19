# Java API Sample Project

## 📌 專案概述

本專案是一個基於 **Spring Boot** 的 RESTful API，提供使用者管理功能（CRUD）。目前支援本地端 **SQL Server** 及雲端 **PostgreSQL (Railway 部署)**。

## 🛠 工具和框架

- **後端框架**: Spring Boot
- **資料庫**: SQL Server / PostgreSQL
- **版本控制**: GitHub
- **雲端部署**: Railway

## 🚀 環境設定

### 1️⃣ **建立本地環境**

1. **安裝 JDK 17+**
2. **安裝 SQL Server (或 PostgreSQL)**
3. **設定 `application.properties`**
   - 第一次部署時使用 `spring.jpa.hibernate.ddl-auto=drop-create` 來建立資料表，之後請改回 `update`。
4. **啟動應用程式**
   ```sh
   mvn spring-boot:run
   ```

### 2️⃣ **雲端部署 (Railway)**

1. **註冊 Railway 並建立 PostgreSQL 資料庫**
2. **設定 `application-dev.properties`**
   ```properties
   # DATASOURCE
   spring.datasource.url=jdbc:postgresql://${PGHOST}:${PGPORT}/${PGDATABASE}
   spring.datasource.username=${POSTGRES_USER}
   spring.datasource.password=${POSTGRES_PASSWORD}
   ```
3. **直接透過 Railway 內建功能連結 GitHub Repositories 進行 CI/CD 自動部署**

## 📡 API 介面文件

### 1️⃣ **取得所有使用者**

```
GET /users
```

**回應範例**

```json
[
  {"id": 1, "name": "Alice", "email": "alice@example.com"},
  {"id": 2, "name": "Bob", "email": "bob@example.com"}
]
```

### 2️⃣ **新增使用者**

```
POST /users
```

**請求 Body（JSON）**

```json
{
  "name": "Alice",
  "email": "alice@example.com"
}
```

**回應範例**

```json
{"id": 1, "name": "Alice", "email": "alice@example.com"}
```

### 3️⃣ **根據 ID 取得使用者**

```
GET /users/{id}
```

**回應範例**

```json
{"id": 1, "name": "Alice", "email": "alice@example.com"}
```

### 4️⃣ **更新使用者資訊**

```
PUT /users/{id}
```

**請求 Body（JSON）**

```json
{
  "name": "Alice Updated",
  "email": "alice.updated@example.com"
}
```

**回應範例**

```json
{"id": 1, "name": "Alice Updated", "email": "alice.updated@example.com"}
```

### 5️⃣ **刪除使用者**

```
DELETE /users/{id}
```

**回應範例**

```
204 No Content
```

## 📝 備註

- 本專案支援 **本地 SQL Server** 與 **Railway PostgreSQL**。
- 若有問題，請開 Issue 或 PR。
- Railway 服務網址：[`https://javaapisampleproject-production.up.railway.app`](https://javaapisampleproject-production.up.railway.app)

---

✍ **作者**: [Ricky741852](https://github.com/Ricky741852/)

