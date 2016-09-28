# UIStoryboard: Safer with Enums, Protocol Extensions and Generics
# 故事版：利用枚举，协议，泛型更加安全
## Because String literals are so yucky.
## 因为字符串总是那么令人讨厌

### Medium post
### 帖子说明
[UIStoryboard: Safer with Enums, Protocol Extensions and Generics](https://medium.com/p/7aad3883b44d/)

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


