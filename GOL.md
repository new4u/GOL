# Web3 Game of Life NFT

## 简介

本项目是一个基于Web3的康威生命游戏（Conway's Game of Life）实现。用户可以在网页上进行生命游戏，并将当前的游戏棋盘状态铸造为一个NFT（非同质化代币）。这些NFT存储在 Monad 测试网上，用户也可以加载已有的NFT来恢复游戏状态，或查看所有已铸造的NFT列表。

## 主要功能

*   **交互式生命游戏棋盘**：创建、编辑和模拟生命游戏图案。
*   **钱包连接**：通过浏览器钱包（如MetaMask）连接到Monad测试网。
*   **铸造NFT**：将当前的游戏棋盘状态铸造为一个新的NFT。
*   **加载NFT**：通过输入Token ID，从区块链加载并显示对应的游戏状态。
*   **列出所有NFT**：显示一个包含所有已铸造NFT信息的表格（Token ID, 所有者, 游戏代数, 时间戳, 棋盘状态）。

## 技术栈

*   **前端**：HTML, CSS, JavaScript
*   **Web3库**：ethers.js (v6)
*   **智能合约**：Solidity
*   **区块链网络**：Monad 测试网 (Chain ID: 10143)

## 项目结构

```
GOL/
├── README.md              # 本项目说明文档
├── frontend/
│   └── index.html         # 游戏主界面、Web3交互逻辑
├── contracts/
│   └── GameOfLifeDemo.sol # (或类似名称) 智能合约，处理NFT铸造和游戏状态存储
├── demo.md                # 包含合约部署地址等演示信息
└── .env                   # 环境变量文件 (例如部署合约时使用的私钥)
```

## 运行指南

1.  **克隆仓库** (如果尚未克隆):
    ```bash
    git clone <repository-url>
    cd GOL
    ```
2.  **打开前端页面**:
    直接在现代浏览器中打开 `frontend/index.html` 文件。
3.  **配置钱包**:
    *   确保你的浏览器安装了MetaMask或兼容的Web3钱包。
    *   将钱包网络切换到 **Monad Testnet**。
        *   Network Name: Monad Testnet
        *   New RPC URL: `https://testnet-rpc.monad.xyz/` (请根据 `demo.md` 或最新信息确认RPC URL)
        *   Chain ID: `10143`
        *   Currency Symbol: MON
    *   确保钱包中有足够的 MON 测试币用于支付交易的gas费用。

## 智能合约信息

*   **合约地址 (Monad Testnet)**: `0x680c88f57717010661710C5849a47A13694F83A0` (具体地址请参考 `demo.md` 文件)
*   **主要交互函数**:
    *   `mintGame(string memory initialState)`: 铸造新的游戏NFT。
    *   `getGameState(uint256 tokenId)`: 获取指定NFT的游戏状态。
    *   `ownerOf(uint256 tokenId)`: 获取NFT的所有者 (用于列出NFT功能)。

---

这个README旨在提供项目的概览和基本操作指南。