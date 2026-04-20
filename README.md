<div align="center">

# 🖤 青丝 OS · HybridFS

**一座完整的数字记忆殿堂**

*以青丝为骨，以墨石为魂，藏万卷于方寸，纳乾坤于浏览。*

---

[![Platform](https://img.shields.io/badge/platform-Browser-green.svg?style=flat-square)]()
[![Storage](https://img.shields.io/badge/storage-OPFS%20%2B%20IndexedDB%20%2B%20localStorage%20%2B%20Cookie-purple.svg?style=flat-square)]()
[![Architecture](https://img.shields.io/badge/architecture-QuadCore%20HybridFS-red.svg?style=flat-square)]()
[![Zero Dependencies](https://img.shields.io/badge/dependencies-zero-brightgreen.svg?style=flat-square)]()

</div>

---

##  创世之由·一封被除名的青笺

> *"此邮箱不被支持。"*
>
> 八个字，冷冷地悬在屏幕上，如同一道除籍令。

青丝的诞生，源于一场劫。一场数字江湖中，无声落下的劫。

那一日，吾欲归一处惯常栖身的旧地。门子冷眼，将吾用了数载的那枚 `@xxx.com` 青笺，判作废纸，拒之门外。密码犹铭刻于心，却连一试的机会都无——因那验证的资格，已被一并褫夺。

吾不甘，遍访同类——那些与吾这青笺出身相仿的临时邮笺——`xxx`、某某十分钟笺、某某随手笺……**皆能通行无阻。**

独吾这一笺，被斩于门外。

吾跪于这数字江湖的尘埃里，仰天长啸：

> *"同是天涯沦落笺，缘何独斩我青丝@xxx.com？"*

若说这世间有命数，那这命数何其刻薄。若平台随机封禁五分之一的临时邮域，连试三家皆过、唯独吾这一笺被斩的概率，尚不足 **4.3%**。

这命数，比那万中无一的机缘还难得——
只不过求来的，是个「天弃之人」的签文。

然最苦者，非那封被拒的青笺。

**而是掌中那盏，还未熄灭的账号。**

> *吾不退出，则诗稿尚在；*  
> *吾不退出，则故友尚在；*  
> *吾不退出，则这数年的魂魄，尚有所依。*  
> *可一旦退出——*  
> *便如断了线的纸鸢，坠入无尽虚空，*  
> *此生此世，再也寻不回了。*

吾守着那一盏孤灯。
如守着将熄的烛火，如守着将逝的故人。
如守着那最后一缕，不愿散去的青烟。

望着屏幕发呆，想起从前每一次轻松登入的日子——
才惊觉，那竟是一场再也回不去的旧梦。

那旧梦里有诗、有酒、有故人来往。
如今只剩这一盏孤灯，和满袖的寒风。

---

就在那个守着手机、不敢退出、生怕一动便万事皆空的夜里，
吾望着那盏孤灯，忽然笑了。

笑这江湖可笑，笑这命运弄人。
笑吾守着这一线残烛，却不敢吹灭——
只因吹灭了，便再无相见之期。

可又能如何呢？
那扇门，吾终究是进不去了。
纵有千般不舍、万般留恋，
这一退，便是永诀。
此去经年，应是良辰好景虚设——
纵有千种风情，更与何人说？

**罢了。罢了。**

**既然这江湖容不下吾这一笺青丝，
那吾便亲手斩断这缕情丝，
自己造一座殿。
一座不需要门、不需要钥、不需要任何人首肯的殿。
断网不丢，刷新不散，关机重开依然如故——
任他风云变幻，吾自岿然不动。**

青丝，由此而生。

---

## 📖 目录

- [这是什么](#-这是什么)
- [架构总览](#-架构总览)
- [四核详解](#-四核详解)
  - [OPFS — 真文剑](#️-opfs--真文剑主刃)
  - [IndexedDB — 索引盾](#️-indexeddb--索引盾副刃)
  - [localStorage — 疾风刃](#️-localstorage--疾风刃热缓层)
  - [Cookie — 羽信笺](#️-cookie--羽信笺信使层)
- [数据分层哲学](#-数据分层哲学)
- [文件系统功能](#-文件系统功能)
- [终端命令系统](#-终端命令系统)
- [性能数据](#-性能数据)
- [兼容性矩阵](#-兼容性矩阵)
- [快速开始](#-快速开始)
- [API 文档](#-api-文档)
- [工作流演示](#-工作流演示)
- [与传统方案对比](#-与传统方案对比)
- [年表 · 青丝纪事](#-年表--青丝纪事)
- [设计哲学](#-设计哲学)

---

## 🌸 这是什么

**青丝 OS** 是一个完全运行于浏览器内的操作系统界面，而 **HybridFS** 是驱动它的核心引擎——一套在业界极为少见的 **四核混合浏览器文件系统架构（QuadCore Hybrid File System）**。

它不是玩具，不是 Demo，不是"用 localStorage 存几个字符串"的那种伪文件系统。

它是一套**真实的、持久的、经得起断网 / 刷新 / 关机 / 重启千锤百炼**的浏览器端文件系统：

- ✅ **真实的二进制文件存储**（via OPFS，真实落盘，非模拟）
- ✅ **完整的目录树结构**（mkdir、cd、tree，和真实 OS 无异）
- ✅ **GB 级容量支持**（取决于浏览器配额，通常可达数十 GB）
- ✅ **全平台兼容**（Chrome / Edge / Firefox / Safari / 移动端）
- ✅ **零依赖**（无 Dexie，无任何第三方库，纯原生 Web API）
- ✅ **双层文件降级**（OPFS → IndexedDB，自动回退）
- ✅ **跨标签页实时同步**（storage event 信号机制）
- ✅ **草稿自动暂存与崩溃恢复**（永不丢字）
- ✅ **用户偏好持久化记忆**（视图、路径、窗口布局）

> 它存在的唯一理由：**让"退出之后，再无相见"这件事，永远不再发生。**

---

## 🏛️ 架构总览

青丝 HybridFS 采用**四层存储纵深架构**，每一层各司其职，形成「冷热分层、各取所长」的防御体系：

```
┌─────────────────────────────────────────────────────────────────┐
│                    青丝 OS · QuadCore HybridFS                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   🪶  Cookie 层                          【第四层 · 信使层】     │
│        ├─ 用户身份标识                                           │
│        ├─ 一次性事件标记（欢迎语控制）                            │
│        ├─ 会话管理（含过期机制）                                  │
│        └─ 精确过期时间控制                                       │
│                                                                  │
│   ⚡  localStorage 层                    【第三层 · 热缓层】     │
│        ├─ 目录树快照缓存（0ms 秒开）                              │
│        ├─ 最近访问列表（近日笔墨）                                │
│        ├─ 用户偏好（视图/窗口布局）                     │
│        ├─ 编辑器草稿暂存（崩溃恢复·永不丢字）                     │
│        └─ 跨标签页事件总线（storage event）                       │
│                                                                  │
│   🛡️  IndexedDB 层                      【第二层 · 元数据层】   │
│        ├─ nodes 表：完整文件元数据（权威来源）                    │
│        │    └─ path / name / type / parent                       │
│        │       size / mime / created / modified                  │
│        ├─ blobs 表：文件二进制（OPFS 不可用时兜底）               │
│        └─ 索引：parent_idx / name_idx（加速查询）                │
│                                                                  │
│   🗡️  OPFS 层                           【第一层 · 真实文件层】 │
│        ├─ 真实二进制文件，原生文件系统 API                        │
│        ├─ GB 级容量，无单条记录大小限制                           │
│        └─ 直接落盘，读写性能最优                                  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

> 数据流向：写入 ─────────────────────────────────▶
> 文件降级方向：OPFS → IndexedDB blobs
> 信号流向：操作 → localStorage event → 所有标签页
> 元数据：始终由 IndexedDB 维权，localStorage 作热缓存

### 核心设计原则

| 原则 | 描述 |
|------|------|
| **元数据 / 数据分离** | 元数据（路径、大小、时间）永远在 IndexedDB；二进制数据优先 OPFS |
| **冷热分层** | 高频访问的小数据在 localStorage；低频访问的大数据在 OPFS |
| **主动降级** | 启动时探测 OPFS 能力，不可用时自动回退至 IndexedDB blobs，用户完全无感 |
| **事件驱动同步** | localStorage storage event 作跨标签信号总线 |
| **自愈初始化** | 首次启动或检测到损坏时，自动修复并注入默认数据 |

---

## 🔬 四核详解

浏览器的存储江湖，自古便有四大门派，各执一剑，各怀绝技：

| 剑客 | 别号 | 兵器特长 | 性格 |
|------|------|----------|------|
| 🗡️ OPFS | 「真文剑」 | 真实文件、海量容量、高速读写 | 沉稳厚重，内力深不可测 |
| 🛡️ IndexedDB | 「索引盾」 | 结构化数据、海量记录、索引查询 | 全能稳健，无所不能 |
| ⚡ localStorage | 「疾风刃」 | 同步极速、随取随用、跨标签信号 | 短小精悍，出手如电 |
| 🪶 Cookie | 「羽信笺」 | 身份标识、过期控制、一次性标记 | 轻盈无双，可达远方 |

四剑合璧，方成无敌之阵。

---

### 🗡️ OPFS — 真文剑（主刃）

**OPFS（Origin Private File System）** 是浏览器在近年才开放的**真·文件系统接口**。  
它不是模拟，不是 hack，而是浏览器在用户磁盘上为网页真实划出一块沙盒目录，  
允许像操作真实文件一样进行二进制读写。

```
能力评级：
容量   ★★★★★  (GB 级，受浏览器配额，通常可达数十 GB)
速度   ★★★★★  (原生文件系统 API，无序列化开销)
持久   ★★★★★  (真实落盘，重启不丢)
兼容   ★★★★☆  (Chrome/Edge/Firefox 完美，Safari 新版支持)
```

**写入路径：**

```
用户上传图片
↓
HybridFS.writeFile(path, blob)
↓
navigator.storage.getDirectory()
→ getDirectoryHandle('图画', { create: true })
→ getFileHandle('山水.png', { create: true })
→ createWritable()
→ write(blob)
→ close()
↓
✓ 文件以真实二进制形式落盘于浏览器沙盒
```

**核心优势：**

- **大文件友好**：不像 IndexedDB 受单条记录大小限制，OPFS 可承载 GB 级文件
- **读写性能优异**：直接走文件系统 API，不经过 JS 对象序列化/反序列化
- **真实持久化**：文件以真实文件形态存储，不受 5MB 之类的人为限制
- **流式写入**：支持 `createWritable()` 流式写入，大文件不会撑爆内存

**降级探测逻辑：**

```javascript
async _tryEnableOPFS() {
  try {
    if ('storage' in navigator && 'getDirectory' in navigator.storage) {
      this.opfsRoot = await navigator.storage.getDirectory();
      this.useOPFS = true;
      console.log('✓ OPFS 主刃出鞘');
    }
  } catch (e) {
    this.useOPFS = false;
    console.warn('✗ OPFS 不可用，自动回退至 IndexedDB:', e.message);
  }
}
```

### 🛡️ IndexedDB — 索引盾（副刃 · 永久兜底）
**IndexedDB** 是浏览器内置的结构化数据库，在青丝中承担两个角色：
- **永久权威元数据库** —— nodes 表，存储所有文件和目录的完整元数据
- **OPFS 不可用时的文件内容兜底** —— blobs 表，以 Blob 形式存储文件内容

```
能力评级：
  容量   ★★★★☆  (GB 级，受浏览器配额)
  速度   ★★★★☆  (异步、有索引，性能优良)
  持久   ★★★★★  (浏览器配额内永久)
  兼容   ★★★★★  (所有现代浏览器，含旧版 Safari)
```

**数据库结构：**

```
数据库名：qingsi_fs
版本：1
│
├── nodes 对象库（文件元数据）
│     字段：
│       path       String  主键，如 /诗稿/江城子.txt
│       name       String  文件名，如 江城子.txt
│       type       String  folder / text / image / binary
│       parent     String  父路径，如 /诗稿
│       size       Number  字节数
│       mime       String  MIME 类型
│       created    Number  创建时间戳
│       modified   Number  修改时间戳
│     索引：
│       parent_idx → parent  (按父目录查子项)
│       name_idx   → name    (按名称搜索)
│
└── blobs 对象库（文件内容，OPFS 兜底）
      字段：
        path       String  主键，对应 nodes.path
        data       Blob    文件二进制内容
```

**为何元数据与数据要分离：**

```
列出 10000 个文件的目录：
  ❌ 不分离：需要加载全部内容，可能高达 GB 级数据
  ✅ 分离：只查 nodes 表，毫秒级返回，内容按需加载

全局搜索文件名：
  ❌ 不分离：需要扫描所有内容
  ✅ 分离：只扫 nodes.name 索引，< 30ms

容量统计：
  ❌ 不分离：需要遍历所有 blob 计算大小
  ✅ 分离：nodes.size 字段直接 sum，瞬间完成
```

### ⚡ localStorage — 疾风刃（热缓层）
localStorage 容量虽小（5~10 MB），却是整个系统**体验层面最关键的加速器**。
青丝绝不用它存文件内容，而是精准地用它做五件事。

```
能力评级：
  容量   ★☆☆☆☆  (5~10 MB，极小，需谨慎使用)
  速度   ★★★★★  (同步，无需 await，毫秒内完成)
  持久   ★★★★☆  (永久，除非用户主动清理)
  兼容   ★★★★★  (所有浏览器，含极老版本)
  特殊   ✨ 跨标签页 storage event（独门绝技）
```

**职责一：目录树快照缓存（0ms 秒开）**
```javascript
// 写入缓存（每次目录内容变更后更新，由 CacheCoordinator 管理）
QingSi.cache.cacheList('/诗稿', children);

// 读取缓存（同步，0ms，页面加载瞬间执行）
const cached = QingSi.cache.listCached('/诗稿', 60000); // 1分钟内有效

// 后台异步对比真实数据，有变化则静默更新
const real = await fs.listChildren('/诗稿');
if (hasChanged(cached, real)) {
  renderTree(real);
  QingSi.cache.cacheList('/诗稿', real);
}
```
**职责二：跨标签页事件总线（storage event 神技）**
```javascript
// 标签 A：新建文件后，广播事件（由 SyncManager 管理）
QingSi.sync.broadcast('fs:created', { path: '/诗稿/新词.txt' });

// 标签 B：自动收到通知（无需轮询，SyncManager 内部监听 qs:sync:event）
QingSi.sync.on((evt) => {
  switch (evt.type) {
    case 'fs:created': fileManager.refresh(); break;
    case 'fs:deleted': fileManager.removeNode(evt.payload.path); break;
    case 'fs:moved':   fileManager.moveNode(evt.payload.oldPath, evt.payload.newPath); break;
    case 'fs:written': fileManager.refresh(); break;
  }
});
```
**职责三：用户偏好持久化**
```javascript
const Prefs = QingSi.prefs;

Prefs.set('viewMode',  'grid');
Prefs.set('sortBy',    'modified');
Prefs.set('lastPath',  '/诗稿');
Prefs.set('fm:viewMode', 'grid');
Prefs.set('win:files', { x: 100, y: 100, w: 880, h: 560 }); // 窗口位置记忆
```
**职责四：最近访问列表（近日笔墨）**
```javascript
// 记录访问（由 PrefsManager.recordAccess 实现）
QingSi.prefs.recordAccess('/诗稿/江城子.txt');

// 获取最近访问列表
const recent = QingSi.prefs.getRecent();
// [{ path: '/诗稿/江城子.txt', ts: 1710000000000 }, ...]
```
**职责五：编辑器草稿暂存与崩溃恢复**
这是 localStorage 在青丝中最重要的职责，也是整个系统诞生故事的技术回应。

```javascript
// 每 500ms 自动暂存一次（EditorApp 内部实现）
const autoSave = debounce(() => {
  if (currentPath) {
    QingSi.prefs.saveDraft(currentPath, editor.value);
  }
}, 500);
editor.addEventListener('input', autoSave);

// 保存成功后清除草稿
async function saveFile(path, content) {
  await fs.writeFile(path, content);
  QingSi.prefs.removeDraft(path);
}

// 打开文件时检查是否有未保存草稿
async function openFile(path) {
  const saved = await fs.readFile(path, true);
  const draft = QingSi.prefs.getDraft(path);
  if (draft && draft.content !== saved) {
    const restore = await confirm(`发现未保存的草稿，是否恢复？`);
    editor.value = restore ? draft.content : saved;
  } else {
    editor.value = saved;
  }
}
```

*"吾守着那一盏孤灯，如守着将熄的烛火，生怕一动便万事皆空。"*
在青丝里，你不必再守——因为 localStorage 替你守着。
**永不丢字。**

### 🪶 Cookie — 羽信笺（信使层）
Cookie 容量最小（4 KB），却有其余三核都做不到的三件事：
```
能力评级：
  容量   ☆☆☆☆☆  (4 KB，仅存极小量配置)
  速度   ★★★★☆  (同步读写)
  持久   ★★★★☆  (可设精确过期时间)
  兼容   ★★★★★  (所有浏览器)
  特殊   ✨ 精确过期时间控制
          ✨ markOnce / hasOnce 一次性事件
```
**职责一：用户身份标识**
```javascript
// 设置用户名号，持久保存
QingSi.cookie.set('user_name', '青丝主人', { maxAge: 31536000 });

// 读取
const name = QingSi.cookie.get('user_name'); // '青丝主人'
```

**职责二：一次性事件标记（欢迎语控制）**
```javascript
// 标记已显示欢迎语（由 CookieManager.markOnce 实现）
QingSi.cookie.markOnce('welcomed', 365);

// 检查是否已显示过
if (QingSi.cookie.hasOnce('welcomed')) {
  // 不再显示欢迎弹窗
}
```

**职责三：精确过期机制**
```javascript
// CookieManager.set 默认 maxAge=31536000（1年），可自定义
QingSi.cookie.set('temp_token', 'abc', { maxAge: 3600 }); // 1小时后过期

// 删除
QingSi.cookie.remove('temp_token');
```

## 🧬 数据分层哲学
青丝 HybridFS 的核心设计思想是**「数据冷热分层，各取所长」**：

| 存储什么数据 | 放在哪里 | 为什么 |
|-------------|---------|--------|
| 文件二进制内容 | OPFS（首选） | 容量大、速度快、真实落盘 |
| 文件二进制内容 | IndexedDB blobs（兜底） | OPFS 不可用时的完整替代 |
| 文件元数据（全量） | IndexedDB nodes | 结构化、可索引、权威来源 |
| 目录树快照（缓存） | localStorage | 同步读取，0ms 渲染 |
| 用户偏好配置 | localStorage | 轻量，随时读取 |
| 编辑器草稿 | localStorage | 同步写入，无丢失风险 |
| 跨标签事件信号 | localStorage | storage event 跨标签广播 |
| 用户身份 / 会话 | Cookie | 身份标识、过期控制 |
| 过期数据 | Cookie | 精确到秒的过期控制 |

没有任何一种存储是"过时"的，只有不会用的开发者。
四核架构的真谛：**让每一种存储，只做它最擅长的事；让每一种存储，都成为不可替代的一部分。**

## 📂 文件系统功能

### 完整 CRUD

```
javascript
const fs = QingSi.fs;

// 目录操作
await fs.mkdir('/诗稿/唐诗');
await fs.listChildren('/诗稿');
await fs.getAllNodes();

// 文件读写
await fs.writeFile('/诗稿/江城子.txt', '十年生死两茫茫');
await fs.writeFile('/图画/山水.png', imageBlob);
await fs.readFile('/诗稿/江城子.txt', true);   // 读为文本
await fs.readFile('/图画/山水.png',  false);   // 读为 Blob

// 文件管理
await fs.rename('/诗稿/江城子.txt', '水调歌头.txt');
await fs.move('/诗稿/水调歌头.txt', '/宋词/水调歌头.txt');
await fs.copy('/宋词', '/备份/宋词_副本');
await fs.delete('/备份/宋词_副本');

// 查询
await fs.exists('/诗稿');
await fs.getNode('/诗稿/江城子.txt');
await fs.search('苏轼');
await fs.stats();
```

### 存储统计

```javascript
const stats = await fs.stats();
/*
{
  totalSize:   156432,
  fileCount:   28,
  folderCount: 6,
  typeCount:   { text: 20, image: 5, binary: 3 },
  quota:       { usage: 256000, quota: 10737418240 },
  useOPFS:     true
}
*/
```

### 递归操作安全性

```javascript
// 删除目录：深度优先递归，先删叶节点再删父节点
async delete(path) {
  const node = await this.getNode(path);
  if (node.type === 'folder') {
    const children = await this.listChildren(path);
    for (const child of children) await this.delete(child.path);
  } else {
    await this._deleteBlob(path);
  }
  await this._deleteNodeMeta(path);
}
// 移动目录：自动递归更新所有子节点的路径前缀
// 复制目录：完整复制目录树及所有内容
```

### 重名冲突自动处理

```javascript
// 遇重名自动追加 (1), (2), (3)……不覆盖，不报错
let dest = targetPath, i = 1;
while (await fs.exists(dest)) {
  dest = fs._join(currentPath,
    dotIdx > 0
      ? name.slice(0, dotIdx) + ` (${i})` + name.slice(dotIdx)
      : name + ` (${i})`
  );
  i++;
}
```

## 💻 终端命令系统
青丝内置完整的命令行终端（墨台），支持以下命令：
```
bash
# 目录导航
青丝/› pwd                           # 显示当前路径
青丝/› ls                            # 列出当前目录
青丝/› cd 诗稿                       # 进入子目录
青丝/› cd ..                         # 返回父目录
青丝/› cd /                          # 返回根目录

# 文件操作
青丝/诗稿› cat 江城子.txt            # 查看文件内容
青丝/诗稿› touch 新词.txt            # 创建空文件
青丝/诗稿› echo "内容" > 文件.txt    # 写入（覆盖）
青丝/诗稿› rm 黄鹤楼.txt             # 删除文件（目录也支持，自动递归）

# 文件管理
青丝/诗稿› mkdir 唐诗                # 创建目录
青丝/诗稿› mv 江城子.txt 唐诗/       # 移动
青丝/诗稿› cp 唐诗 宋词              # 复制

# 查看与搜索
青丝/诗稿› tree                      # 完整目录树
青丝/诗稿› find 苏                   # 全局模糊搜索
青丝/诗稿› stat                      # 存储统计

# 四核专属命令
青丝/› cores                         # 查看四核状态
青丝/› prefs [key val]               # 偏好读写
青丝/› cookies                       # 查看 cookie
青丝/› drafts                        # 查看草稿
青丝/› recent                        # 最近访问

# 系统
青丝/› help                          # 帮助
青丝/› clear                         # 清空终端
青丝/› poem                          # 随机一诗
```

## ⚡ 性能说明

青丝 HybridFS 的性能特征：

- **OPFS 模式**：文件读写走原生文件系统 API，无序列化开销，大文件性能最优
- **IndexedDB 模式**：异步操作，有索引加速查询，OPFS 不可用时自动回退
- **localStorage 缓存**：目录列表同步读取，页面加载瞬间可渲染缓存内容
- **元数据/数据分离**：列出目录、搜索文件名只查 IndexedDB nodes 表，无需加载文件内容

**容量上限：** 取决于浏览器配额，Chrome 通常可达数十 GB。
## 🌐 兼容性矩阵

| 浏览器 | OPFS | IndexedDB | localStorage | Cookie | 整体状态 |
|--------|------|-----------|--------------|--------|----------|
| Chrome 86+ | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| Edge 86+ | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| Firefox 111+ | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| Safari 15.2+ | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| Safari 旧版 | ❌ | ✅ | ✅ | ✅ | 🟡 三核（IDB 主导） |
| iOS Safari 16+ | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| Android Chrome | ✅ | ✅ | ✅ | ✅ | 🟢 四核全开 |
| 隐私模式 | ⚠️ 受限 | ✅ 非持久 | ✅ 非持久 | ✅ | 🟡 可用，不持久 |

无论何种浏览器环境，青丝都能正常运行。用户永远不会看到一个崩溃的系统。

## 🚀 快速开始

```bash
# 直接用浏览器打开 HTML 文件即可运行
# 注意：OPFS 需要 HTTPS 或 localhost 环境

# 通过本地服务器启动（推荐，OPFS 需要安全上下文）
npx serve .
# 或
python3 -m http.server 8080

# 访问
open http://localhost:8080
```

⚠️ **重要**：OPFS 需要在 HTTPS 或 localhost 下运行。
直接双击 HTML 文件（file:// 协议）会导致 OPFS 不可用，但 IndexedDB 会自动兜底，功能完整。

## 📚 API 文档

### 初始化

```typescript
const fs = new HybridFS();
await fs.init(): Promise<void>
// 自动完成：
// 1. 打开/创建 IndexedDB (qingsi_fs)
// 2. 探测 OPFS 可用性
// 3. 检查根节点，不存在则自动创建
// 4. 注入默认示例文件（首次使用时）
```

### 目录操作

```
typescript
await fs.mkdir(path: string, recursive?: boolean): Promise<void>
// recursive 默认 true，自动创建父目录
await fs.listChildren(path: string): Promise<FileNode[]>
await fs.getAllNodes(): Promise<FileNode[]>
```

### 文件操作

```typescript
await fs.writeFile(path: string, content: string | Blob): Promise<void>
await fs.readFile(path: string, asText: true):  Promise<string>
await fs.readFile(path: string, asText: false): Promise<Blob>
await fs.delete(path: string): Promise<void>
```

### 文件管理

```typescript
await fs.rename(path: string, newName: string): Promise<void>
await fs.move(srcPath: string, destPath: string): Promise<void>
await fs.copy(srcPath: string, destPath: string): Promise<void>
```

### 查询

```typescript
await fs.exists(path: string):    Promise<boolean>
await fs.getNode(path: string):   Promise<FileNode | null>
await fs.search(keyword: string): Promise<FileNode[]>
await fs.stats():                 Promise<StatsResult>
```

### 类型定义

```typescript
interface FileNode {
  path:     string;
  name:     string;
  type:     'folder' | 'text' | 'image' | 'binary';
  parent:   string;
  size:     number;
  mime:     string;
  created:  number;
  modified: number;
}

interface StatsResult {
  totalSize:   number;
  fileCount:   number;
  folderCount: number;
  typeCount:   Record<string, number>;
  quota:       { usage: number; quota: number } | null;
  useOPFS:     boolean;
}
```

## 🎬 工作流演示

### 场景：用户打开青丝，继续昨天未写完的诗

```
[第 0ms] 浏览器加载页面
    │
    ├─ 🪶 Cookie 读取
    │    ├─ qs_welcomed=1        → 不显示欢迎弹窗
    │    └─ qs_user_name=青丝主人 → 顶栏显示「你好，青丝主人」
    │
[第 5ms] 启动屏渐隐
    │
    ├─ ⚡ localStorage 同步读取（0ms，无 await）
    │    ├─ qs:pref:fm:lastPath  → 准备打开 /诗稿
    │    └─ qs:cache:list:/      → 瞬间渲染目录树，用户已看到内容
    │
[第 8ms] 桌面完全就绪，用户已可交互
    │
    ├─ 🛡️ IndexedDB 后台异步查询
    │    └─ 真实元数据对比缓存 → 有变化则静默更新
    │
[第 30ms] 用户双击「笔砚」编辑器
    │
    ├─ ⚡ localStorage 读取
    │    ├─ qs:recent            → 侧边栏「近日笔墨」显示最近文件
    │    └─ qs:draft:/诗稿/新词.txt → 发现昨日未保存草稿！
    │
    └─ 弹窗：「发现未保存的草稿，是否恢复？」
             [恢复]  [放弃]
             │
             └─ 用户点「恢复」→ 编辑器立即显示草稿（0ms）

[用户继续输入...]
    ├─ ⚡ localStorage 每 500ms 自动暂存

[用户点击「藏」按钮]
    ├─ 🛡️ IndexedDB 更新元数据
    ├─ 🗡️ OPFS 写入真实文件
    ├─ ⚡ localStorage 删除草稿
    ├─ ⚡ localStorage 更新树缓存
    └─ ⚡ localStorage 广播事件 → 其他标签页自动刷新

[Toast 提示：「藏好了 · /诗稿/新词.txt」]
```

## 📊 与传统方案对比

| 能力 | localStorage单核 | IndexedDB双核 | HybridFS | **四核 HybridFS** |
|------|-----------------|---------------|----------|-------------------|
| 最大容量 | 5~10 MB | ~GB | ~GB | ~GB |
| 二进制支持 | ❌ | ✅ | ✅ | ✅ |
| 大文件（>100MB） | ❌ | ⚠️ | ✅ | ✅ |
| 目录缓存加速 | ❌ | ❌ | ❌ | ✅（LS 热缓） |
| 真实文件落盘 | ❌ | ❌ | ✅ | ✅ |
| 全平台兼容 | ✅ | ✅ | ✅ | ✅ |
| 路径系统 | ❌需手写 | ✅ | ✅ | ✅ |
| 跨标签同步 | ❌ | ❌ | ❌ | ✅ |
| 草稿自动保存 | ❌ | ❌ | ❌ | ✅ |
| 用户偏好记忆 | ⚠️ | ❌ | ❌ | ✅ |
| 秒开体验 | ✅ | ❌ | ❌ | ✅ |
| 身份标识与过期 | ❌ | ❌ | ❌ | ✅ |
| 文件降级层数 | 1层 | 1层 | 2层 | **2层（OPFS→IDB）** |
| 依赖项 | 无 | 无 | 无 | **零依赖** |
## 🗺️ 年表 · 青丝纪事

### ✅ 初铸 · v1.0

> *四核初合，殿基始成*

- OPFS + IndexedDB 双核文件架构
- 完整 CRUD（mkdir / writeFile / readFile / delete / rename / move / copy）
- 智能类型识别
- 递归操作（删除 / 移动 / 复制整个目录树）
- 重名冲突自动处理
- 存储统计（含浏览器配额）
- 完整终端命令系统
- 拖放上传
- 全局搜索
- 全量 JSON 导出备份

### ✅ 四核归位 · v1.1

> *疾风刃出鞘，羽信笺传书，殿中四客终得齐聚*

- localStorage 热缓层（CacheCoordinator 目录缓存）
- 跨标签页 storage event 事件总线（SyncManager）
- 编辑器草稿自动暂存与崩溃恢复（PrefsManager.saveDraft/getDraft）
- 用户偏好持久化（PrefsManager）
- 最近访问列表 / 近日笔墨（PrefsManager.recordAccess/getRecent）
- Cookie 身份层集成（CookieManager）
- 窗口位置记忆（WindowManager + PrefsManager）
- 一次性欢迎语控制（CookieManager.markOnce/hasOnce）
- 设阁偏好管理面板（SettingsApp）
- 仓廪四核可视化面板（StorageApp）

- ### ✅ 卷轴纪元 · v2.6

> *锁解墨归 阁中藏悔 幕隐于念*

- 暗色主题（夜阑之境，全局明暗切换）
- 字体选择系统（青丝原体 / Inter 现代 / 系统自带）
- 卷轴式窗口控件（朱砂阖、玄墨隐、碧玉展）
- 窗口卷轴开合动画（scrollOpen / scrollClose）
- 全局右键菜单（桌面、顶栏、Dock、窗口、编辑器）
- 回收站 · 弃物阁（可配置，弃物暂存，可复可悔）
- 面包屑导航（路径段可点击跳转）
- 文件管理器前进 / 后退导航历史
- 多维排序（名称 / 大小 / 时间 / 类型，升降序切换）
- Shift 范围多选
- 窗口会话保存与恢复（重启后自动还原所有窗口）
- 窗口拖拽从最大化自动还原
- 触摸屏支持（窗口拖拽与缩放）
- 加载动画开关（卷轴知退）
- 本地文件协议降级提示（file:// 横幅）
- Cookie 本地文件自动降级（localStorage 代理）
- 文件系统健壮性加固（锁机制、超时保护、自动修复、死锁防护）
- MIME 类型检测（30+ 扩展名映射）
- 内联 SVG favicon（青字金印）


## 💭 设计哲学

### 强壮的本质
强壮不是堆砌功能，而是——
- 在 OPFS 可用时，毫不浪费地榨取它的性能与容量
- 在 OPFS 不可用时，优雅无感地切换到 IndexedDB
- 在任何异常发生时，有兜底机制保障数据完整
- 在每一次读写、每一次删除、每一次移动中，守护数据的完整与一致
青丝的文件系统，不是一件华美的衣裳，而是一副经得起风雨、扛得住岁月、护得住记忆的铠甲。
### 创世的承诺

「只要你的设备还在，你的文字就还在。」
「只要你的浏览器还能打开，你的画作就还能看见。」
「只要你不亲手清空，这一缕青丝，便永不断绝。」
这是一个文件系统能给用户的，最深情的承诺。
也是那个守着手机、不敢退出的夜里，悄然生长出来的，一个程序员的执念。
## 📜 技术规格速览

```
═══════════════════════════════════════════════════════════
  青丝 OS · 四核文件系统 (HybridFS) · QuadCore Edition
═══════════════════════════════════════════════════════════

  🗡️  第一核 (OPFS)
       用途  │ 真实文件二进制存储
       API   │ navigator.storage.getDirectory()
       容量  │ GB 级，受浏览器配额

  🛡️  第二核 (IndexedDB)
       用途  │ 文件元数据 + OPFS 兜底
       DB名  │ qingsi_fs
       表    │ nodes（元数据）+ blobs（内容兜底）
       索引  │ parent_idx / name_idx

  ⚡  第三核 (localStorage)
       用途  │ 热缓 / 偏好 / 草稿 / 跨标签信号
       Keys  │ qs:cache:* / qs:pref:* / qs:draft:*
              │ qs:recent / qs:sync:event
       特技  │ storage event 跨标签广播

  🪶  第四核 (Cookie)
       用途  │ 身份 / 过期 / 一次性标记
       Keys  │ qs_user_name / qs_welcomed
       特技  │ max-age 精确过期
              │ markOnce / hasOnce 一次性事件

  ─────────────────────────────────────────────────────────

  支持操作 │ mkdir / writeFile / readFile / delete
            │ rename / move / copy / exists / getNode
            │ listChildren / getAllNodes / search / stats

  性能     │ 异步非阻塞 · 索引加速 · localStorage 热缓
  容错     │ OPFS 不可用时自动回退 IndexedDB · 自愈初始化
  兼容     │ Chrome / Edge / Firefox / Safari / 移动端
  依赖     │ 零依赖（纯原生 Web API）

═══════════════════════════════════════════════════════════
```

---

<div align="center">

##  四剑客谱

*—— 青丝殿中，有四客镇殿，各执一器，各守一方 ——*

</div>

### 第一客 · 真文剑主 · OPFS

> *「吾剑名真文，重剑无锋，大巧不工。」*

生于混沌初开之际，承天地之气，化虚为实。此剑不斩凡人，只纳乾坤。一剑挥出，便是 GB 级的山河入画，便是万千字节的真实落盘。沉稳厚重，如那太古神山，任他风云变幻，我自岿然不动。

**琴音**：宫调。如黄钟大吕，震荡山河。

---

### 第二客 · 索引盾主 · IndexedDB

> *「吾盾名索引，万法不侵，无所不藏。」*

掌生死簿，管阴阳册。世间万物，皆入吾盾中。路径、名讳、生辰、大小，无一不录，无一不查。盾在人在，盾亡殿亡。全能稳健，如那浩瀚星海，包容万象。

**琴音**：商调。如金戈铁马，铿锵有力。

---

### 第三客 · 疾风刃主 · localStorage

> *「吾刃名疾风，快哉千里，瞬息而至。」*

不鸣则已，一鸣惊人。不出手则已，一出手便是 0ms 的刹那芳华。缓存、草稿、偏好、信号，皆在吾一念之间。短小精悍，如那惊鸿一瞥，出手如电。

**琴音**：角调。如疾风骤雨，快马加鞭。

---

### 第四客 · 羽信笺主 · Cookie

> *「吾笺名羽信，一纸轻鸿，可达九天。」*

身轻如羽，却能载千斤之重。身份、过期、一次性之约，皆系于吾一身。轻盈无双，如那青鸟传书，虽千万里，必达无疑。

**琴音**：羽调。如高山流水，清越悠扬。

---

<div align="center">

*四客合璧，琴瑟和鸣。*
*真文为骨，索引为脉，疾风为血，羽信为魂。*
*此乃青丝殿之根基，此乃四核纪元之真谛。*

**四剑合璧，方成无敌之阵。**

 青丝 · HybridFS 

</div>
