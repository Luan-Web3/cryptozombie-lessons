---
title: 放在一起
actions: ['checkAnswer', 'hints']
requireLogin: true
material:
  saveZombie: false
  zombieDeck:
    zombie:
      lesson: 6
    hideSliders: true
    answer: 1
---

恭喜啊少年，你已经成功编写了一个 Web3.js 前端界面来和你的智能合约交互

## 接下来的步骤

这节课的内容非常基础。我们想要给你展示和智能合约交互的核心内容，而并不想用太多的时间来教你完整实现。我们也不想花太多时间在HTML/CSS上，因为大部分人都已经知道了。

所以我们把一些实现略去了。这里是你要完整实现所需要完成的基本事项列表：

1. 为 `attack`, `changeName`, `changeDna` 以及 ERC721 函数 `transfer`, `ownerOf`, `balanceOf` 等实现前端函数。这些函数的实现将和我们讲过的 `send`交易的函数非常相似。

2. 实现一个“管理界面”，在那里你可以调用 `setKittyContractAddress`, `setLevelUpFee`, 以及 `withdraw`。再次，在前端这块没有什么特别的代码——这些实现之间将非常相似。你应该保证从部署合同时候相同的以太坊地址调用这些函数，因为他们都有`onlyOwner` 修饰符。

3. 在应用里我们还应该实现一些其他的界面：

  a. 一个僵尸页面，在那里你可以查看一个特定僵尸的信息并可以分享它的链接。这个页面应该渲染僵尸的外形，展示它的名字，它的所有者（以及用户主页的链接），它的输赢次数，它的战斗记录等等。

  b. 一个用户界面，在那里你可以查看用户的僵尸大军并分享它的链接。
  
  c. 一个主页，就是用户页面的变体，可以展示当前用户的僵尸大军（正如我们在index.html）里面实现的那样。

4. 界面中的一些方法允许用户用 CryptoKitties 喂食僵尸。我们可以给每一个僵尸添加一个按钮，叫做“给我投食”，再给一个输入框让用户输入一个猫咪的ID（或者一个猫咪的网址，比如<a href="https://www.cryptokitties.co/kitty/578397" target=_blank>https://www.cryptokitties.co/kitty/578397</a>），它将触发我们的 `feedOnKitty` 函数。

5. 界面中的一些方法将让用户用来攻击其他用户的僵尸

  实现这点的一个方法是，当用户浏览其他用户的页面的时候，可以在对方僵尸旁边显示一个按钮，叫做“攻击这头僵尸”。当用户点击的时候，可以弹出一个模块，展示当前用户的僵尸大军并询问用户“你想用哪头僵尸出战？”

  在用户的主页，也可以在每个僵尸旁边显示一个按钮，叫做“攻击一个僵尸”。当用户点击的时候，可以弹出一个模块，展示一个搜索框，可以让用户输入僵尸ID或者网址来搜索，或者也可以有一个按钮叫做“随机攻击一头僵尸”，将随机搜索一头僵尸来。

  我们也建议你将在冷却期的僵尸用特殊的颜色显示，比如使其变成灰色。这样界面就能告诉用户不能用冷却期的僵尸来进攻。

6. 在用户的主页，每一个僵尸也应该有选项可以更改名字、DNA、以及升级（通过付费）。若用户等级不到，无法使用的选项应该标灰。

7. 对于新用户，我们应该显示一个欢迎信息，并让其确认用 `createRandomZombie()`创建一个新僵尸。

8. 也可以为我们的智能合约添加一个包含`indexed` 的用户地址属性的 `Attack` 事件。这样就可以创建实时通知了——我们可以在用户的僵尸遭受攻击的时候弹出一条通知，这样他们可以看到谁在用什么僵尸攻击他们并做出报复。

9. 我们也许还想实现一些前端缓存层，这样就不用总是为了相同的数据去访问Infura。（在我们当前实现中，`displayZombies` 将在每次页面刷新的时候为每一个僵尸调用 `getZombieDetails`，但是实际中我们将只需要为新加入的僵尸调用这个函数）

10. 一个实时聊天室，这样你就可以在你击溃别人的僵尸大军的同时嘲讽他们？

因为这将需要大量的前端代码来实现全部的界面（HTML， CSS， JavaScript 以及诸如 React 和 Vue.js 这样的框架）。光实现一个这样的前端界面也许会花费多达10节课，所以我们将这个光荣的任务交给你自己去完成。

> 注意：尽管智能合约是去中心化的。这个用来和DApp交互的前端界面依然需要放在我们中心化的网络服务器上。不过，有了我们正在内测的<a href="https://medium.com/loom-network-chinese/3d0d686163df" target=_blank>Loom Network</a> SDK，很快你就可以在应用自己的DApp链上运行前端界面而不是中心化的网络服务器。这样在以太坊和 Loom DApp 链上，你的整个应用都100%运行在区块链上了。

## 总结

学完第六课。你现在有了编写智能合约和前端界面来让用户交互的所需技能了。

在下一课。 我们将涉及这个历程中最后缺失的一部分——将你的智能合约部署到以太坊。

知道你已经急不可耐了，点击“下一章”领取你的奖励吧。
