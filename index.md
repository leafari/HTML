## 您好，这里是 winery926's GitHub Pages

没有什么目的
### 读书笔记

对称加密

简单来说就是通信双方通过同一个密钥对信息进行加密与解密的一种方法。这种方法可以有效地将信息从可读形式转换成乱码，例如凯撒密码。
凯撒密码将原文中每一个字母转换成原来字母在字母表中位置之后某个位置的字母，其后移的步长就为其密钥。比如当发起方想要发送“ABCDE”这一串字母，并规定其后移的步长为1，这样的话，经过加密的信息就为“BCDEF”。接收方在接收到“BCDEF”后，只需知道之前商定好的密钥，也就是步长=1，再对密文中的每一个字母进行前移一步的操作(加密操作的逆过程)，就可得到原文“ABCDE”。这样其他人就算拦截或窃取到密文“BCDEF”，也没办法得知原文为“ABCDE”。
但是这种方法存在一个问题，通信双方都需要知道密钥是什么，这就需要通信双方在进行私密通信之前商定好一个密钥并且共享密钥，要保证这个过程的安全，通信双方需要建立一个安全加密连接，但是没有密钥的话，又不能建立安全加密连接，这样就产生了矛盾。公钥-私钥加密则可以较好的解决这个矛盾。


公钥-私钥加密（非对称加密）

假设你有两个密钥，这里称为密钥A与密钥B。两个密钥之间的关系是这样的：用密钥A加密的信息只能用密钥B进行解密，用密钥B加密的信息只能用密钥A进行解密，当然这里要保证其他人不能通过密钥A猜出密钥B是什么，也不能通过密钥B猜出密钥A是什么。
现在你可以选择密钥A与密钥B中的其中一个作为公钥，另外一个作为私钥。公钥你完全可以把它公开在任何地方，所有人都可以知道你所拥有的公钥是什么。而私钥则是你必须要完全保密的，必须要确保只有你知道你的私钥是什么。        
同时你需要进行私密通信的对方也需要有这样的一个密钥对。这里不要求对方的密钥对与你自己的密钥对有任何的联系。所以你和对方不需要在进行私密通信之前有任何的交流。
如果你想向对方发送信息，并且不想让其他人知道，你需要知道对方的公钥，将你想要发送的信息用对方的公钥进行加密，并发送给对方。对方收到消息后，只需要对加密的信息用自己的私钥进行解密就可以得到你所发送的原文。在这个过程中，就算其他人拦截到你发送的信息，但因为是用对方公钥进行加密的，只有用对方的私钥才能进行解密，而对方的私钥只有对方知道，所以其他人并不能读取你发送的信息。
对方想给你发送信息也是同样的一个过程。所以这样可以很好地弥补对称加密的一个不足。
除此之外，你还可以把你想要发送给对方的信息用先自己的私钥进行加密，然后用对方的公钥进行加密，再发送出去。先用自己的私钥进行加密的意义在于这样对方就可以知道这条消息确实是你发送过来的，并不是他人恶意冒充的。因为你的公钥是公开的，能用你的公钥进行解密就意味着这条消息一定是用你的私钥加密的，而只有你才知道你自己的私钥是什么。数字签名的大致原理就是这样。
这种密钥对的实现主要是依靠数学理论与计算机技术的发展，例如RSA加密。简单来说这种加密方式用两个很大的质数作为私钥，用两个大质数的乘积作为公钥的一部分。因为要对一个很大的数分解质因数是很困难的，即使用现代计算机进行分解也要花费很长的一段时间，这才保证了这种加密技术的可行性。


# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/winery926/HTML/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
