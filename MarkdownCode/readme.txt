在编写代码的时候，我们会通过注释对代码进行说明。但是有的时候想表达的内容完全没法用文字表述，让人有画一幅图片插入到代码里的冲动。
但是每次用ASCII码试图拼出一副图片都是很困难的事情。（；´д｀）ゞ
如果代码里也可以写markdown就好了。
比如把特殊标记过的注释，类似 "//md: "后面的内容解析为markdown
甚至可以做一些扩展，通过锚点的方式以支持代码导航，点击链接从一个函数跳转到另一个函数等等
那么图片怎么办？
可以用base64注释一下附在文件最后，然后通过标识符的方式引用图片。

We use comments to explain the code when coding. But sometime what we want to express is just ..... beyondwords!! making me want to insert a picture to the code to illustrate.
But every time I tried to "make" a picture by ASCII code, It always cost me a long time.（；´д｀）ゞ
What if we can use markdown in the code....
such as parsing the content after a special comment like "//md: " as markdown
even more, we can extend the markdown to support code navigation, like click the link and navigate to another function.....
Then how to deal with the picture?
base 64 and comment the raw data and attach it to the end of file, and give it an ID. then use the picture by ID.