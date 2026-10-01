# Multi-Camera Video Prompt

一个用于编写和修复多机位视频生成提示词的 Codex Skill。它根据主体、场景、动作、时长、画幅、参考素材和声音要求安排镜头，并保持人物、动作和空间连续。

## 适合处理

- 把视频创意整理成多机位生成提示词；
- 安排全景、中景、近景、特写、过肩和跟拍镜头；
- 让连续动作在不同镜头之间自然衔接；
- 修正跳轴、视线错误、人物站位突变、背景漂移和切镜过密；
- 根据需要输出自然语言分镜或带时间段的分镜；
- 处理配乐、对白、音效、环境声和静音要求。

## 不处理

- 不直接生成或编辑视频；
- 不提交外部平台任务；
- 不自动增加用户没有要求的剧情、人物、字幕、品牌或声音。

## 安装

将整个文件夹复制到 Codex Skills 目录：

```bash
cp -R multi-camera-video-prompt ~/.codex/skills/
```

也可以把仓库克隆到同一目录。安装后重新载入 Codex，使 Skill 出现在可用技能列表中。

## 使用

显式调用：

```text
Use $multi-camera-video-prompt to turn my video idea into a coherent multi-camera generation prompt.
```

中文示例：

```text
使用 $multi-camera-video-prompt，把“一位厨师在家庭厨房完成一道早餐”写成20秒、多机位、自然语言分镜的视频提示词。保持厨房布局和人物动作连续，无BGM，只保留动作音效和环境声。
```

Skill 默认允许自动调用。当请求涉及多机位视频提示词、镜头设计、动作连续性或跳轴修正时，Codex 可以自动选择它。

## 输出

默认输出一个可直接复制的 `text` 代码块，包含：

1. 主体
2. 风格
3. 分镜
4. 声音
5. 限制

分镜默认使用自然语言。用户明确要求按秒、节拍同步或严格时长分配时，才使用连续时间段。

## 目录

```text
multi-camera-video-prompt/
├── SKILL.md
├── README.md
├── LICENSE
├── agents/
│   └── openai.yaml
├── references/
│   └── prompt-contract.md
└── examples/
    └── multi-camera-scene.md
```

- [`SKILL.md`](SKILL.md)：触发条件、工作方式和交付规则；
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 界面元数据和调用策略；
- [`references/prompt-contract.md`](references/prompt-contract.md)：完整输出合同与连续性检查；
- [`examples/multi-camera-scene.md`](examples/multi-camera-scene.md)：通用多机位示例。

## License

MIT，详见 [`LICENSE`](LICENSE)。
