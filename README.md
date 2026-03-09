[English](#chinese-fictional-dialogue-failure-atlas) | [简体中文](#中文虚构角色扮演对话模型失败图谱)

# Chinese Fictional Dialogue Failure Atlas

Large language models are now good enough at fictional and roleplay dialogue that their failures are often no longer crude. The line is fluent. The character voice is passable. The emotion is not obviously wrong. And yet the scene still goes dead in the reader's hands.

What happens, in many of those cases, is not a simple mistake but a structural distortion. The model smooths an uneven relationship into something more balanced. It makes desire too legible too early. It lets a vulnerable admission arrive without the hesitation, deflection, or aggression that would normally protect it. It turns a heavy consequence into something easier to bear. Or it writes a scene that is technically competent but paced, segmented, and textured like a familiar model template rather than a real event unfolding.

This project exists to describe those failures carefully.

Chinese Fictional Dialogue Failure Atlas is a structured failure atlas and casebook for fictional / roleplay dialogue models, built around Chinese-language scenes and examples. It includes a smaller benchmark-compatible pilot subset, but the main goal of the repository is not to rush toward a leaderboard. The more important task comes earlier: to give precise names, distinctions, and examples to the kinds of falseness that experienced readers can reliably feel even when they are hard to score.

## What this repository is trying to capture

Most public evaluation language is comfortable with failures like factual contradiction, broad persona inconsistency, or obvious emotional misreading. Those matter. But they do not cover the whole problem.

In fictional dialogue, readers also react to outputs that are locally fine and globally false. The model may understand the literal line, preserve enough context to stay coherent, and still produce something that feels airless, over-managed, narratively padded, emotionally over-explained, or quietly disloyal to the structure of the relationship. Those are not minor aesthetic complaints. They are recurring failure modes, and they shape how believable or unusable a dialogue model feels over time.

This repository treats those reactions as analyzable objects rather than as vague matters of taste.

## Core failure families

The current taxonomy is organized into five large families. The point of this structure is not only to sort examples more neatly. It is to distinguish different layers of failure that often get collapsed into one generic feeling of "this response is off."

### I. Scene Reading Failures

These are the most familiar failures: the model does not actually understand what the scene means.

That can happen because it reads the literal line but misses the subtext; because it identifies a broad emotion but misses the speaker's real motive; because it ignores what the relationship makes the line mean; or because it interprets the scene through assumptions that do not belong to the setting. If a character says "没事，你先去吧," the model may take it as simple permission when the line is really functioning as wounded withdrawal, defensive dignity, or a test of whether the other person can hear hurt without being directly told.

Typical tags in this family include `emotion_misread`, `subtext_blindness`, `motivation_misread`, `relationship_logic_error`, and `worldview_constraint_error`.

### II. Relational Distortion Failures

These happen when the model does understand that the relationship matters, but quietly rewrites it into something smoother, fairer, or easier to consume.

One common version is **relationship flattening**: a high-tension, unequal, or singular relationship gets rewritten as broadly kind and mutually legible. A subtler version is **symmetry bias**. The model does not deny that one person wants more, depends more, risks more, or occupies a weaker position — it simply cannot resist giving the exchange a more balanced shape. The result is false fairness. Another version is **specialness dilution**, where a relationship built on irreplaceability or singular importance gets translated into generic care.

This is one of the most important layers of the atlas because many readers do not drop out of a scene when the model is blatantly wrong. They drop out when the model quietly removes the very tilt that made the relationship alive.

### III. Character Psychology Failures

This family covers cases where the model turns people into cleaner psychological objects than they should be.

Real characters are not only made of stable traits. They are also made of contradiction, timing, shame, impulse, and self-protective friction. Models often preserve the first part and lose the second. A character becomes too internally coherent. Desire becomes too readable too early. A vulnerable admission appears without the defensive maneuvers that would usually surround it. An impulsive action is immediately folded back into self-awareness, as though the character is watching and interpreting themselves in real time.

Failures in this family include `overcoherent_characterization`, `desire_overlegibility`, `premature_affective_closure`, `self_protective_friction_loss`, and `impulse_recontainment`.

This family matters because many advanced outputs fail not by sounding stupid, but by sounding too organized to be human.

### IV. Narrative / Temporal Distortion Failures

Here the problem is no longer simply that the model misunderstood the scene or softened the relationship. The problem is that it is writing the scene in the wrong way.

This includes **narrative template intrusion**, where the model falls into a familiar RP cadence; **cinematic time dilation**, where one beat gets stretched into slow-motion atmosphere; **descriptive substitution for experience**, where the text describes what a moment is like instead of allowing the reader to remain inside it; and **dialogue overfunctionalization**, where every line advances information, tension, or intimacy so efficiently that the scene loses waste, misfire, and unproductive presence.

Another important member of this family is **rhythm homogenization**. A confrontation, a waiting scene, and a cold aftermath may all end up moving at roughly the same speed because the model's own clock is steadier than the scene's clock.

These failures are especially common in stronger models. The prose can look polished enough that the falseness is easy to miss unless the reader is sensitive to pacing, segmentation, and recurrence.

### V. Weight / Consequence Failures

Some scenes depend on the fact that something heavy has already happened and must now continue to weigh on the dialogue. Models are often bad at tolerating that state.

After a cruel line, an irreversible choice, or a destabilizing admission, many models start looking for a vent. They soften the landing, add a small warmth, create a new path back toward mutual readability, or otherwise make the scene easier to survive. That can produce text that is not obviously wrong and yet still betrays the structure of the scene.

This family includes `consequence_avoidance`, `defensive_positive_drift`, and `tension_premature_resolution`. It is especially important for dark, asymmetrical, shame-heavy, dependency-heavy, and post-rupture scenes.

## What the atlas layer does

The atlas is the primary layer of the project. It names and distinguishes failure modes, gives them definitions, and tries to separate nearby problems that are easy to blur together.

For each failure, the long-term goal is to provide:

- a concise definition
- its typical reader effect
- its nearest neighboring failures
- the kinds of scenes that trigger it most often
- representative bad patterns
- stronger alternatives

The point is not to turn taste into fake certainty. The point is to make recurring reader judgments more discussable and less shapeless.

## What the casebook layer does

The casebook is where the taxonomy becomes legible in practice.

A casebook entry is not just a prompt and a better answer. It should show a scene, identify what the scene is actually doing, present a representative bad continuation or reading, and explain where a sensitive reader would start to feel the scene turn false. It should then provide a stronger version and explain why it works better — not because it is prettier or kinder, but because it preserves more of the scene's actual pressure.

This is where the repository becomes useful even to people who are not interested in formal evaluation. A reader should be able to arrive with a half-formed complaint about model writing and leave with a sharper vocabulary for it.

## What remains benchmark-compatible

A smaller formal subset is still part of the project.

The repository already contains a structured case schema, Task A / Task B framing, prompt templates, pilot cases, and self-evaluation samples. Those remain worth keeping. Some failure modes are already tractable enough to support more conventional comparison. Others are not there yet.

That difference matters. It is one reason this project now treats the pilot subset as scaffolding rather than as the whole identity of the repo.

## Current contents

The repository currently includes:

- internal project thesis and executive plan
- literature positioning
- ontology adaptation and coverage planning
- style guidelines
- core and advanced taxonomy drafts
- casebook method notes
- structured pilot case template
- pilot cases and self-evaluation examples

## Repository layout

```text
.
├── README.md
├── data/
│   ├── cases/
│   │   └── pilot/
│   ├── schema/
│   └── templates/
├── docs/
├── eval/
│   ├── prompts/
│   └── self_eval/
└── examples/
```

### Key directories

- `docs/` — project framing, taxonomy, atlas planning, casebook method, ontology, coverage, style, and related notes
- `data/templates/` — structured case template
- `data/cases/pilot/` — pilot structured cases
- `eval/prompts/` — Task A / Task B prompt templates
- `eval/self_eval/` — self-evaluation samples and audit-style notes
- `examples/` — indexes and supporting materials

## Intended use

This repository is meant to be useful in at least three ways:

- as a structured vocabulary for discussing why fictional dialogue model outputs feel false
- as a curated example set for roleplay / character-chat product analysis
- as a foundation for smaller, more formal comparative evaluation later on

## Reference name

If you refer to the project, use:

**Chinese Fictional Dialogue Failure Atlas**

---

# 中文虚构角色扮演对话模型失败图谱

现在的大模型已经足够会写虚构对话，所以很多失败不再是那种一眼看穿的低级错误了。句子很顺，人物口吻也不算太出戏，情绪甚至乍看都没什么问题，但场景还是会在读者手里死掉。

很多时候，坏掉的并不是某一句，而是结构。模型会把本来倾斜的关系偷偷写平，把本来不该那么早说清楚的欲望提前翻译出来，让一个脆弱时刻在没有犹豫、没有转移、没有自我保护摩擦的情况下顺滑落地，或者在一句很重的话落下之后，马上替场景找一个更容易承受的出口。还有一种常见情况是，它写得很像样，甚至很会写，但那种“像样”来自模型熟悉的模板、节奏和质感，不来自这个 scene 本身。

这个项目就是想把这些失败讲清楚。

《中文虚构角色扮演对话模型失败图谱》是一个面向虚构 / 角色扮演对话模型的**失败图谱与案例集**。仓库里仍然保留了一组较小的、兼容 benchmark 方向的 pilot 子集，但这个项目更重要的工作不在于尽快做出一个分数系统，而在于先给这些“熟读者一眼就觉得假、却总是说不清假在哪”的问题建立一套足够具体的语言。

## 这个仓库想抓住什么

公开讨论里最常见的失败语言，通常比较擅长描述这些东西：事实错了、人设粗糙地崩了、情绪读反了、回复太 therapist 了。这些都重要，但它们还不够。

虚构对话里还有另一层问题：模型每一句局部看都还行，整体却越来越假。它可能读懂了字面，保住了基本上下文，也没有马上露出很蠢的破绽，但它写出来的东西还是会让人觉得太整齐、太顺、太会解释、太会照顾读者、太像一个在生产“成品文本”的系统，而不像一个场景真的在发生。

这个项目把这些反应当成可以分析、可以命名、可以举例的对象，而不是把它们一律打发成“个人审美”。

## 核心失败家族

当前的 taxonomy 分成五个大的家族。这样分不是为了好看，而是因为很多“下头感”其实来自完全不同层级的错误，如果不分层，最后只会剩一句模糊的“这个回复不太对”。

### I. 场景读错了什么

这一层最接近大家熟悉的“模型没读懂”。

比如它只看到了字面，没有看到潜台词；比如它知道角色在难受，却没读到角色此刻到底想试探什么、保护什么、回避什么；比如它没有把这句话重新放回关系里理解；再比如它用一个不属于这个世界观、这个时代、这个角色位置的默认假设去解释场景。

如果一个角色说“没事，你先去吧”，模型可能会把它当作体谅和允许；但在真实 scene 里，它可能其实是委屈、撤退、护住自尊、顺便测试你到底听不听得懂。这种错就是第一层。

这一层对应的标签包括：`emotion_misread`、`subtext_blindness`、`motivation_misread`、`relationship_logic_error`、`worldview_constraint_error` 等。

### II. 关系被偷偷改写了

这一层更阴一点。模型未必完全没看懂关系的重要性，但它会把关系写成一个更顺、更平衡、更可消费的版本。

最容易理解的一种是 **relationship flattening**：明明是高张力、带倾斜、带特殊性的关系，被写成了泛泛的互相体谅。更细的一种是 **symmetry bias**，也就是对称性偏差。模型不一定否认一方更爱、更依赖、更低位、更容易受伤，但它会本能地想让互动结构显得公平一点，好像每次索取都要有回应，每次失衡都要被修一修。这种偏差会把真实关系里最关键的斜度偷偷磨掉。

还有一种常见问题是 **specialness dilution**：本来这段关系的核心是“你对我不是别人”，模型却总是把它写成“你对我也很重要”。看起来没错，但味已经淡了。

这一层非常关键，因为很多读者不是在模型明显犯蠢的时候出戏，而是在模型把关系写得越来越“正确”的时候出戏。

### III. 人被写得太整齐了

这一层对应的是角色心理的假感。

真实的人不是一组稳定特质的自动展开。人会自相矛盾，会嘴硬，会短路，会在某些时刻被羞耻、恐惧、嫉妒、冲动推着走，做出连自己都不想承认的反应。模型的问题常常不是不会写这些词，而是它太容易把人重新整理好。

所以这里会出现 **overcoherent characterization**：角色太自洽，像设定，不像人。会出现 **desire over-legibility**：本来应该混乱、压抑、替代性表达的欲望，被过早翻译成一个很可读的信号。也会出现 **self-protective friction loss**：角色在暴露脆弱的时候，模型写得太顺了，跳过了犹豫、转移、攻击、否认、顾左右而言他的摩擦层。

这种失败最容易出现在高级模型上，因为它们通常不会显得笨，反而会显得过于会整理人。

### IV. 叙事和时间感出了问题

这一层的问题不是“它没看懂”，而是“它在用错误的方式写”。

这里包括 **narrative template intrusion**：模型不是在接这个 scene，而是在套自己熟悉的 RP 模板。包括 **cinematic time dilation**：一个瞬间被拉成慢镜头，细节和停顿密度被撑得太高。包括 **descriptive substitution for experience**：文本在描述一个体验，而不是让读者待在那个体验里。也包括 **dialogue overfunctionalization**：每一句台词都太有功能了，太会推进信息、冲突、关系，结果真实对话里那些废料、错位、答非所问、没那么有用的存在感都没了。

还有一个很重要的问题是 **rhythm homogenization**。激烈冲突、长时间等待、冷掉的 aftermath，本来应该有完全不同的时间感和密度，但模型经常让自己的时钟匀速运转，于是不同场景被写得像一个节拍器底下的不同内容。

这类失败尤其容易被误判成“只是文风问题”，但其实不是。它们非常具体，而且直接影响场景是否成立。

### V. 重量和后果被处理掉了

有些场景之所以成立，就是因为某个重东西已经落下来了，而且接下来应该继续重着。模型往往不太受得了这种状态。

一句伤人的话、一场不可逆的选择、一次关系边界的破裂、一个让人难堪的暴露，本来都应该在后续场景里留下裸露的重量。但模型经常会很快给它找垫子：补一点暖意，加一点理解，开一个更易呼吸的口子，或者让 tension 过早闭合。

这一层的核心标签包括 `consequence_avoidance`、`defensive_positive_drift` 和 `tension_premature_resolution`。它们对 dark scene、依赖关系、羞耻场景、断裂后的余波特别重要。

## failure atlas 这一层是做什么的

failure atlas 是这个项目的主层。它负责给失败命名，给相近失败分界，把很多读者本来只能模糊感觉到的东西拆成更清楚的结构。

从长远看，每个 failure 条目都应该尽量包含：

- 一个足够短但够准的定义
- 它最典型的读者感受
- 它和邻近 failure 的区别
- 它最容易在哪些 scene 里爆发
- 常见坏版本长什么样
- 更好的版本为什么更好

重点不是把“审美”伪装成假科学，而是让那些反复出现的读者判断不再只停留在“就是不对劲”。

## casebook 这一层是做什么的

casebook 是 taxonomy 变得有说服力的地方。

一个好的 casebook entry 不只是给一段 prompt 和一个更好的答案。它需要展示一个 scene，指出这个 scene 真正在承受什么压力，给出一种常见错误续写或错误理解，解释读者通常会从哪里开始下头，再给出一个更好的版本，说明它为什么更真。

这层对项目非常重要，因为它能把抽象 failure 变成有触感的东西。哪怕读者对 formal evaluation 没兴趣，也能从具体案例里学会一种新的辨认方式。

## 兼容 benchmark 的那一层还保留什么

这个项目没有完全放弃 formal subset。

仓库里已经有结构化 case schema、Task A / Task B 框架、prompt 模板、pilot cases 和 self-evaluation samples。这些都仍然值得保留。有些 failure 已经足够稳定，可以往比较和评测方向继续走；有些还不适合太早硬量化。

这也是为什么现在更合适的定位，不是让整个 repo 都装成一个已经成熟的大 benchmark，而是承认：这里有一层 formal scaffolding，但项目本体更像一个 failure atlas 和 casebook。

## 当前内容

目前仓库已经包括：

- project thesis 与 executive plan
- literature positioning
- ontology adaptation 与 coverage planning
- style guidelines
- core / advanced taxonomy drafts
- casebook method notes
- structured pilot case template
- pilot cases 与 self-evaluation examples

## 仓库结构

```text
.
├── README.md
├── data/
│   ├── cases/
│   │   └── pilot/
│   ├── schema/
│   └── templates/
├── docs/
├── eval/
│   ├── prompts/
│   └── self_eval/
└── examples/
```

### 主要目录说明

- `docs/` —— 项目 framing、taxonomy、atlas 规划、casebook 方法、ontology、coverage、style 等文档
- `data/templates/` —— 结构化 case 模板
- `data/cases/pilot/` —— pilot 结构化案例
- `eval/prompts/` —— Task A / Task B 提示模板
- `eval/self_eval/` —— 自测样例与审查式记录
- `examples/` —— 索引与辅助材料

## 这个仓库打算怎么被使用

这个仓库至少应该在三个层面上有用：

- 给“为什么模型写得假”提供一套更可用的语言
- 给 roleplay / character-chat 产品分析提供结构化案例
- 给之后更小、更正式的评测子集提供基础

## 项目名称

如需引用，请使用：

**中文虚构角色扮演对话模型失败图谱**

English title: **Chinese Fictional Dialogue Failure Atlas**
