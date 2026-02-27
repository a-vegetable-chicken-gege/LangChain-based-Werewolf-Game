# LangChain-based-Werewolf-Game
# 🐺 AI狼人杀

> *"人工智能的欺骗艺术"*
---
## 📅 开发日志 | 2026年2月27日

**💡 灵感迸发**

> 过年刷抖音，偶然瞥见AI狼人杀视频。  
> 瞬间梦回高中——那些为谁是狼人争得面红耳赤的深夜。  
> 恰巧去年刚入门LangChain，先写个雏形占个坑位，成不成另说。  

---

## 🎮 快速开始

完整原型请戳 [`langchain_wolfkill.ipynb`](langchain_wolfkill.ipynb)

### 环境配置

| 步骤 | 操作 | 备注 |
|:---|:---|:---|
| 1 | **环境搭建** | 参考 [LangChain官方文档](https://python.langchain.com/) |
| 2 | **配置密钥** | 创建`.env`文件，填入模型API |
| 3 | **选择模型** | 默认DeepSeek API（便宜💰） |
| 🔄 | **混搭玩法** | 多模型API接入|

---

## 🤖 与Kimi结对编程：爱恨交织

*本项目由人类直觉与AI热情联合出品。*

**优点：** AI写码乃人类最伟大发明。  
**现实：** Kimi偶尔... *脑子短路*。

### 🚨 Kimi的"昏头"实录

#### ❌ 通灵女巫Bug

```python
# Kimi的离谱代码：
prompt_parts = [f"你是女巫。今晚{werewolf_target if werewolf_target else '没有人'}被杀。"]

if potions["save"]:
   prompt_parts.append(f"你还有解药（可以救活{werewolf_target}）。")
else:
   prompt_parts.append("你的解药已用完。")
```
没解药还直接报身份？这可不行奥，本质上其实是对规则的不熟悉，看来要先找找bug再说了。

#### ❌ 传递死亡信息Bug
```python
            if len(expelled) == 1 and max_votes > len(votes) / 2:
                expelled_player = expelled[0]
                print(f"\n☠️ {expelled_player} 被投票放逐！身份是：{self.get_player_role(expelled_player)}")
```
这不开玩笑呢吗？

## 🎭 玩家Agent 表现评估
| 维度 | 评分 | 吐槽 |
| --- | --- | --- |
| 逻辑推理 | ⭐⭐☆☆☆ | 新手水平，逻辑一点 |
| 规则理解 | ⭐⭐⭐☆☆ | 懂点皮毛，细节没有 |
| 废话程度 | ⭐⭐⭐⭐⭐ | 500字起步讲心路历程 |
| 欺骗能力 | ⭐⭐☆☆☆ | 不会骗人，更不会抓骗 |

### 📝 未来工作
- Prompt工程亟待升级，是不是狼人杀的规则还没有理解清楚啊
- 战略思维深度调教缺失，正常来说调用API使用模型就足够本项目了，但是要是想做一个狼人杀高手Agent就得后训练了（暂不考虑）
- 架构改变：
  当前架构：工作流上帝：夜晚 → 狼人杀人 → 预言家验人 → 女巫操作 → 白天 → 投票
  僵硬、predictable、毫无体验，那是不是可以创建一个Agent来当上帝，省去正则提取关键信息了。

