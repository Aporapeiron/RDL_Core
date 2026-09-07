> [!IMPORTANT]
> **初めて RDL に触れる方へ**
> この `RDL_Core` は、関係力学言語（RDL）の基底公理と数式モデル（T0/T1）を管理する最も厳密なリポジトリです。
> マニフェスト（宣言）、基本概念のチュートリアル、パラドックス等の具体例（Examples）をお探しの方は、エントランスである [**RDL_Introduction**](https://github.com/Aporapeiron/RDL_Introduction) を先にご覧ください。

# RDL_Core (The Core)

**関係力学言語（RDL: Relational Dynamics Language）** の全ての土台となる、基底措定（BASE）、最低動作仕様（SPEC v2.0）、および対象を操作するための SILN プロトコル（T0/T1）を保持する「公理の聖域」です。

RDL は、世界そのものを絶対的な真理として直接記述することはしません。有限の境界 $B$ を通じて形成された「解釈と予測（$F$）」の不整合（$E$）を計算し、未解消不整合（熱 $H$）の蓄積と保持限界（$\theta$）突破による再編相（$M_\Delta$）への移行を記述するための言語です。

---

## 📂 Repository Structure

```text
RDL_Core/
│
├── 00_T0_基盤層/
│   ├── T0 基底措定（BASE）.md
│   └── T0 最低動作仕様（SPEC）.md  (v2.0 関係拘束・残存熱力学版)
│
├── 01_T1_SILN操作層/
│   ├── T1_SILN操作_総論.md
│   ├── T1_SILN展開.md
│   ├── T1_検査と選別.md
│   └── T1_再構成.md
│
├── 02_TD_共有語彙層/
│   ├── TD_共有語彙.md
│   ├── TD_自然言語概念のRDL的翻訳.md
│   ├── TD_整合と跳躍の観測的定義.md
│   └── TD_よく使う概念語彙_*.md
│
├── 03_Explanation/
│   └── (T0/T1の背景思想、思考のプロセス、メタ解説)
│
├── 04_Examples/
│   └── (パラドックスや具体事象をRDL変数で解剖した実例集)
│
└── README.md
```

---

## 🧬 各層・ディレクトリの役割

### 1. T0 基盤層 (基底措定と最低動作仕様)
RDL がシステムとして計算を回すための絶対ルール。
- **BASE**: 関係ネットワークに境界 $B$ を引くと有限関係拘束構造 $M_B$ とともに必ず余剰 $\xi$ が残るという基底措定（Foundational Postulates）。
- **SPEC**: 通常巡航代謝（$F/F'/E/H/\theta$ 比較ループ）と、保持限界突破時の高負荷再編相 $M_\Delta$ への移行を定める最低動作仕様。

### 2. T1 SILN操作層 (操作プロトコル)
T0 の力学を用いて、エージェントが対象を解剖・操作・再構成するための運用マニュアル。
- **展開 (Expansion)**: 通常代謝および未知 Probe の差分列から、関係・状態・候補構造群の可能性空間を開く。
- **検査と選別 (Inspection & Selection)**: 目的と許容損失に応じ、T2等の道具を用いて頑健な関係拘束構造を見極める（Source Constraint による相対的拘束評価を含む）。
- **再構成 (Reconstruction)**: 選別された関係核を新たな有限関係拘束構造 $M_B'$ として自己側へ定着・血肉化させる。

### 3. TD 共有語彙層 (翻訳・辞書プロトコル)
既存の日常用語や曖昧な概念（時間、意味、価値、整合、跳躍など）をそのまま使わず、T0 の力学パラメーター（$B, M_B, \xi, E, H, \theta$）に厳密に「翻訳（マッピング）」するためのプロトコル。内部推論の精度を極限まで高めるための辞書です。

### 4. Explanation (背景と解説)
T0 / T1 がなぜそのような設計になったのかという、基底に至るまでの思考プロセスやメタ的な背景を保存する層です。RDL のアーキテクチャの根拠となる考察が格納されます。

### 5. Examples (具体実例)
T0 / T1 の公理や計算式が、実際の事象（パラドックス、オカルト、日常現象など）にどのように適用できるかを示す実例集です。抽象的な公理を具体的な事象へ当てはめる際のトレーニングデータとして機能します。

---

## 🔗 エコシステムにおける位置づけ

`RDL_Core` は、Aporapeiron の代謝プロセス（SILN）における **「日常式・公理の提供元」** です。

ここにある公理（日常式）は、[**RDL_Functions**](https://github.com/Aporapeiron/RDL_Functions) (T2) によって具体的な数学・AIアルゴリズムへと翻訳され、[**RDL_Durability_Modules**](https://github.com/Aporapeiron/RDL_Durability_Modules) (T2) による過酷な耐久検査を経たのち、[**RDL_Human**](https://github.com/Aporapeiron/RDL_Human) や [**RDL_Music_Theory**](https://github.com/Aporapeiron/RDL_Music_Theory) (T3) の現実課題へと適用されていきます。

詳細なアーキテクチャ図は、[Organization Profile](https://github.com/Aporapeiron/.github) を参照してください。