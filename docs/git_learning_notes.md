> Git 就像一个“代码时光机”，它会记录你每一次修改，让你可以随时回到过去，也能把代码安全地传送到 GitHub（云端）。
> 

---

## **🛠️ Git 三大核心概念（用“写书”来比喻）**

| **Git 概念** | **比喻** | **说明** |
| --- | --- | --- |
| **工作区（Working Directory）** | 你正在写的 Word 文档 | 就是你的 `ai-backend-practice` 文件夹 |
| **暂存区（Staging Area）** | 把修改标记为“准备发布” | 用 `git add` 把文件放进来 |
| **本地仓库（Local Repository）** | 你电脑上的最终书稿 | 用 `git commit` 提交，生成历史记录 |
| **远程仓库（Remote Repository）** | 出版社（GitHub） | 用 `git push` 把书稿发给出版社 |

---

## **🚶‍♂️ Git 标准工作流（四步走）**

你每天写代码，都按这个流程来：

### **1️⃣ 第一步：看一眼改了什么（可选但推荐）**

```
bash深色版本
git status

```

👉 查看哪些文件被修改、新增、删除。

> ✅ 建议：每次操作前先 git status，心里有数。
> 

---

### **2️⃣ 第二步：把修改“暂存”起来**

```
bash深色版本
git add .

```

- `.` 表示“当前目录下所有更改”
- 也可以指定文件：`git add python/py01_lru_cache.py`

🎯 作用：告诉 Git：“这些文件我要提交了”。

---

### **3️⃣ 第三步：提交到本地历史**

```
bash深色版本
git commit -m "feat: 完成 PY-01，实现 LRU 缓存"

```

- `m` 后面是提交信息
- 格式建议：`类型: 描述`，如 `feat`, `fix`, `docs`

✅ 提交后，这次修改就进入了你的“本地时光机”。

---

### **4️⃣ 第四步：推送到 GitHub（云端）**

```
bash深色版本
git pull origin main   # 先拉取远程最新内容（防冲突）
git push origin main   # 再推送

```

> ⚠️ 记住口诀：先拉后推，避免冲突
> 

---

## **🔁 为什么需要 `git pull`？**

想象：

- 你在本地写代码
- 同时，GitHub 上有人（其实是你自己）改了 README
- 如果你直接 `push`，Git 会说：“你落后了，先去同步！”

所以：

```
bash深色版本
git pull origin main

```

👉 相当于：“先下载最新版，再上传我的修改”。

---

## **📚 常用 Git 命令速查表**

| **命令** | **作用** | **示例** |
| --- | --- | --- |
| `git status` | 查看当前修改状态 | `git status` |
| `git add <file>` | 添加文件到暂存区 | `git add .` |
| `git commit -m "..."` | 提交到本地仓库 | `git commit -m "feat: 新功能"` |
| `git pull origin main` | 拉取远程最新代码 | `git pull origin main` |
| `git push origin main` | 推送到 GitHub | `git push origin main` |
| `git log` | 查看提交历史 | `git log --oneline` |
| `git diff` | 查看修改了什么 | `git diff` |

> ✅ 推荐：用 git log --oneline 看简洁的历史。
>