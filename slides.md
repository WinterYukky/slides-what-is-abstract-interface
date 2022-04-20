---
theme: default
background: /josephine-bredehoft-KsAo8ouBn8A-unsplash.jpg
highlighter: shiki
lineNumbers: true
colorSchema: 'dark'
fonts:
  sans: 'Noto Sans Japanese'
  serif: 'Noto Sans Japanese'
  mono: 'Inconsolata'
---

# 抽象クラスとインターフェースの重要性が<br />100倍理解できるようになる講義

Presentation slides for beginners

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<style>
h1 {
  font-size: 2.5rem !important;
}
</style>

---
layout: center
class: text-center
---

# 突然ですが<br>洗濯機をJavaのクラスとして表してみてください

---

# 洗濯機クラスが出来上がりましたか？

```java
/**
 * 洗濯機クラス
 */
public class WashingMachine {
  /** 入っている衣服を表します */
  private Array<Wear> wears;

  /** 衣服を追加します */
  void add(Wear wear) { }

  /** 洗剤を投下します */
  void setDetergent(Detergent detergent) { }

  /** 洗濯を開始します */
  Array<Wear> wash() {
    this.wears.forEach(wear => wear.dart = false);
    return this.wears;
  }
}
```

---
layout: center
class: text-center text-3xl
---

<div>この講義の最終目標は、</div>
<div>先ほどのような課題が与えられた際に</div>
<div>皆さんが<span v-click class="italic underline font-bold text-4xl text-sky-400">洗濯機クラスを作らなく</span>なることです</div>

---

<the-agenda :step="1" />

---

# クラス

オブジェクトの属性や振舞を定義する

<div class="grid grid-cols-2 items-center text-2xl h-3/5">
  <div>
    <ul>
      <li>オブジェクトの属性や振舞を定義</li>
      <li>インスタンス化できる</li>
      <li>初心者向けに設計図と説明されることも</li>
    </ul>
  </div>
  <div>

```java
public class Yamada {
  private String from = "Japan";
  public void greet() {
    System.out.println("こんにちは");
  }
}
```

  </div>
</div>

---

# 抽象クラス

派生クラスの基底となるクラスを定義する

<div class="grid grid-cols-2 items-center text-2xl h-3/5">
  <div>
    <ul>
      <li>オブジェクトの属性や振舞を定義</li>
      <li>抽象メソッドを定義できる</li>
      <li>単体でインスタンス化できない</li>
    </ul>
  </div>
  <div>

```java
public abstract class Japanese {
  protected String from = "Japan";
  public abstract void greet();
}
```

  </div>
</div>

---

# インターフェース

メソッドの型を定義する

<div class="grid grid-cols-2 items-center text-2xl h-3/5">
  <div>
    <ul>
      <li>メソッドの型のみを定義する</li>
      <li>属性を定義できない</li>
      <li>インスタンス化できない</li>
    </ul>
  </div>
  <div>

```java
public interface Human {
  void greet();
}
```

  </div>
</div>

---
layout: center
class: text-center
---


# この説明で理解できた方、この講義は不要です
そうじゃない？では、一緒に続きを見ましょう

---

<the-agenda :step="2" />

---
layout: center
---

# Q. みなさん、家でどんな洗濯機を使っていますか？

---
layout: center
class: text-center text-2xl
---

あなたが友人の家に泊まったとします。

その日、友人に家事を手伝って欲しいと言われ、あなたは洗濯をすることにしました。  
洗濯機と洗剤等の場所は知っています。  

洗濯機の機種は知りませんが、恐らく洗濯できますよね？

---

# 洗濯機と言っても色々

<div class="grid grid-cols-2 items-center">
  <ul class="text-xl">
    <li>SHARP製？日立製？三菱製？</li>
    <li>ドラム式？全自動式？</li>
    <li>中身は同じパーツ？</li>
    <li>回転速度とかは同じ？</li>
    <li>完全に同じ機能？</li>
    <li>ボタンの場所は同じ？</li>
  </ul>
  <div class="text-center h-4/5">
    <img src="/SHARP-洗濯機.png" class="mb-1 h-full" />
    <div class="text-sm opacity-60">SHARP製洗濯機の例</div>
  </div>
</div>

---
layout: center
---

# みんな違う機種を使っているのにすごい😯

---
layout: center
class: text-center
---

# そんなの当たり前やん
# そう思った方、正解です🥰

---
layout: center
class: text-center
---

## なぜなら
# 皆が洗濯機の<span class="italic underline font-bold text-sky-400">インターフェース</span>を知っているから

---
layout: center
---

# インターフェースとは概念を言語化したもの

---
layout: center
---

# 洗濯機の場合

<div class="grid grid-cols-2">
  <div>
    <ol>
      <li>服を入れられる</li>
      <li>洗剤・柔軟剤がセットできる</li>
      <li>洗濯を開始できる</li>
    </ol>
    <div class="mt-5"><mdi-arrow-right />この操作ができれば洗濯機と言える</div>
  </div>
  <div>
    <div class="text-sm opacity-60">洗濯機の概念をJavaのインターフェースに表したイメージ</div>
  
```java
public interface WashingMachine {
  void add(Wear wear);
  void setDetergent(Detergent detergent);
  Array<Wear> wash();
}
```

  </div>
</div>

---
layout: center
---

# クラス＝設計図

---
layout: center
---

# インターフェース＝概念

---

# つまり、この世に洗濯機クラスは存在しない

<div class="grid grid-cols-2 gap-6 h-4/5 mt-12 p-4">
  <div>
    <h4>❌洗濯機という製品の設計図は存在しない</h4>

```java {all|none}
public class WashingMachine {
  private Array<Wear> wears;
  void add(Wear wear) {
    // 服を洗濯槽に追加
  }
  void setDetergent(Detergent detergent) {
    // 洗剤を投下
  }
  Array<Wear> wash() {
    // 洗濯開始
    this.wears.forEach(w => w.dart = false);
    return this.wears;
  }
}
```

  </div>
  <div>
    <h4>⭕洗濯機を実装したESW114の設計図はある</h4>
  
```java {none|1-5|7-12}
public interface WashingMachine {
  void add(Wear wear);
  void setDetergent(Detergent detergent);
  Array<Wear> wash();
}

// 洗濯機の概念を実装した家電ESW114
public class ESW114 implements WashingMachine {
  void add(Wear wear) { }
  void setDetergent(Detergent detergent) { }
  Array<Wear> wash() { }
}

```

  </div>
</div>

---
layout: center
class: text-center
---

# この世はインターフェースだらけ
意識していないだけでほとんどのモノがインターフェースを実装している

---
layout: center
class: text-center
---

# じゃあ、抽象クラスは🤔?

---

# 抽象クラスはなんなのかというと
姉妹製品の基礎部分のようなイメージ (ほぼ同じ製品だが、左の製品はスマートフォンアプリに対応している)

<div class="p-4 h-4/5">
  <img src="/ES-GW11F_ES-GV10F.png" class="h-full mx-auto" />
</div>

---

# ❌抽象クラスを使わない場合

<div class="grid grid-cols-2 gap-6 h-4/5 p-4">
  <div>
    <h4>ES-GW11F</h4>

```java {all|8-20|10-12|2-7}
public class ESGW11F implements WashingMachine {
  void add(Wear wear) { 
    this.tank.push(wear); 
  }
  void setDetergent(Detergent detergent) { 
    this.tank.setDetergent(detergent);
  }
  Array<Wear> wash() {
    try {
      if (this.wears.weight >= 11) {
        throw new Exception("重量オーバー：11kg越え");
      }
      this.tank.hydration();
      this.tank.role();
      this.tank.dehydration();
      this.app.notice(Status.FINISH);
    } catch (Exception ex) {
      this.app.notice(Status.ERROR, ex);
    }
  }
}
```

  </div>
  <div>
    <h4>ES-GV10F</h4>
  
```java {none|8-16|9-11|2-7}
public class ESGV10F implements WashingMachine {
  void add(Wear wear) { 
    this.tank.push(wear); 
  }
  void setDetergent(Detergent detergent) { 
    this.tank.setDetergent(detergent);
  }
  Array<Wear> wash() {
    if (this.wears.weight >= 10) {
      throw new Exception("重量オーバー：10kg越え");
    }
    this.tank.hydration();
    this.tank.role();
    this.tank.dehydration();
  }
}
```

  <div v-click class="mt-5 text-2xl">
    <mdi-arrow-right />同じであるべきパーツが冗長な記述に
  </div>
  </div>
</div>

---

# ⭕抽象クラスを使う場合

<div class="grid grid-cols-2 gap-6 h-4/5 p-4">
  <div>
    <h4>同じ部分は抽象クラスで実装</h4>

```java {all|2-7|8}
abstract class ESGSeries implements Washi... {
  void add(Wear wear) { 
    this.tank.push(wear); 
  }
  void setDetergent(Detergent detergent) { 
    this.tank.setDetergent(detergent);
  }
  abstract Array<Wear> wash(); // 製品側で実装させる
}
```

```java {none|all}
public class ESGV10F extends ESGSeries {
  @override
  Array<Wear> wash() {
    if (this.wears.weight >= 10) {
      throw new Exception("重量オーバー：10kg越え");
    }
    this.tank.hydration();
    this.tank.role();
    this.tank.dehydration();
  }
}
```

  </div>
  <div>
    <h4>⭕同じ仕組みは共通化</h4>
  
```java {none|all}
public class ESGW11F extends ESGSeries {
  @override
  Array<Wear> wash() {
    try {
      if (this.wears.weight >= 11) {
        throw new Exception("重量オーバー：11kg越え");
      }
      this.tank.hydration();
      this.tank.role();
      this.tank.dehydration();
      // 洗い終わるとアプリに通知
      this.app.notice(Status.FINISH);
    } catch (Exception ex) {
      // エラーもアプリに通知
      this.app.notice(Status.ERROR, ex);
    }
  }
}

```

  </div>
</div>
<arrow x1="270" y1="300" x2="230" y2="370" class="text-sky-400"></arrow>
<arrow x1="300" y1="280" x2="540" y2="210" class="text-sky-400"></arrow>

---

<the-agenda :step="3" />

---
layout: center
---

# 弊社でパソコンとUSBマウスを製造することになったとする

---
layout: center
---

# パソコンとUSBマウスを例にモデリングしてみる

---
layout: center
class: text-center
---

# USB Mouse is Class
最高に蜜結合なパターン

---

# USBマウスがクラスだった場合

<div class="grid grid-cols-2 gap-4 h-3/5 items-center px-10">
  <div>
    <div class="text-sm opacity-60">PCクラス</div>

```java {all|3-6}
public class PC {
  private CLMouse usbPort1;
  public void setUSBPort1(CLMouse usb) {
    usb.install(this);
    this.usbPort1 = usb;
  }
}
```

  </div>
  <div>
    <div class="text-sm opacity-60">CLMouseクラス</div>

```java
public class CLMouse {
  public void install(PC pc) { 
    pc.setMouse(this);
  }
}
```

  </div>
</div>
<div class="px-10 mt-4">
  ポイント
  <ul>
    <li v-click class="text-green-400">PCクラスはCLMouseクラスを受け取る</li>
  </ul>
</div>
<arrow v-after x1="530" y1="220" x2="400" y2="230" class="text-green-400"></arrow>

---

# CLMouseがクラスだった場合

<div class="grid grid-cols-2 gap-4 px-10">
  <div>
    <h3>解決したこと</h3>
    <div class="h-4/5 grid items-center">
      <div>
        <ul>
          <v-list-item icon="✅">CLMouseの実装</v-list-item>
        </ul>

```java
var pc = new PC();

// ⭕CLMouseの利用
CLMouse mouse = new CLMouse();
pc.setUSBPort1(mouse);
```

  </div>
  </div>
  </div>
  <div>
    <h3>課題</h3>
    <ul>
      <v-list-item v-click icon="😯">このマウスしか使えないUSBポートになっちゃった</v-list-item>
      <v-list-item v-click icon="🤔" class="mt-2">USBメモリを使いたかったらどうするの？

```java
var pc = new PC();

// ❌型の不一致で他アクセサリは使えない
USBMemory memory = new USBMemory();
pc.setUSBPort1(memory); // エラー
```

  </v-list-item>
        <v-list-item v-click icon="🤔" class="mt-2">
          他のUSBマウスすら使えない

```java
var pc = new PC();

// ❌型の不一致で他マウスは使えない
ElecomMouse mouse = new ElecomMouse();
pc.setUSBPort1(mouse); // エラー
```

  </v-list-item>
    </ul>
  </div>
</div>

---
layout: center
class: text-center
---

# 💩こんなPC誰も使わない💩
設計ができない日本のSEはこれを量産しています

---
layout: center
class: text-center
---

# USB is Class
継承を利用するパターン

---

# USBクラスを継承する場合

<div class="grid grid-cols-2 gap-4">
  <div>
    <div class="text-sm opacity-60">PCクラス</div>

```java
public class PC {
  private USB usbPort1;
  public void setUSBPort1(USB usb) {
    usb.install(this);
    this.usbPort1 = usb;
  }
}
```

<div class="text-sm opacity-60">USBクラス</div>

```java
public class USB {
  public void install(PC pc) { }
}
```

  <div class="mt-4">
    ポイント
    <ul>
      <li v-click class="text-green-400">PCクラスはUSBクラスを受け取る</li>
      <arrow v-after x1="210" y1="290" x2="270" y2="190" class="text-green-400"></arrow>
      <li v-click class="text-blue-400">各アクセサリクラスはUSBクラスを継承</li>
      <arrow v-after x1="220" y1="290" x2="530" y2="150" class="text-blue-400 z-10"></arrow>
      <arrow v-after x1="230" y1="300" x2="530" y2="290" class="text-blue-400 z-10"></arrow>
    </ul>
  </div>
  </div>
  <div>
    <div class="text-sm opacity-60">CLMouseクラス</div>

```java
public class CLMouse extends USB {
  @override
  public void install(PC pc) { 
    pc.setMouse(this); // マウスに設定
  }
}
```

<div class="text-sm opacity-60">USBメモリクラス</div>

```java
public class USBMemory extends USB {
  @override
  public void install(PC pc) { 
    pc.setStorage(this); // ストレージに設定
  }
}
```

  <div class="mt-4 text-xl opacity-90">
    <mdi-arrow-right /><strong class="text-green-400 text-3xl">PC</strong>と<strong class="text-blue-400 text-3xl">CLMouse</strong>の<strong class="text-rose-400 text-3xl">直接的関係</strong>を排除
  </div>
  </div>
</div>


---

# USBクラスを継承する場合

<div class="grid grid-cols-2 gap-4">
  <div>
    <h3>解決したこと</h3>
    <ul>
      <v-list-item icon="✅">USBマウスの実装</v-list-item>
      <v-list-item icon="✅">USBを継承したクラスなら何でも使えるように</v-list-item>
    </ul>

```java {all|3-5|7-9|all}
PC pc = new PC();

// ⭕USBマウスが使える
CLMouse mouse = new CLMouse();
pc.setUSBPort1(mouse);

// ⭕USBメモリも使える
USBMemory memory = new USBMemory();
pc.setUSBPort1(memory);
```
  
  </div>
  <div>
    <h3>課題</h3>
    <ul>
      <v-list-item v-click icon="😯">installのオーバーライドを忘れるとバグを生む

```java
public class CLMouse extends USB {
  // ❌コメントアウトしてもエラーにならない
  /** @override
  public void install(PC pc) { 
    pc.setMouse(this); // マウスに設定
  } */
}
```

  </v-list-item>
  <v-list-item v-click icon="🤔">USBインスタンスはそのまま使われてもいいの？

```java
PC pc = new PC();

// ❌何も機能しないUSBをそのまま使えてしまう
USB usb = new USB();
pc.setUSBPort1(usb);
```
  
  </v-list-item>
    </ul>
  </div>
</div>

---
layout: center
class: text-center
---

# USB is <span class="underline">Abstract</span> Class
抽象クラスを利用するパターン

---

# USBが抽象クラスだった場合

<div class="grid grid-cols-2 gap-4">
  <div>
    <div class="text-sm opacity-60">PCクラス</div>

```java
public class PC {
  private USB usbPort1;
  public void setUSBPort1(USB usb) {
    usb.install(this);
    this.usbPort1 = usb;
  }
}
```

<div class="text-sm opacity-60">USBクラス</div>

```java
public abstract class USB {
  public abstract void install(PC pc);
}
```

  <div class="mt-4">
    ポイント
    <ul>
      <li v-click class="text-green-400">PCクラスはUSBクラスを受け取る</li>
      <arrow v-after x1="240" y1="290" x2="270" y2="190" class="text-green-400"></arrow>
      <li v-click class="text-blue-400">各アクセサリクラスはUSBクラスを継承</li>
      <arrow v-after x1="250" y1="290" x2="530" y2="150" class="text-blue-400 z-10"></arrow>
      <arrow v-after x1="260" y1="300" x2="530" y2="290" class="text-blue-400 z-10"></arrow>
      <li v-click class="text-yellow-200">installメソッドを抽象化</li>
    </ul>
  </div>
  </div>
  <div>
    <div class="text-sm opacity-60">USBマウスクラス</div>

```java
public class CLMouse extends USB {
  @override
  public void install(PC pc) { 
    pc.setMouse(this); // マウスに設定
  }
}
```

<div class="text-sm opacity-60">USBメモリクラス</div>

```java
public class USBMemory extends USB {
  @override
  public void install(PC pc) { 
    pc.setStorage(this); // ストレージに設定
  }
}
```

  </div>
</div>

---

# USBが抽象クラスだった場合

<div class="grid grid-cols-2 gap-4">
  <div>
    <h3>解決したこと</h3>
    <ul>
      <v-list-item icon="✅">USBマウスの実装</v-list-item>
      <v-list-item icon="✅">USBを継承したクラスなら何でも使えるように</v-list-item>
      <v-list-item icon="✅">
        installのオーバーライド忘れを回避

```java
public class CLMouse extends USB {
  // ⭕コメントアウトするとエラーとして検出
  /** @override
  public void install(PC pc) { 
    pc.setMouse(this); // マウスに設定
  } */
}
```
  
  </v-list-item>
      <v-list-item icon="✅">
        USBインスタンスがそのまま使われなくなる

```java
// ⭕USBがインスタンス化できなくなる
var usb = new USB(); // エラー
```
  
  </v-list-item>
    </ul>

  
  </div>
  <div>
    <h3>課題</h3>
    <ul>
      <v-list-item v-click icon="🤔">別の型(e.g Bluetooth型)として扱えない

```java
public class PC {
  private USB usbPort1;
  public void setUSBPort1(USB usb) {
    usb.install(this);
    this.usbPort1 = usb;
  }
  // Bluetoothペアリング機能を追加
  public void pairing(Bluetooth device) {
    device.pairing(this);
  }
}
```
    
```java
// ❌Bluetoothデバイスとして扱えない
public class CLMouse extends USB { }

// ❌USBデバイスとして扱えない
public class CLMouse extends Bluetooth { }
```

  </v-list-item>
    </ul>
  </div>
</div>

---
layout: center
---

# USB is Interface

---

# USBがインターフェースだった場合

<div class="grid grid-cols-2 gap-4">
  <div>

<div class="text-sm opacity-60">USBインターフェース</div>

```java
public interface USB {
  void install(PC pc);
}
```

<div class="text-sm opacity-60">Bluetoothインターフェース</div>

```java
public interface Bluetooth {
  void pairing(PC pc);
}
```
  <div class="mt-4">
      ポイント
      <ul>
        <li v-click class="text-green-400">PCクラスはUSBインターフェースを受け取る</li>
        <arrow v-after x1="250" y1="135" x2="540" y2="180" class="text-green-400 z-10"></arrow>
        <li v-click class="text-blue-400">CLMouseクラスはUSBインターフェースを実装</li>
        <arrow v-after x1="250" y1="140" x2="480" y2="300" class="text-blue-400 z-10"></arrow>
        <li v-click class="text-lime-400">PCクラスはBluetoothインターフェースを受け取る</li>
        <arrow v-after x1="280" y1="235" x2="530" y2="250" class="text-lime-400 z-10"></arrow>
        <li v-click class="text-sky-400">CLMouseクラスはBluetoothインターフェースを実装</li>
        <arrow v-after x1="280" y1="240" x2="480" y2="350" class="text-sky-400 z-10"></arrow>
      </ul>
    </div>
  </div>
  <div>
    <div class="text-sm opacity-60">PCクラス</div>

```java
public class PC {
  private USB usbPort1;
  public void setUSBPort1(USB usb) {
    usb.install(this);
    this.usbPort1 = usb;
  }
  public void pairing(Bluetooth device) {
    device.pairing(this);
  }
}
```

  <div class="text-sm opacity-60">CLMouseクラス</div>

```java
public class CLMouse implements USB, Bluetooth {
  @override
  public void install(PC pc) { 
    pc.setMouse(this); // マウスに設定
  }
  @override
  public void pairing(Bluetooth device) {
    device.setMouse(this); // マウスに設定
  }
}
```

  </div>
</div>

---

# USBがインターフェースだった場合

<div class="grid grid-cols-2 gap-4">
  <div>
    <h3>解決したこと</h3>
    <ul>
      <v-list-item icon="✅">USBマウスの実装</v-list-item>
      <v-list-item icon="✅">USBを継承したクラスなら何でも使えるように</v-list-item>
      <v-list-item icon="✅">installのオーバーライド忘れを回避</v-list-item>
      <v-list-item icon="✅">USBインスタンスがそのまま使われなくなる</v-list-item>
      <v-list-item icon="✅">様々な型として扱うことが可能に
   
```java {all|5|6|all}
PC pc = new PC();
CLMouse mouse = new CLMouse();

// ⭕USB、Bluetoothどちらの型としても扱える
pc.setUSBPort1(mouse);
pc.pairing(mouse);
```

  </v-list-item>
    </ul>
  </div>
  <div>
    <h3>課題</h3>
    <ul>
      <v-list-item v-click icon="🤔">初学者にとって難しい</v-list-item>
      <v-list-item v-click icon="🤔">自分で概念を見つける必要がある</v-list-item>
      <v-list-item v-click icon="🥰">理解できれば保守性の高いコードが記述可能</v-list-item>
    </ul>
  </div>
</div>

---

<the-agenda :step="4" />

---

# 互換性が不要なアプリでは必要ない？

<div class="grid place-content-center h-4/5">
  <div class="flex items-center text-2xl">
    🥸<v-speech-bubble class="ml-8">うちは互換性が必要ないアプリやからインターフェースなんていらんで</v-speech-bubble>
  </div>
  <div v-click class="mt-4 text-2xl">
    <mdi-arrow-right /> 実際の動作に互換性が不要でも、テストのスタブやモックに使えます。
  </div>
</div>

---

# テストのスタブ・モックに使うケース

例：モバイル端末からWEB API経由で花火を打ち出せるアプリを作るとします

<div class="grid grid-cols-7 h-3/5 items-center justify-items-center">
  <mdi-cellphone-wireless class="text-5xl" />
  <mdi-arrow-right />
  <mdi-weather-cloudy class="text-5xl" />
  <mdi-arrow-right />
  <mdi-server class="text-5xl" :class="{'text-green-400': $slidev.nav.clicks === 1}" />
  <mdi-arrow-right />
  <div class="grid h-3/5">
    <mdi-white-balance-sunny class="text-5xl" />
    <mdi-floor-lamp-torchiere-variant class="text-5xl" />
  </div>
</div>
<div class="grid grid-cols-7 items-center justify-items-center">
  <div>モバイル端末</div>
  <div></div>
  <div>インターネット</div>
  <div></div>
  <div :class="{'text-green-400': $slidev.nav.clicks === 1}">サーバー</div>
  <div></div>
  <div>花火台</div>
</div>

<div v-click class="mt-8 text-3xl text-green-400">サーバーの実装を例に考えてみます</div>
<arrow v-after x1="530" y1="350" x2="580" y2="300" class="text-green-400" width="3"></arrow>

---

# ❌外部依存関係を直接参照しているパターン

<div class="grid grid-cols-2 gap-4 items-center">
  <div>
    <ul>
      <li>
        HTTPクライアントを内部でインスタンス化
        <ul>
          <li>必ずHTTP通信が行われる</li>
          <li>どんな通信内容かテストしにくい</li>
          <li>サーバーがダウンしていたら？</li>
          <li>逆にサーバーがダウンしている時のテストは？</li>
        </ul>
      </li>
    </ul>
  </div>
  <div>

```java {all|4|6-7|all}
class FireUseCase {
  public FireResult fire(FireOptions options) {
    try {
      HTTPClient client = new HTTPClient();
      String data = JSON.Marshal(options);
      Response response = 
        client.post("https://queue.fire-flower.com", data);
      FireResult result = new FireResult();
      result.setSuccess(response.Body["success"]);
      result.setCost(response.Body["cost"]);
      return result;
    } catch (Exception ex) {
      FireResult result = new FireResult();
      result.setMessage("花火の発射に失敗しました。");
      return result;
    }
  } 
}
```

  </div>
</div>
<div v-click class="mt-2 text-2xl">
  テストする度に1発何十万円の花火が発射されます😇
</div>

---

# フェイクパターン

例：モバイル端末からWEB API経由で花火を打ち出せるアプリを作るとします

<div class="grid grid-cols-2 gap-3 h-4/5 items-center">
  <div>
    <ul>
      <li>結合テストで利用</li>
      <li>接続先を変えて実現 <span class="opacity-60">(この例ではダミーの花火台と通信)</span></li>
      <li>外部の影響を受けやすい</li>
      <li>初期化時に接続先を注入する</li>
      <div class="text-sm opacity-60 mt-3">接続先を注入する例</div>

```java {all|3-5,9}
class FireUseCase {
  private String endpoint;
  public FireUseCase(String endpoint) {
    this.endpoint = endpoint;
  }
  public FireResult fire(FireOptions options) {
      HTTPClient client = new HTTPClient();
      String data = JSON.Marshal(options);
      Response response = client.post(this.endpoint, data);
  }
}
```

  </ul>
  </div>
  <div class="grid grid-cols-3 items-center justify-items-center">
    <mdi-server class="text-5xl" />
    <mdi-arrow-right />
    <div class="grid justify-items-center gap-4">
      <mdi-white-balance-sunny class="text-5xl" />
      <mdi-floor-lamp-torchiere-variant class="text-5xl" />
    </div>
    <div>サーバー</div>
    <div></div>
    <div class="mt-4">ダミーの花火台</div>
  </div>
</div>

---

# スタブ・モックパターン

例：モバイル端末からWEB API経由で花火を打ち出せるアプリを作るとします

<div class="grid grid-cols-2 gap-3 h-4/5 items-center">
  <div>
    <ul>
      <li>単体テストで利用</li>
      <li>任意の動作をするオブジェクトを注入して実現</li>
      <li>外部と通信させない <span class="opacity-60">(この例では例外が発生する)</span></li>
      <li>初期化時にオブジェクトを注入する</li>
  </ul>
  </div>
  <div>
    <div class="grid items-center justify-items-center">
      <mdi-server class="text-5xl" />
      <div class="mt-4">サーバーは外部と通信しない</div>
    </div>
  </div>
  <div>
    <div class="text-sm opacity-60 mt-3">接続先を注入する例</div>

```java {all|4,6,10}
class FireUseCase {
  private IHTTPClient http;
  private String endpoint;
  public FireUseCase(IHTTPClient http, String endpoint) {
    this.endpoint = endpoint;
    this.http = http;
  }
  public FireResult fire(FireOptions options) {
    String data = JSON.Marshal(options);
    this.http.post(this.endpoint, data); // 例外が発生する
  }
}
```
  </div>
  <div>
    <div class="text-sm opacity-60 mt-3">強制的に例外を発生させるHTTPClientの例</div>

```java
class ExceptionClient implements IHTTPClient {
  @override
  public Response post(String url, Object data) {
    throw new Exception("単体テスト用例外");
  }
}
```
  </div>
</div>

---
layout: center
class: text-center
---

# スタブやモックを利用することで<br>効率的なテストが実施可能

---
layout: center
---

# 神クラスの降臨を回避するパターン

---

# 神クラスの例

<div class="grid grid-cols-2">
  <div>

```java
public class IPhone {
  private String type; // iPhone 13 等
  public IPhone(String type) {
    this.type = type;
  }
  public void unlock() {
    switch(this.type) {
      case "iPhone 3G":
      case "iPhone 4":
      case "iPhone 4S":
        // パスコードでロック解除
        break;
      case "iPhone 5":
      case "iPhone 5S":
      case "iPhone 5C":
      ...
        // Touch IDでロック解除
        break;
      case "iPhone X":
        // Face IDでロック解除
    }
  }
```
  </div>
  <div>

```java
  public void applePay() {
    switch(this.type) {
      case "iPhone 3G":
      case "iPhone 4":
      case "iPhone 4S":
      case "iPhone 5":
      case "iPhone 5S":
      case "iPhone 5C":
        throw new Exception("非対応端末です");
        break;
      case "iPhone 6":
      case "iPhone 6 Plus":
        // Apple Payの処理
    }
  }
}
```
  <div class="mt-8 ml-4 text-2xl">
    <mdi-arrow-right />iPhoneを知り尽くした神降臨
  </div>
  </div>
</div>

---

# 神クラスは何がダメなのか

<div class="grid grid-cols-2 items-center h-4/5">
  <div>
    <ul>
      <li>
        単純に分類しやすく皆が追加しやすい
        <ul>
          <li>聞こえはいいが、それ故に永遠に肥大化する</li>
          <li>肥大化し続けた結果、誰も触れられないコードに</li>
          <li>触らぬ神に祟りなし、神クラスとして崇められる</li>
        </ul>
      </li>
      <li>
        同じようなswitch文が量産される
        <ul>
          <li>一部追加し忘れただけで重大なバグに</li>
          <li>追加し忘れを検知できないのも問題</li>
        </ul>
      </li>
      <li>
        これがiPhoneではなく何百と種類のあるものだったら・・・
        <ul>
          <li>間違いなく崩壊する</li>
        </ul>
      </li>
    </ul>
  </div>
  <div>

```java
public class God {
  public void wishComeTrue() {
    // ここに数兆行のコードが記述される・・・
  }
}
```
  </div>
</div>

---

# 神クラスを回避するには

<div class="grid grid-cols-2 gap-4 items-center h-4/5">
  <div>

```java
public class IPhone13 implements IPhone {
  public void unlock() {
    // Face IDでロック解除
  }
}
```
```java
public class IPhoneFactory {
  public static IPhone build(String type) {
    switch(type) {
      case "iPhone 3G":
        return new IPhone3G();
      case "iPhone 5":
        return new IPhone5();
      // 以降続く
    }
  }
}
```
  </div>
  <div class="ml-8">
    <ul>
      <li>
        クラス名は厳密にする
        <ul>
          <li>曖昧な名前程神クラスになりやすい</li>
          <li>utilって見たら神クラスだと思え</li>
        </ul>
      </li>
      <li>
        クラス単体の責務を最小にする
        <ul>
          <li>長文って読みたくないでしょ</li>
          <li>長いコードがあったら設計ミスを疑え</li>
        </ul>
      </li>
      <li>
        ファクトリーメソッドなどでswitch文は1か所に
        <ul>
          <li>繰り返される条件分岐を人間は理解できない</li>
          <li>同じswitch文が出てきたら設計を疑え</li>
        </ul>
      </li>
    </ul>
  </div>
</div>

---
layout: center
---

# さいごに

---
class: p-0
---

<div class="text-6xl">ここまでの抽象クラスやインターフェースについての説明でそれらの重要性が理解できたでしょうか。このスライドのようにデザインが悪いものは可読性が悪くなります。可読性が悪いものはミスがあっても見落とされやすく、また作業をする人間の精神的負担にも繋がります。デザインに機能はありませんが、デザインが重要だというのはこのスライドを見れば一目瞭然ですね。</div>

---
layout: center
---

# ✨デザイン = 重要✨

---
layout: center
---

# インターフェース = プログラム設計(デザイン)

---
layout: center
---

# 🥰インターフェース = 重要🥰

---
layout: center
---

# Thanks