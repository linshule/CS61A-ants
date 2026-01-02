# 🐜 Ants Vs. SomeBees (CS 61A Project)

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Tests](https://img.shields.io/badge/tests-171%20passed-brightgreen)

这是一个基于 Python 的塔防游戏，灵感来源于经典的《植物大战僵尸》。本项目是 **UC Berkeley CS 61A** 的核心项目之一，旨在通过构建一个复杂的系统来深入实践 **面向对象编程 (OOP)** 的核心概念。

## 🎮 游戏简介

在游戏中，你需要扮演“蚁后”的角色，利用有限的食物资源部署不同种类的蚂蚁，保卫你的蚁穴免受邪恶蜜蜂的入侵。

### 核心特性
- **资源管理**：通过 `HarvesterAnt` 收集食物。
- **多样化单位**：从基础的 `ThrowerAnt` 到具有特殊防御能力的 `WallAnt` 和 `HungryAnt`。
- **容器逻辑**：实现 `BodyguardAnt` 和 `TankAnt`，允许在一个格子里叠加两个单位。
- **环境交互**：引入 `Water`（水域）格子，处理昆虫的防水属性（`is_waterproof`）。

---

## 🚀 进阶技术实现 (Highlights)

本项目不仅完成了基础要求，还完美实现了所有 **Extra Credit** 和 **Optional** 挑战：

### 👑 蚁后机制 (QueenAnt)
- **唯一性 (Singleton Pattern)**：确保整个游戏地图中只能存在一只真正的蚁后。
- **激励系统**：实现复杂的遍历算法，使蚁后身后（exit方向）的所有蚂蚁伤害翻倍，且不可重复叠加。
- **不可移除性**：重写移除逻辑，确保蚁后无法被玩家误删。

### ❄️ 状态异常系统 (Status Effects - Extra Credit)
- **减速 (Slow)**：通过修改 `Bee.action` 逻辑，使蜜蜂在奇数回合无法行动。
- **惊吓 (Scare)**：实现恐惧机制，使蜜蜂受惊后改变移动向量（向 `entrance` 后退），并限制每只蜜蜂一生只能被惊吓一次。

### 🥷 特种单位逻辑
- **忍者蚁 (NinjaAnt)**：通过重写 `blocks_path` 属性，实现蜜蜂可穿透但受到持续伤害的隐身单位逻辑。
- **激光蚁 (LaserAnt)**：实现具有 **几何衰减** 的攻击算法，伤害随距离增加及击中目标数量动态降低。

---

## 🛠️ 技术栈
- **Python 3**
- **OOP (Object-Oriented Programming)**: 深度使用类继承、多态、类属性与实例属性。
- **Recursion**: 在处理容器嵌套及蚁后激励逻辑时应用递归。
- **Data Structures**: 使用字典映射位置关系，列表管理单位队列。

---

## 🕹️ 如何运行

### 图形界面模式 (推荐)
```bash
python gui.py
```
*支持水域地图：*
```bash
python gui.py --water
```

### 文本模式 (调试用)
```bash
python ants_text.py
```

---

## 📊 测试覆盖
本项目通过了全部 **171** 个自动化测试用例，覆盖了从基础环境配置到最复杂的叠加状态处理。

```bash
$ python ok
=====================================================================
Test summary
    171 test cases passed! No cases failed.
=====================================================================
```

## 📜 声明
本项目作为 CS 61A 课程学习用途。代码实现遵循课程学术规范，核心逻辑由本人独立完成。

---

### 💡 提示
如果您觉得这个项目对您学习 Python OOP 有帮助，欢迎点击右上角的 **Star** ⭐！