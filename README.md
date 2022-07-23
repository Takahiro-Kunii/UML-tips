# UML-tips
UMLについて

plantumlという、テキストから図を起こすツールがあり、そこにUMLについての説明もある。

* [plantuml](https://plantuml.com/ja/)

mermaidはGithubでそのまま表示可能

* [mermaid](https://mermaid-js.github.io)

```mermaid
  graph TD;
      subgraph 追加構成
      sim(Robot Simulator)
      end
      subgraph 既存構成
      Human(人間)
      rc(Robot Controller)
      Robot
      end
      sim-->| 高さ指定 | rc
      rc-->| ライブ画像 |sim;
      rc-->|高さ指定|Robot;
      Robot-->|ライブ画像|rc
      Human-->|カメラ位置調整|Robot      
```

```mermaid
sequenceDiagram
    participant Human as 人間
    participant Robot
    participant rc as Robot Controller
    participant sim as Robot Simulator
    Human->>Robot: カメラの取り付け位置を微糖性
    Robot->>rc:ライブ画像
    rc->>sim:ライブ画像（UDP）
    sim->>sim: Robot側のモニター画像更新
```


## 分析
* ユースケース図

### ユースケース図

誰が、何をなんの目的で、どのように行うか

## 設計
* 配置図
* シーケンス図

### 配置図
配置(deployment)が、ハード、ソフトの具体的な配置を説明し、システムが何に依存するかはっきりさせる

ソフト部を抜き出しより抽象化しているコンポーネント図は、配置図の中でも書くので、最初は配置図からやるといい

### シーケンス図
どのように連携するか
