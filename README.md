# 課題1
`The Art of Readable Code`の目的はコードを理解しやすくすることです。  
コードを理解しやすくなるために、自分のコードは他の人が最短期間で読みやすくように書いた方がいいです。  
コードは短くした方がいいですがコードを完全に理解するのにかかる時間を短くする方がもっと重要です。  
その本にはリーダブルコード活用方法を説明し、C++、Python、Java、JavaScript などの言語を使って多くの例で説明してあります。  

# 課題2

## 例：１  

以下のコードでは変数の名前を省略しています。  
省略する場合、変数の意味を理解するのに時間がかかります。   
変数には意味のある名前を付けるようにしましょう。  

悪い例
```java
    String pName;
    int pQnt;
    int pCat;
    double pPrice;
    double totalAmt;
```

名前に情報を詰め込むようにしてください。  

良い例
```java
    String productName;
    int productQuantity;
    int productCategory;
    double productPrice;
    double totalAmount;
```

## 例：２  

Javaプログラムを書く上で守るべき一般的な命名指針を導入します。  
以下のルールで命名することができます。  

良い例
| **識別子の種類** | **命名規則**       | **例**                     |
|------------|----------------|---------------------------|
| パッケージ      | 小文字            | com.example.demo          |
| クラス        | パスカルケース        | class Student, class StudentController |
| インターフェース   | パスカルケース        | interface Drawable, interface DrawShape                 |
| メソッド       | キャメルケース        | setName()                 |
| 変数         | キャメルケース        | String productName               |
| 定数         | すべて大文字とスネークケース | static final int MIN_VALUE                 |

## 例：３

foo(), myFun(), fun(), MyMethod()など意味がない名前を付けることはよくないです。  
以下のコードの関数の名前のように関数についての情報が伝わらない名前を付けないように気を付けましょう。   

悪い例
```java
    private static void display(String name) {
        System.out.printf("名前： %s", name);
    }
```

以下のコードを見るとその名前を表示する関数だとすぐに分かります。  
関数の名前を付けるときにも名前に情報を詰め込むことが大事です。  

良い例
```java
    private static void displayName(String name){
        System.out.printf("名前： %s", name);
    }
```

## 例：４
以下の例のboolean型変数の名前を読むと意味をはっきり理解できないです。  
適切に名前をつけないと、読み手によって解釈が異なり、誤解が生じる場合があります。

悪い例
```java
    boolean authenticated = true;
    boolean change = true;
    boolean eaten = true;
```

状態を意味するboolean型変数はis、has、canといったなど動詞から始めるべきです。

良い例
```java
    boolean isAuthenticated = true;
    boolean canChange = true;
    boolean hasEaten = true;
```
## 例：５

以下のコードは間違っていないですが読みにくいです。  
優れたコードを書くとき目に優しい見た目も大事です。  

悪い例
```java
public static void findMedianValue(int a,int b,int c)
  {

   if((a<b&&b<c)||(c<b&&b<a)) {
   System.out.println(b);}
        else if {((b<a&&a<c)||(c<a&&a<b))   System.out.println(a);
        }
 
          else{
             System.out.println(c);}
    }
```    

見た目が美しいコードの方が読みやすいです。  
インデントが整って適切に改行された美しいコードの方が読みやすいです。  

良い例
```java
    public static void findMedianValue(int a, int b, int c) {
        if ((a < b && b < c) || (c < b && b < a)) {
            System.out.println(b);
        } else if ((b < a && a < c) || (c < a && a < b)) {
            System.out.println(a);
        } else {
            System.out.println(c);
        }
    }
```

## 例：６

以下のコードの変数はバラバラになっていて整っていないため、読みにくいです。

悪い例
```java
    String shopName = "さくら";
    String productName = "Samsung Galaxy";
    String customerName = "Mike";
    String productCategory = "Phone";
    String productPrice = "1200000";
    String shopPhoneNumber = "09786829123";
    String customerPhoneNumber = "09786858121";
    String shopAddress = "Hledan";
    String customerAddress = "Sangchaung";
```

見た目が美しいコードを書くとき関連するコードをまとめてブロックにすることも重要です。  
文章と同様にコードも段落に分割するようにしてください。

良い例
```java
    String productName = "Samsung Galaxy";
    String productCategory = "Phone";
    String productPrice = "1200000";

    String customerName = "Mike";
    String customerPhoneNumber = "09786858121";
    String customerAddress = "Sangchaung";

    String shopName = "さくら";
    String shopPhoneNumber = "09786829123";
    String shopAddress = "Hledan";
```

## 例：７

以下のコードではコメントはいいですが関数の名前を見ると`display`だけ書いてなにを表示するか書いてありません。  
`良いコード > 悪いコード + 良いコメント`だから良いコメントより良いコードを書きましょう。  

悪い例
```java
    //名前を表示する
    private static void displayName(String name) {
        System.out.printf("名前： %s", name);
    }
```

良い例
```java
    private static void displayName(String name) {
        System.out.printf("名前： %s", name);
    }
```

## 例：８

コメントすべきことを知ることが大事です。  
コードからすぐに理解できることをコメントする必要がないです。  

悪い例
```java
    //すべての製品の名前を表示する
    System.out.println("すべての製品の名前を表示する");
    products.forEach(product -> System.out.printf("名前：%s", product.getName()));
```

本当に必要なコメントだけ書きましょう。

良い例
```java
    System.out.println("すべての製品の名前を表示する");
    products.forEach(product -> System.out.printf("名前：%s", product.getName()));
```

## 例：９

コメントをするとき今後やりたいこと、改善したいこと, 修正したいことをコメントすることができます。  

良い例
```java
    // TODO:ヘッダーのデザインを更新する
```

## 例：１０

以下のコードは間違ってはいないですがちょっと長いです。  

悪い例
```java
    String result = "";
    if (mark >= 50) {
        result = "おめでとうございます！合格です。";
    } else {
        result = "残念ですが不合格です！";
    }
```

上記のコードを短くするために三項演算子を使います。  
三項演算子を使う以下のコードはもっと短くて読みやすくて理解できます。  

良い例
```java
    String result = mark >= 50 ? "おめでとうございます！合格です。" : "残念ですが不合格です！";
```

## 例：１１

以下のコードでは三項演算子を使ってコードは短いですが読みにくいです。  
三項演算子はシンプルなコードなら使うことができますが以下の例のように簡単ではない複雑なコードなら使わない方がいいです。  

悪い例
```java
    public static void findMedianValue(int a, int b, int c) {
        System.out.println((a < b) ? (b < c) ? b : (a < c) ? c : a : (a < c) ? a : (b < c) ? c : b);
    }
```  

行数を短くするより読み手が理解するのにかかる時間を短くすることが大事です。  
上記の例を三項演算子を使わないで基本的なif~elseを使って実地しましょう。  

良い例
```java
    public static void findMedianValue(int a, int b, int c) {
        if ((a < b && b < c) || (c < b && b < a)) {
            System.out.println(b);
        } else if ((b < a && a < c) || (c < a && a < b)) {
            System.out.println(a);
        } else {
            System.out.println(c);
        }
    }
```  

## 例：１２

コードの表現が長くなるほど理解が難しくなります。  
巨大な式を分割することが必要です。  

悪い例
```java
    if (username == "admin" && password == "12345") {
        System.out.println("ログイン成功");
    }
    if (username != "admin" && password != "12345") {
        System.out.println("ログイン失敗");
    }
```

要約変数を用いて分割するとコードも短くて読みやすいです。

良い例
```java
    boolean isAuthenticated = username == "admin" && password == "12345";
    if (isAuthenticated) {
        System.out.println("ログイン成功");
    }
    if (!isAuthenticated) {
        System.out.println("ログイン失敗");
    }    
```

## 例：１３

以下のコードでの`mark`変数はグローバル変数です。その変数を一つの条件しか使いません。  
大きいプロジェクトならすべてのメンバー変数と、各メンバー変数を変更するメソッドをを追うのが大変です。  

悪い例
```java
    public static void methodName() {
        int mark;
        if (condition) {
            //mark変数を使用する
        }
        //ここからmark変数を使用しない
    }
```

`mark`変数を一つの条件しか使いませんから変数のスコープを縮めてメンバ変数をローカル変数に変更しましょう。  

良い例
```java
    public static void methodName() {
        if (condition) {
            int mark;
            //markを使用する
        }
        //ここからmarkを使用しない
    }
```

## 例：１４

以下の例で関数の名前を見るとなにをテストしているかすぐに分かりません。
その上変数の名前も似ているから期待値と実測値を混同してしまいます。  

悪い例
```java
    @Test
    void test() {
        int result1 = underTest.subtract(1, 12);
        int result2 = -11;
        assertThat(result1).isEqualTo(result2);
    }
```

テストコードも読みやすさが大切です。  
テストの関数の名前にも情報を詰め込むようにしましょう。  
変数名に"actual” や “expected” を付けましょう。  
これによって読みやすくなり、期待値と実測値もすぐ分かります。  

良い例
```java
    @Test
    void testMinus() {
        int actualResult = underTest.subtract(1, 12);
        int expectedResult = -11;
        assertThat(actualResult).isEqualTo(expectedResult);
    }
```
日本のプロジェクトではテストケースのメソッド名を日本語で書くこともあります。  
日本人と働くとき日本語が書かれていると読み手にとって何のテストしているのか、テストの正否がわかりやすいです。    

良い例
```java
    @Test
    void subtractionで1と12の減算結果が取得できる() {
        int actualResult = underTest.subtract(1, 12);
        int expectedResult = -11;
        assertThat(actualResult).isEqualTo(expectedResult);
    }
```
