# HelloKotlin

## Foreword

首先，献上官方网址：[Kotlin][kotlin]，官方介绍它是**用于现代多平台应用的静态类型编程语言**，而且可以100%用于Java及安卓，这不2017-05-17的谷歌I/O大会上已正式宣布`Kotlin`为安卓官方语言，这不，[Android Studio 3.0预览版][as3_pre]已自带`Kotlin`插件，如果想要在线体验，那就点击这个[传送门][try_kotlin]吧。


## Introduce

Kotlin不同于Swift，它的野心更大，它的平台更广，如下图所示。

![Kotlin Build Applications For][kotlin_app_for]

怎么样，心动了吗，是不是觉得可以做全栈了？哈哈。

那么，为什么要选择Kotlin呢，官方给出了它的四大优点。

### 1. 简洁（Concise）

大幅度缩减样板代码。

E.g.

比如创建一个带有`getters`, `setters`, `equals()``, `hashCode()``, `toString()`` and `copy()`函数的`POJP`只需要一行代码即可。

``` kotlin
data class Customer(val name: String, val email: String, val company: String)
```

亦或者迭代一个链表用lambda表达式只需如下写法。

``` kotlin
val positiveNumbers = list.filter { it > 0 }
```

想要构造一个单例？只需创建一个`object`即可。

``` kotlin
object ThisIsASingleton {
    val companyName: String = "JetBrains"
}
```


### 2. 安全（Safe）

避免了蛋疼的空指针异常。

E.g.

曾经的*十亿美元错误*就是由空指针异常引起的，用Kotlin的话我们就可以避免它。

``` kotlin
var output: String
output = null   // Compilation error
```

Kotlin可以避免你犯空指针引起的错误。

``` kotlin
val name: String? = null    // Nullable type
println(name.length())      // Compilation error
```

如果你检查了这个类型是对的，编译器将会自动帮你转型。

``` kotlin
fun calculateTotal(obj: Any) {
    if (obj is Invoice)
        obj.calculateTotal()
}
```


### 3. 互用（Interoperable）

库可以在JVM、安卓及浏览器端可以互用。

E.g.

可以使用任何可以运行在JVM上的库，因为它具有100%的兼容性，包括支持SAM。

``` kotlin
import io.reactivex.Flowable
import io.reactivex.schedulers.Schedulers

Flowable
    .fromCallable {
        Thread.sleep(1000) //  imitate expensive computation
        "Done"
    }
    .subscribeOn(Schedulers.io())
    .observeOn(Schedulers.single())
    .subscribe(::println, Throwable::printStackTrace)
```

它的目标既可以是JVM也可以是JavaScript，你只需要用Kotlin写完代码，然后决定部署在哪即可。

``` kotlin
import kotlin.browser.window

fun onLoad() {
    window.document.body!!.innerHTML += "<br/>Hello, Kotlin!"
}
```


### 4. 工具友好（Tool-friendly）

可以选择任何Java的IDE或者用命令行编译。

E.g.

Kotlin语言可以在JetBrains提供的工具大放异彩。

![tooling0][tooling0]

![tooling1][tooling1]


## Learn Material

[Kotlin Github][kotlin_github]

[Kotlin官方Doc][kotlin_doc_eng]

[Kotlin官方Doc中文][kotlin_doc_cn]

[Kotlin官方Doc中文PDF][kotlin_doc_cn_pdf]

[Kotlin for Android Developers(有钱你就买吧)][kotlin_for_android_developers_eng]

[Kotlin for Android Developers中文][kotlin_for_android_developers_cn]

[Kotlin for Android Developers中文PDF][kotlin_for_android_developers_cn_pdf]


## Conclusion

Kotlin已经介绍完毕，之后就跟着我一起来学习它吧，我会把我所学到的都发不在[HelloKotlin][hello_kotlin]库中，喜欢的话点个star给柯基动力吧。

想进微信讨论群的话扫一下我微信，加我好友，注明“kotlin”即可，我会把你拉到群里。



[kotlin]: https://kotlinlang.org/
[as3_pre]: https://developer.android.com/studio/preview/index.html
[try_kotlin]: http://try.kotlinlang.org/
[kotlin_app_for]: https://github.com/Blankj/HelloKotlin/blob/master/art/kotlin_app_for.png
[tooling0]: https://github.com/Blankj/HelloKotlin/blob/master/art/tooling0.png
[tooling1]: https://github.com/Blankj/HelloKotlin/blob/master/art/tooling1.png
[kotlin_github]: https://github.com/JetBrains/kotlin
[kotlin_doc_eng]: http://kotlinlang.org/docs/
[kotlin_doc_cn]: https://www.gitbook.com/book/huanglizhuo/kotlin-in-chinese/details
[kotlin_doc_cn_pdf]: hhttps://github.com/Blankj/HelloKotlin/raw/master/art/kotlin_doc_cn.pdf
[kotlin_for_android_developers_eng]: https://leanpub.com/kotlin-for-android-developers
[kotlin_for_android_developers_cn]: https://github.com/wangjiegulu/kotlin-for-android-developers-zh
[kotlin_for_android_developers_cn_pdf]: https://github.com/Blankj/HelloKotlin/raw/master/art/kotlin_for_android_developers_cn.pdf
[hello_kotlin]: https://github.com/Blankj/HelloKotlin
