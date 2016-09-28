# UIStoryboard: Safer with Enums, Protocol Extensions and Generics
# 故事版：利用枚举，协议，泛型更加安全
## Because String literals are so yucky.
## 因为字符串总是那么令人讨厌

### Medium post
[UIStoryboard: Safer with Enums, Protocol Extensions and Generics](https://medium.com/p/7aad3883b44d/)
### 中文翻译地址
[UIStoryboard：和枚举、协议扩展、泛型一起使用更安全](http://swift.gg/2016/09/26/uistoryboard-safer-with-enums-protocol-extensions-and-generics/)

### tl;dr
Turn this:
原始代码：

````
let name = "News"

let storyboard = UIStoryboard(name: name, bundle: nil)

let identifier = "ArticleViewController"

let viewController = storyboard.instantiateViewControllerWithIdentifier(identifier) as! ArticleViewController

viewController.printHeadline()
````

Into this:
转换后的代码：

````
let storyboard = UIStoryboard.storyboard(.News)

let viewController = storyboard.instantiateViewController(ArticleViewController.self)

viewController.printHeadline()
````


