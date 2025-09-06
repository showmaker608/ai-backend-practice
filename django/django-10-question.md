# 🐍 Django 核心概念：10 个关键问题与解答

> 💡 本文档通过“提问-解答”方式，帮助你深入理解 Django 的核心机制。  
> 适用于初学者巩固基础，也适合面试复习。

---

## 1. 请求是如何匹配到视图的？（路由机制）

### ❓ 问题
当你访问 `http://127.0.0.1:8000/api/health/` 时，Django 是如何找到 `HealthCheckView` 的？

### ✅ 答案
Django 使用**分层路由机制**：

1. **主路由** `backend/urls.py` 匹配 `/api/`，通过 `include('api.urls')` 将请求转发给 `api` 应用。
2. **应用路由** `api/urls.py` 匹配 `/health/`，调用 `views.HealthCheckView.as_view()`。
3. 最终执行 `HealthCheckView` 的 `get()` 方法并返回响应。

> 🔁 路由 = URL 到 视图函数 的映射表。

---

## 2. 为什么要拆分 `urls.py`？`include()` 的作用是什么？

### ❓ 问题
`backend/urls.py` 和 `api/urls.py` 有什么区别？为什么不能写在一个文件里？

### ✅ 答案
- **解耦**：主项目不关心应用内部结构。
- **可复用**：`api/` 应用可被多个项目复用。
- **可维护**：路由按功能分组，避免主文件臃肿。

`include()` 的作用是：
> “把以 `/api/` 开头的请求，交给 `api.urls` 模块处理”。

---

## 3. 为