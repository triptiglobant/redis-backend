### ✅ 1. **Project Description**

####  📖 Overview

This application integrates Redis as a backend for storing I18n translation strings in a Ruby on Rails application. It allows fast retrieval of translation data, improving performance in multilingual apps.

---

#### 🧾 About

This project is focused solely on using Redis as a storage mechanism for I18n translations. It does not include any management UI or editing features. Instead, it provides a simple, performant, Redis-backed solution for reading and writing translation strings.

It's particularly useful for applications where translations are updated frequently or need to be accessed quickly across distributed environments.

---

### 🧑‍💼 2. **Key Features**

Highlight the core user-facing features:

#### 🌟 Features

- Fast loading of translations using Redis
- Fallback support for missing translations
- Long-term caching for better performance
- Redis-based storage that supports editing/clearing translations
- Easy integration into multilingual Rails apps

---

### 🛠️ 3. **How to Use**


1. Launch the application to check application is ready

```
rails server
```

2. To check the functionality, start console of the application

```
rails console
```

3. Add translations using the UI or console:

```
redis_backend = TolkRedisBackend.new
redis_backend["greetings"] = "Hello"
```

4. To read translations

```
redis_backend = TolkRedisBackend.new
redis_backend["greetings"] => # Hello
```

5. Edit translations using the UI or console:

```
redis_backend = TolkRedisBackend.new
redis_backend["greetings"] = "Bye"
redis_backend["greetings"] => # Bye
```

---

### 🧹 4. **Managing Translations**

You can clear Redis-stored translations:

```
redis_backend = RedisBackend.new
redis_backend.clear_old_entries
```

---

### ⚠️ 5. **Requirements**

Let users know what's needed to run this app:

#### 📋 Requirements

- Ruby 3.2.2+
- Rails 7/8
- Redis installed and running

Install Redis if needed:

#### On macOS with Homebrew
```
brew services start redis
```

To check if it's running:
```
brew services list
```

If you don’t have Redis installed:
```
brew install redis
```

#### On Ubuntu / Linux
```
sudo service redis-server start
```

Or:
```
sudo systemctl start redis
```

#### ✅ Confirm Redis Is Running

Once started, try:

```
redis-cli
```
##### Input:

127.0.0.1:6379> `ping`

##### Expected output:

`PONG`

---

### 💡 6. **Environment Variables**

If Redis URL or others are configurable:

#### 🔧 Environment Variables

| Variable     | Description              | Default                     |
|--------------|--------------------------|-----------------------------|
| `REDIS_URL`  | Redis connection string  | `redis://localhost:6379/1` |

Set it in your environment or `.env` file.

---

### 🙋‍♀️ 7. **FAQ or Common Issues**

Help users troubleshoot:

#### ❓ FAQ

##### ⚠️ Redis connection error?
Ensure Redis is running:

For Mac `brew services start redis` or for Ubuntu/Linux `sudo service redis-server start`

Or manually:

```
redis-server
```

##### 🚂 Is Rails 7 or 8 required?
No, this approach can be integrated into any Rails application. However, this particular implementation has been built and tested using Rails 8, so using Rails 8 is recommended for compatibility.

##### 💎 Is Ruby 3.2.2+ required?
No, the required Ruby version depends on the version of Rails being used. Ensure that your Ruby version is compatible with the Rails version you're working with.
