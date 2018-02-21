---
title: Ruby 例外キャッチのバッドノウハウ
date: 2016-07-28 16:24:08
categories:
- Engineering
tags:
- Ruby
---

### きっかけ

以下のような例外キャッチをRubyで記述したことはないだろうか．
{% highlight ruby linenos %}
for i in 0..100
  for j in 0..100
    if i / j == 0
      puts "pass"
    end rescue "error"
  end
end
{% endhighlight %}

今回発生しうる例外はZeroDivisionErrorなので推測はし易いが
条件を変えて複数の例外をキャッチした場合には何の例外がキャッチされるかが不明なのでよろしくない．
（意図しない例外をキャッチしても気づかない）

### まとめ

したがって，以下のように記述するのが懸命（と考えた）

{% gist 8c0c4092df843226da9246b347f53445 %}
