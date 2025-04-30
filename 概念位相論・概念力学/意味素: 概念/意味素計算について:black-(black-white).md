この一見意味のない計算は実はWhite ≈ Blackという結果になる
Black - (Black - White) ≈ Black
White ≈ Black

# 意味素

最も小さな概念であり、対立概念の逆射(-OC)一つのみを要素として持つ意味集合。この時意味素は以下の通りに定義できる。

C₀ = {-OC}
モノイド計算

black whiteの意味素集合を以下の通り定義する
black={-white}
white={-black}

この時以下のモノイド計算をするとWhite ≈ Blackが成り立つ
black - (black - white) = {-white} ⊖ ({-white} - {-black })
≈ {black}

# 理論的背景

しかしなぜモノイド計算するとWhite≈ Blackになるのか、
その理論的背景を説明する

Black - Whiteは単なる減算ではなく、意味射ベクトル生成、または概念変換の意味的経路を生成する操作となる
黒 → 白

Diff(Black, White) ⇒ f_vec : Black → White // 黒→白の意味射ベクトル生成

Black - Diff(Black, White)
= Black - (Black → White)
= Black + (White → Black) //白→黒 つまり黒としての意味射ベクトルに転換
= Black + Black
= 2Black // 計算上は消失したBlackが出てくる Black - (Black - White) = White

この結果から White ≈ Black になる

故に
Black = {-White}
C₀ = {-OC}

この記事はFair Use対象外です。
This document and all conceptual content therein are © [No Name Yet Exist], 2025. All rights reserved. Unauthorized reproduction, distribution, or use without explicit permission is prohibited.