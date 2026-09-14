> [!IMPORTANT]
> **初めて RDL に触れる方へ**
> この `RDL_Core` は、関係力学言語（RDL）の基底措定・最低動作仕様・共有語彙・T1 操作仕様を管理する最も厳密なリポジトリです。
> マニフェスト、基本概念のチュートリアル、具体例を先に読みたい場合は、エントランスである [**RDL_Introduction**](https://github.com/Aporapeiron/RDL_Introduction) を参照してください。

# RDL_Core (The Core)

**関係力学言語（RDL: Relational Dynamics Language）** の基盤となる、基底措定（BASE v2.3）、最低動作仕様（SPEC v2.3）、共有語彙、および SILN 操作プロトコル（T0/T1）を保持する中核リポジトリです。

RDL が基本構造として扱うのは **SILN（Survival-biased Integration of Local Linear Approximations in a Nonlinear Network）** です。SILN は孤立した静的実体ではなく、非線形関係ネットワーク上で複数の **RIB（Relational Interaction Bundle）** と相互作用しながら構造を保持・変化させます。

RDL は世界そのものや相互作用全体を完全取得することを前提としません。用途・問いに応じて有限境界 $B$ を引き、構造側を自己側有限関係拘束構造 $M_B$、相互作用側を有限作用断面 `RIB_B` として扱います。

```text
SILN
  ↕
{RIB_1, RIB_2, ..., RIB_n, ...}
  ↓ 用途・問いに応じた B
RIB_B
  ↓
F = interp(M_B, RIB_B)
  ↓
F' → E → H → θ
           ├─ H < θ  : 維持・局所更新
           └─ H ≥ θ  : M_Δ → 展開・検査・選別・再構成 → M_B'
```

有限境界 $B$ には常に未回収関係 $\xi$ が残り、現在の構造・語彙・モデル・RDL自身も終端的真理として固定されません。

---

## 📂 Repository Structure

```text
RDL_Core/
│
├── 00_T0_基盤層/
│   ├── T0 基底措定（BASE）.md      (v2.3 SILN基底化 / RIB導入)
│   └── T0 最低動作仕様（SPEC）.md  (v2.3 RIB_B断面運用)
│
├── 01_T1_SILN操作層/
│   ├── T1_SILN操作_総論.md
│   ├── T1_SILN展開.md
│   ├── T1_検査と選別.md
│   └── T1_再構成.md
│
├── 02_TD_共有語彙層/
│   ├── TD_共有語彙.md               (SILN / RIB / RIB_B / M_B 共通定義)
│   ├── TD_自然言語概念のRDL的翻訳.md
│   ├── TD_整合と跳躍の観測的定義.md
│   ├── TD_よく使う概念語彙_時間_v0.1.md
│   ├── TD_よく使う概念語彙_空間_v0.1.md
│   ├── TD_よく使う概念語彙_ρ_無限解像度仮設_v0.1.md
│   └── TD_よく使う概念語彙_関係拘束と歪み_v0.1.md
│
├── 03_Explanation/
│   ├── AporapeironとSILN/
│   ├── EFP考察_文字に見る作用と解釈の境界.md  (旧体系由来・要同期)
│   ├── RDL語彙の道具的本質_便利語彙としての境界設定.md
│   ├── RDLに対する批判予測と回答案.md
│   └── RDL破断点考察.md
│
├── 04_Examples/
│   └── (具体事象をRDL変数で解剖した実例集)
│
└── README.md
```

---

## 🧬 各層・ディレクトリの役割

### 1. T0 基盤層 — 基底措定と最低動作仕様

RDL が成立するための最低条件と、通常運転／再編への状態遷移を規定します。

- **BASE**: SILN を基底構造に置き、非線形関係ネットワーク、RIB、有限境界 $B$、$M_B$、`RIB_B`、$\xi$ の基本関係を定める。
- **SPEC**: `RIB_B` を $M_B$ が解釈して $F$ を形成し、後続解釈との差異 $E$、未解消残存不整合 $H$、保持限界 $\theta$、再編相 $M_\Delta$ へ接続する最低動作を定める。

標準形：

```text
RIB_B(t) = Section_B({RIB_i(t)})
F(t)     = interp(M_B, RIB_B(t))
```

### 2. T1 SILN操作層 — 展開・検査・選別・再構成

T0 が「何が成立し、最低限どう動くか」を定めるのに対し、T1 は **SILN を特定の用途・問いのもとで対象化し、その構造をどう展開・検査・選別・再構成するか**を規定します。

- **SILN展開 (Expansion / Unfolding)**: 対象化した SILN、観測された `RIB_B` 列、既知理論等から、関係・状態・候補構造の可能性空間を開く。
- **検査と選別 (Inspection & Selection)**: T2 等の検査道具を用い、現在の $B$・目的・許容損失に対して残存可能な候補構造を絞り込む。
- **再構成 (Reconstruction)**: 選別された残存関係を、新たな自己側有限関係拘束構造 $M_B'$ として定着させる。
- **Probe**: 相互作用条件へ有限な探りを入れ、その結果として得られる `RIB_B` の変化・解釈差分を探索材料として用いる。RIB 全体や $\xi$ そのものを直接取得する操作ではない。

SILN は「対象側だけの食材」を意味しません。自己側の $M_B$ も、必要に応じて SILN として対象化し、通常の T1 操作へ戻すことができます。

### 3. TD 共有語彙層 — 共通辞書・翻訳

全層で使用する語彙の最小定義と身分を保持します。中心語彙は次の通りです。

```text
SILN    : RDL が扱う基底構造
RIB     : Relational Interaction Bundle / 関係ネットワーク上の相互作用束
B       : 用途・問いに応じた有限境界
M_B     : 構造側・自己側の B 依存有限断面
RIB_B   : 相互作用側の B 依存有限作用断面
ξ       : 有限境界に伴う未回収関係
F       : interp(M_B, RIB_B) による作用解釈・予測
E/H/θ   : 不整合・未解消残存不整合・保持限界
M_Δ     : 高負荷再編相
```

旧 `EFP / 素流圧` は廃止され、場側の相互作用束を `RIB`、有限作用断面を `RIB_B` として分離しています。

### 4. Explanation — 背景と解説

T0 / T1 の設計がどのような思考経路から成立したかを保存する層です。旧体系に基づく文書は履歴資料として残る場合がありますが、定義が衝突する場合は **T0 BASE / SPEC と TD_共有語彙を優先**します。

### 5. Examples — 具体実例

T0 / T1 の概念・式を、物理・社会・認知・記述・パラドックス等の具体事象へ適用した例を保持します。

---

## 🔗 エコシステムにおける位置づけ

`RDL_Core` は、**SILN とその RIB を有限境界のもとで記述・解釈・検査・再構成するための基底規則と操作仕様の提供元**です。

ここで定義された基底概念・日常式・操作仕様は、[**RDL_Functions**](https://github.com/Aporapeiron/RDL_Functions) によって具体的な数学・AIアルゴリズムへ翻訳され、[**RDL_Durability_Modules**](https://github.com/Aporapeiron/RDL_Durability_Modules) の検査道具を利用しつつ、[**RDL_Human**](https://github.com/Aporapeiron/RDL_Human) や [**RDL_Music_Theory**](https://github.com/Aporapeiron/RDL_Music_Theory) 等の応用層へ接続されます。

詳細なアーキテクチャ図は [Organization Profile](https://github.com/Aporapeiron/.github) を参照してください。
