---
title: "FizzBuzz"
---
## FizzBuzzの仕様

FizzBuzzは、1から100までの数を順に出力するプログラムです。ただし、以下のルールに従います。

- 3で割り切れる数の場合は「Fizz」を出力
- 5で割り切れる数の場合は「Buzz」を出力
- 3と5の両方で割り切れる数の場合は「FizzBuzz」を出力
- それ以外の数の場合はその数を出力

## 要件

1. プログラムは、1から100までの数を順に処理する。
2. 各数に対して、以下の条件を判定する。
   - 数が3で割り切れる場合は、「Fizz」と出力する。
   - 数が5で割り切れる場合は、「Buzz」と出力する。
   - 数が3と5の両方で割り切れる場合は、「FizzBuzz」と出力する。
   - 上記のいずれの条件にも当てはまらない場合は、その数を出力する。
3. 出力は、改行またはスペースで区切られる。

## 例

出力の例は以下の通りです。

```stdout
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
```

## コード (How)

:::details

```php
<?php
function fizzBuzz($n) {
    if ($n % 15 === 0) {
        return "FizzBuzz";
    } elseif ($n % 3 === 0) {
        return "Fizz";
    } elseif ($n % 5 === 0) {
        return "Buzz";
    } else {
        return (string)$n;
    }
}

for ($i = 1; $i <= 100; $i++) {
    echo fizzBuzz($i) . PHP_EOL;
}
?>
```

:::

## テストコード (What)

:::details
テスト失敗時のメッセージも設定

```php
<?php
use PHPUnit\Framework\TestCase;

class FizzBuzzTest extends TestCase {
    public function testFizzBuzz() {
        $this->assertEquals("Fizz", fizzBuzz(3), "3の倍数でFizzを返すべきです");
        $this->assertEquals("Buzz", fizzBuzz(5), "5の倍数でBuzzを返すべきです");
        $this->assertEquals("FizzBuzz", fizzBuzz(15), "15の倍数でFizzBuzzを返すべきです");
        $this->assertEquals("2", fizzBuzz(2), "3の倍数でも5の倍数でもない数値はそのまま返すべきです");
    }
}
?>

```

:::

## コミットログ (Why)

:::details

```commit
コミットメッセージ: FizzBuzz関数の実装

PHPでFizzBuzzの基本的なロジックを実装しました。3で割り切れる数は"Fizz"、5で割り切れる数は"Buzz"、15で割り切れる数は"FizzBuzz"を返します。それ以外の数はその数自身を文字列として返します。

```

:::

## コードコメント (Why not)

:::details

```php
<?php
function fizzBuzz($n) {
    // 15で割り切れるかどうかを最初にチェックしています。
    // これは、3と5の両方で割り切れる数は15で割り切れるため、
    // より効率的なチェック方法です。
    if ($n % 15 === 0) {
        return "FizzBuzz";
    } elseif ($n % 3 === 0) {
        return "Fizz";
    } elseif ($n % 5 === 0) {
        return "Buzz";
    } else {
        return (string)$n;
    }
}
?>
```

:::
