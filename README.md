# 金城卫浴到货查询

车间员工用手机打开网址，按「分类 → 用途说明」或直接模糊搜索，就能查到装柜清单（LOADING DETAILS）里每件货物所在柜子的预计到港时间（ETA）。

## 文件说明

| 文件 | 作用 |
|---|---|
| `index.html` | 查询页面本身 |
| `data.json` | 备用数据（数据库连不上时才用） |
| `photos/` | 从 Excel 里提取的货物照片和装柜照片 |
| `robots.txt` | 让搜索引擎不收录这个网站 |

## 数据存在哪里

柜子、货物和 ETA 存在 Supabase 数据库（项目 inerayabqrryrsuezlik）的 `app_data` 表里，新导入的照片存在 Supabase Storage 的 `photos` 存储桶里。管理员密码只在数据库里核对，网页代码里没有密码原文。

## 日常更新

1. 打开网站，点右上角「管理」，输入管理员密码。
2. 导入新的装柜清单 Excel；ETA、状态等都是选填，可以以后再补。
3. 点「保存并发布」。保存成功后，大家刷新页面就能看到。

## 修改管理员密码

在 Supabase 的 SQL Editor 里运行（把 新密码 换成你要的密码）：

```sql
update public.app_secret set pw_hash = extensions.crypt('新密码', extensions.gen_salt('bf')) where id = 1;
```
