
<!-- 个人 GitHub 首页 README（酷炫款 · 为 feichenchina 定制） -->

<p align="center">
  <a href="https://github.com/feichenchina"> 
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3000&pause=800&color=2AF7DC&center=true&vCenter=true&width=800&lines=Hi%2C+I'm+feichenchina+%F0%9F%91%8B;Code%2C+Compute%2C+and+Creativity;Build+fast%2C+ship+reliable%2C+secure+by+design" alt="Typing SVG" />
  </a>
</p>

<p align="center">
  <img src="https://visitor-badge.laobi.icu/badge?page_id=feichenchina.feichenchina" alt="visitors"/>
  <img src="https://img.shields.io/github/followers/feichenchina?label=Follow&style=social" alt="followers"/>
  <img src="https://img.shields.io/github/stars/feichenchina?label=Total%20Stars&style=social" alt="stars"/>
</p>

---

## 🚀 关于我
- 🧭 专注方向：高性能计算 / AI 工程 / 自动化工具
- 🛠 常用语言：Python · JS . VUE · C/C++
- 🧪 兴趣点：交易自动化、工作流编排、推理服务与效率提升
- 💬 联系方式：[Email](tiejipiaoliu@163.com)

---

## 🧰 技术栈 & 工具
<p align="left">
  <img src="https://skillicons.dev/icons?i=python,cpp,js,ts,vue,html,css" />
  <br/>
  <img src="https://skillicons.dev/icons?i=pytorch,torch_npu" />
  <br/>
  <img src="https://skillicons.dev/icons?i=docker,linux,git,vscode,redis,postgres,mysql" />
</p>

---

## 📊 GitHub 数据看板
<!-- 📊 GitHub 数据看板 -->
<p align="center">
  <!-- 总览统计 -->
  <img
    height="170"
    src="https://github-readme-stats.vercel.app/api?username=feichenchina&show_icons=true&theme=radical&rank_icon=github&include_all_commits=true&count_private=true&cache_seconds=7200"
    alt="GitHub Stats"
  />
  <!-- 语言占比 -->
  <img
    height="170"
    src="https://github-readme-stats.vercel.app/api/top-langs/?username=feichenchina&layout=compact&langs_count=10&theme=radical&cache_seconds=7200"
    alt="Top Languages"
  />
  <br/>
  <!-- 连续贡献 -->
  <img
    height="170"
    src="https://streak-stats.demolab.com?user=feichenchina&theme=radical&date_format=%5BY.%5Dm.%5Bd&hide_border=true"
    alt="GitHub Streak"
  />
</p>


---

## ⭐ 精选项目
<p>
  
[![daily_filling](https://github-readme-stats.vercel.app/api/pin/?username=feichenchina&repo=daily_filling&theme=radical)](https://github.com/feichenchina/daily_filling)

> 日填充工具 / 自动化习惯追踪与数据记录

[![go_binance_futures](https://github-readme-stats.vercel.app/api/pin/?username=feichenchina&repo=go_binance_futures&theme=radical)](https://github.com/feichenchina/go_binance_futures)

> Go 语言实现的币安合约交易工具/SDK

[![Claude-Code-Workflow](https://github-readme-stats.vercel.app/api/pin/?username=feichenchina&repo=Claude-Code-Workflow&theme=radical)](https://github.com/feichenchina/Claude-Code-Workflow)

> 面向 Claude 的代码工作流与自动化示例


---

## 🧪 最近活动
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username={username}&theme=react-dark&hide_border=true" />
</p>

---

## 📝 最新博文（自动同步）


---

## 🎯 里程碑
- [x] 发布/维护 {len(repos)} 个代表性仓库
- [x] 打造个人工作流与自动化工具链
- [ ] 下一步：将更多实践沉淀为文档与教程

---

## 🧩 趣味 & 生活
> 跑步 / 旅行 / 游戏（按喜好更改）

```mermaid
graph TD
    %% 定义样式
    classDef host fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef device fill:#f3e5f5,stroke:#4a148c,stroke-width:2px;
    classDef memory fill:#fff9c4,stroke:#fbc02d,stroke-width:2px,stroke-dasharray: 5 5;
    classDef compute fill:#ffccbc,stroke:#bf360c,stroke-width:2px;
    classDef bus fill:#e0e0e0,stroke:#616161,stroke-width:2px;

    subgraph Host_Server [🖥️ CPU Host & System Memory]
        class Host_Server host
        UserReq(用户请求 JSON) --> |HTTP| APIGateway[API Gateway / Server]
        APIGateway --> |解析| Tokenizer[分词器 Tokenizer]
        Tokenizer --> |Token IDs| HostDRAM[(Host DRAM\nCPU 主存)]
        Scheduler[调度器 Scheduler] --> |分配 Page 表| HostDRAM
    end

    HostDRAM ==> |PCIe Gen4/5 / NVLink\n传输 Token IDs & 元数据| GPU_HBM

    subgraph GPU_Device [🚀 NVIDIA GPU Architecture]
        class GPU_Device device
        
        subgraph Global_Memory [High Bandwidth Memory (HBM)]
            class Global_Memory memory
            GPU_HBM[(HBM 显存)]
            Weights[(模型权重 Weights\nFP16/INT8)]
            KVCache[(KV Cache Pool\nPaged Blocks)]
            LogitsMem[(Logits Buffer)]
        end

        subgraph Compute_Unit [Streaming Multiprocessor (SM)]
            class Compute_Unit compute
            
            subgraph OnChip_Memory [SRAM L1 / Shared Memory]
                class OnChip_Memory memory
                SRAM[(Shared Mem / L1\n极速缓存)]
                Regs[寄存器 Registers]
            end

            TensorCores[⚡ Tensor Cores\n矩阵乘法 GEMM]
            CUDACores[🔧 CUDA Cores\n向量加减/激活/Norm]
        end

        %% 详细数据流与计算流
        GPU_HBM -.-> |1. Load Embeddings| SRAM
        Weights -.-> |2. Load Weights| SRAM
        
        SRAM --> |3. Inputs & Weights| TensorCores
        TensorCores --> |4. Q, K, V Projections| Regs
        
        Regs --> |5. RoPE 旋转| CUDACores
        
        Regs --> |6. Write New K,V| KVCache
        KVCache -.-> |7. Read History K,V| SRAM
        
        SRAM --> |8. FlashAttention\nSoftmax(QK^T)V| TensorCores
        
        TensorCores --> |9. FFN / MLP\nUp & Down Projections| Regs
        Regs --> |10. Activation SiLU/GELU| CUDACores
        
        Regs --> |11. Final Layer Norm| CUDACores
        TensorCores --> |12. LM Head Projection| LogitsMem
    end

    subgraph Sampling_Phase [🎲 Sampling & Output]
        class Sampling_Phase compute
        LogitsMem --> |13. Temperature Div| CUDACores
        CUDACores --> |14. Top-K / Top-P Sort| SRAM
        SRAM --> |15. Softmax & Select| NewTokenID(新 Token ID)
    end

    NewTokenID ==> |PCIe 回传| HostDRAM
    HostDRAM --> |Detokenize| Response(流式响应文本)

    %% 连接关系
    GPU_HBM --- Weights
    GPU_HBM --- KVCache
    GPU_HBM --- LogitsMem

---

### 使用说明
1. 在 GitHub 新建/打开 `feichenchina/feichenchina` 仓库。
2. 将本 `README.md` 置于根目录并提交。
3. 如不需要第三方统计服务，删除对应图片链接即可。

<p align="center">
  Made with ❤️  —  Keep coding, keep shipping.
</p>
```
