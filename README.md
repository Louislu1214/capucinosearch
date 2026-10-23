# 金城卫浴到货查询

车间员工用手机打开网址，按「分类 → 用途说明」或直接模糊搜索，就能查到装柜清单（LOADING DETAILS）里每件货物所在柜子的预计到港时间（ETA）。

## 文件说明

| 文件 | 作用 |
|---|---|
| `index.html` | 查询页面本身 |
| `data.json` | 所有柜子和货物数据（ETA 也在这里） |
| `photos/` | 从 Excel 里提取的货物照片和装柜照片 |
| `robots.txt` | 让搜索引擎不收录这个网站 |

## 日常更新（不用改代码）

1. 打开网站，点右上角「管理」，输入管理员密码。
2. 第一次使用时，在「GitHub 保存设置」里填：
   - 仓库：`用户名/仓库名`，例如 `Louislu1214/capucinosearch`
   - GitHub 令牌：按下方步骤生成，勾选「在这台设备上记住」
3. 导入新的装柜清单 Excel，或修改柜子的 ETA、状态。
4. 点「保存并发布」。大约 1–2 分钟后，大家刷新页面就能看到更新。

## 生成 GitHub 令牌（只做一次）

1. 打开 GitHub → 右上角头像 → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token。
2. Repository access 选 **Only select repositories**，只勾这个仓库。
3. Permissions → Repository permissions → **Contents** 选 **Read and write**，其他保持默认。
4. 有效期按需设置（例如 1 年），生成后复制 `github_pat_…` 开头的令牌，填进网站的管理界面。

令牌只保存在你自己的设备上，不会写进网站文件。令牌丢失或泄露时，在同一页面删除旧令牌，再生成一个新的即可。
