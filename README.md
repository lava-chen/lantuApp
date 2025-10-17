# 澜图智衡小程序（lantuApp）  

![Node.js](https://img.shields.io/badge/Node.js-16.x-green?logo=node.js)
![Taro](https://img.shields.io/badge/Taro-3.x-blue)
![React](https://img.shields.io/badge/React-18.x-blueviolet)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)

基于 **Taro + React + TypeScript** 的微信小程序项目，支持实时内涝风险预测与可视化。

---

## 🚀 项目启动与开发

### 1️⃣ 环境准备
确保以下工具已安装：

- **Node.js**（建议使用 LTS 版本）  
- **包管理器**：Yarn 或 NPM（**注意**：不要混用）  
- **微信开发者工具**（用于项目调试，准备 AppID 或测试号）

---

### 2️⃣ 克隆与依赖安装
```bash
git clone <your-repo-url> lantuApp
cd lantuApp

# 安装依赖（选择一种）
yarn install
# 或
npm install
```
### 3️⃣ 快速启动命令

| 功能 | 命令 |
|------|------|
| 实时构建并监听小程序 | `yarn dev:weapp` / `npm run dev:weapp` |
| 构建生产包 | `yarn build:weapp` / `npm run build:weapp` |
| 清理缓存 | `yarn clean` / `npm run clean` |
| 启动 JSON Server Mock 数据 | `json-server --watch db.json --port 3000` |

- 构建输出目录：`dist/`  
- **保持终端运行**以实现热更新

---

### 4️⃣ 在微信开发者工具中导入项目

1. 打开 **微信开发者工具** → 点击“导入项目”。  
2. 选择项目目录：`dist/`  
3. 填写 **小程序 AppID**（无 AppID 可使用测试号/无 AppID 调试）  
4. 选项建议：
   - 勾选 **使用 npm 模块**（若存在）  
   - 关闭 **将 JS 编译为 ES5**（Taro 已处理）  
   - 忽略上传 `node_modules`（默认即可）  
5. 点击确定 → 预览或真机调试

---

### ⚠️ 常见问题及解决方案

**1. 包管理器混用警告**  
- 请仅使用 **Yarn** 或 **NPM**  
- 删除另一种锁文件（`yarn.lock` 或 `package-lock.json`），重新安装依赖  

**2. Windows 权限或 EPERM 错误**  
- 管理员运行终端  
- 检查占用进程（如 `esbuild.exe`、杀毒软件、索引服务）  
- 必要时删除 `node_modules` 与锁文件并重装依赖  
- 重启电脑以清除占用  

**3. 类型定义误报（如 `sass` / `@ampproject`）**  
- 在 `tsconfig.json` 中保留：
```json
"typeRoots": ["node_modules/@types"]
```
- 按需设置 "types"，如：

```json
"types": ["@tarojs/taro"]
```
## 📁 项目结构（简略）
```bash
src/
 ├─ pages/         # 页面目录
 ├─ components/    # 公共组件
 ├─ store/         # Redux Toolkit 状态管理
 ├─ services/      # 接口请求封装
 ├─ assets/        # 图片/字体资源
 └─ styles/        # 全局样式
 ```
## 🔧 额外建议
- 使用 VSCode + Taro 插件 提升开发效率

- 保持 依赖版本一致，避免在多人协作中出现构建问题

- 可以在 dist/ 目录中开启 SourceMap，便于调试

---
