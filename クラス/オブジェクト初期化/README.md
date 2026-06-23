# オブジェクト初期化

2つの初期化方法の違い

```csharp
// ✅ コンストラクタ経由（private set でもOK）
var dorayaki = new Product(
    code: 98,
    name: "どら焼き",
    price: 210
);

// ❌ オブジェクト初期化子（private set だとエラー）
var dorayaki2 = new Product {
    Code = 98,
    Name = "どら焼き",
    Price = 210
};
```

{} の正体
オブジェクト初期化子はセッターを呼び出している。

```csharp
// この書き方は…
var profile = new UserProfile { Name = "田中" };

// 内部的にこう展開される
var profile = new UserProfile();
profile.Name = "田中";  // セッター呼び出し
```
