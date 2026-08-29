> [!IMPORTANT]
> **初めて RDL に触れる方へ**
> この `RDL_Core` は、関係力学言語（RDL）の基底公理と数式モデル（T0/T1）を管理する最も厳密なリポジトリです。
> マニフェスト（宣言）、基本概念のチュートリアル、パラドックス等の具体例（Examples）をお探しの方は、エントランスである [**RDL_Introduction**](https://github.com/Aporapeiron/RDL_Introduction) を先にご覧ください。

# RDL_Core (The Core)

**関係力学言語（RDL: Relational Dynamics Language）** の全ての土台となる、基底仮設（HYP）、最低動作仕様（SPEC v0.8）、および対象を操作するための SILN プロトコル（T0/T1）を保持する「公理の聖域」です。

RDL は、世界そのものを絶対的な真理として直接記述することはしません。有限の境界 $B$ を通じて形成された「解釈と予測（$F$）」のズレ（$E$）を計算し、熱（$H$）の蓄積による再編（SILN）を記述するための言語です。

---

## 📂 Repository Structure

```text
RDL_Core/
│
├── 00_T0_観測層/
│   ├── T0 基底仮設（HYP）.md
│   └── T0 最低動作仕様（SPEC）.md  (v0.8 認識論的徹底版)
│
├── 01_T1_SILN層/
│   ├── 01_T1_SILN操作プロトコル.md
│   └── (展開・選択・再構築の各フェーズ文書)
│
├── 02_TD_共通語彙層/
│   ├── TD_辞書.md
│   ├── TD_既存用語RDL翻訳.md
│   └── TD_整合と跳躍の観測的定義.md
│
└── README.md
```

---

## 🧬 各層の役割

### 1. T0 観測層 (基底仮設と最低動作仕様)
RDL がシステムとして計算を回すための絶対ルール。
- **HYP**: いかなる境界 $B$ にも必ず余剰 $\xi$ が残るという基底仮設。
- **SPEC**: $EFP \to F \to E \to H \to M_B'$ という、対象の解釈とズレを計算する代謝ループの定義。

### 2. T1 SILN層 (操作プロトコル)
T0 の力学を用いて、エージェントが対象を解剖・操作するための運用マニュアル。
- **展開 (Expansion)**: 熱を与えて可能性を限界まで広げる。
- **選択 (Selection)**: 強靭な構造を見極める（Survival-biased）。
- **再構築 (Reconstruction)**: 新たな $M_B'$ として定着させる。

### 3. TD 共通語彙層 (翻訳・辞書プロトコル)
既存の日常用語や曖昧な概念（時間、意味、価値、整合、跳躍など）をそのまま使わず、T0 の力学パラメーター（$B, M_B, \xi, H$）に厳密に「翻訳（マッピング）」するためのプロトコル。内部推論の精度を極限まで高めるための辞書です。

---

## 🔗 エコシステムにおける位置づけ

`RDL_Core` は、Aporapeiron の代謝プロセス（SILN）における **「日常式・公理の提供元」** です。

ここにある公理（日常式）は、[**RDL_Functions**](https://github.com/Aporapeiron/RDL_Functions) (T2) によって具体的な数学・AIアルゴリズムへと翻訳され、[**RDL_Durability_Modules**](https://github.com/Aporapeiron/RDL_Durability_Modules) (T2) による過酷な耐久検査を経たのち、[**RDL_Human**](https://github.com/Aporapeiron/RDL_Human) や [**RDL_Music_Theory**](https://github.com/Aporapeiron/RDL_Music_Theory) (T3) の現実課題へと適用されていきます。

詳細なアーキテクチャ図は、[Organization Profile](https://github.com/Aporapeiron/.github) を参照してください。
