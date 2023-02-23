<!-- +++ 
title = "Get an Urbit ID"
weight = 2
description = "How to acquire an Urbit ID"
tag = "selfhost"
+++ -->

+++
title = "获取一个 Urbit ID"
weight = 2
description = "如何获取一个 Urbit ID"
tag = "自我托管"
+++


<!-- ### Types of ID 

There are [five different
types](https://operators.urbit.org/guides/which-id-should-i-buy) of Urbit ID, but here we'll just be  discussing two types called comets and planets.

**Comets** are free, temporary identities that you can issue yourself and are best-suited for
short-term usage. **Planets** are permanent identities that are suitable for long-term use.

![](https://storage.googleapis.com/media.urbit.org/site/getting-started/comet-planet.png)

Planets have a unique, four syllable phonetic name and a [sigil](https://urbit.org/blog/creating-sigils), a visual representation of the name. -->

### ID 的类型

Urbit ID 有 [五种不同的类型](https://operators.urbit.org/guides/which-id-should-i-buy)，但在这里我们只讨论两种类型，即彗星和行星。

**彗星** 是免费的临时身份，你可以自己签发，但只适合短期使用。**行星** 是永久性身份，适合长期使用。

![](https://storage.googleapis.com/media.urbit.org/site/getting-started/comet-planet.png)

Planets have a unique, four syllable phonetic name and a [sigil](https://urbit.org/blog/creating-sigils), a visual representation of the name.


行星具有独特的四个音节名称和一个 [符号 (sigil)](https://urbit.org/blog/creating-sigils)，即名称的视觉表示。


<!-- ### Where to get a planet 

There are a few ways to get your own planet:

- Receiving one from a friend
- Asking on Twitter (if you're lucky)
- Booting a comet and being friendly in [Urbit Community](https://urbit.org/groups/~bitbet-bolbel/urbit-community)
- Purchasing one from a marketplace -->

This guide will cover the last case and what to do after receiving one.

### 哪里可以获取一个行星

有几种方法可以获取属于你自己的行星：

- 从朋友那里得到一个
- 在推特 (Twitter) 上询问（如果你很幸运的话）
- 启动彗星，并在 [Urbit 社区](https://urbit.org/groups/~bitbet-bolbel/urbit-community) 保持友好
- 从市场上购买一个

本指南将介绍最后一个案例以及收到行星后的流程说明。

<!-- ### Buying a planet 

There are many places to buy a planet using either crypto or fiat currency.

Layer 1 planets are the most available through marketplaces, however they can be expensive due to Ethereum gas fees. You will need an Ethereum wallet such as Metamask to purchase planets, and will later need to sign in to Bridge with your wallet to configure your planet.

Layer 2 planets do not require any crypto wallet management, but are only available on specific marketplaces.

There is no difference between Layer 1 or Layer 2 in the quality of experience
when using Urbit. -->

### 购买一个行星

有许多地方可以使用加密货币或法定货币来购买行星。

第1层 (Layer 1) 行星在市场上是最容易买到的，但由于以太坊的费用，它们可能很昂贵。你需要一个以太坊钱包 (例如 Metamask) 来购买行星，随后需要使用你的钱包登录桥接 (Bridge) 以配置你的行星。

第2层 (Layer 2) 行星不需要任何加密货币钱包管理，但只在特定市场上可以买得到。

在使用 Urbit 时，第一层或第二层的体验质量没有区别。

<!-- Here are a few of the places where you can buy planets: 
{% table .w-full .my-4 %}
* L1 Planet Markets
* L2 Planet Markets
---
*
    - [Urbitex](https://urbitex.io)
    - [Urbit.live](https://urbit.live)
    - [Urbit.me](https://urbit.me)
* 
    - [azimuth.shop](https://azimuth.shop)
    - [lanlyd](https://lanlyd.net/)
    - [~mocbel house](https://mocbel.house)
    - [\_networked subject](https://subject.network)
    - [Planet Market](https://planet.market)
    - [Wexpert Systems](https://wexpert.systems)
{% /table %}

{% callout %} -->

以下是一些可以购买行星的地方：
{% table .w-full .my-4 %} 
* L1 行星市场
* L2 行星市场
---
*
    - [Urbitex](https://urbitex.io)
    - [Urbit.live](https://urbit.live)
    - [Urbit.me](https://urbit.me)
* 
    - [azimuth.shop](https://azimuth.shop)
    - [lanlyd](https://lanlyd.net/)
    - [~mocbel house](https://mocbel.house)
    - [\_networked subject](https://subject.network)
    - [Planet Market](https://planet.market)
    - [Wexpert Systems](https://wexpert.systems)
{% /table %}

{% callout %}


<!-- **Layer 2 for planets** 

Learn more about [layer 2 for planets](https://operators.urbit.org/manual/id/layer-2-for-planets) in the User's Manual page on the topic.

{% /callout %} -->


**第2层行星**

了解更多有关 [第2层行星](https://operators.urbit.org/manual/id/layer-2-for-planets) 的信息，请参阅用户手册的专题页面。

{% /callout %}


### Claiming your planet

An invitation to claim your planet comes in one of two forms.

The first is an email invitation with an Urbit ID and a Master Ticket.

The second, made available through our [L2 solution](https://operators.urbit.org/manual/id/layer-2-for-planets), is an activation code or a link to activate on [Bridge](https://bridge.urbit.org), the Urbit ID management tool.

![](https://media.urbit.org/site/getting-started/Server-setup-1.jpg)

Clicking a link to activate a planet on Bridge will take you to page which will generate a Master Ticket for you. Follow the instructions which will prompt you to download a copy of your Passport: your Master Ticket, management proxy, and keyfile. Store your Master Ticket and management proxy somewhere safe, hold on to the keyfile, and proceed to the next step.

{% callout %}


### 领取你的行星

领取你的行星的邀请函有两种形式。

第一种是带有 Urbit ID 以及主票 (Master Ticket) 的电子邮件邀请。

第二种是通过我们的 [L2 解决方案](https://operators.urbit.org/manual/id/layer-2-for-planets)提供的，是一个激活码或者在[Bridge](https://bridge.urbit.org)上激活的链接，Urbit ID管理工具。

！[](https://media.urbit.org/site/getting-started/Server-setup-1.jpg)

在Bridge上点击激活星球的链接将带你进入为你生成主票的页面。按照指示，你将下载一份护照的副本：你的主票、管理代理和密钥文件。将你的主票和管理代理保存在一个安全的地方，拿着钥匙文件，继续进行下一个步骤。

**Claiming L1 planets**

If you’ve purchased an L1 planet, you won’t need to claim it because you already own it as an NFT. Simply log into Bridge using Metamask or your wallet of choice.

{% /callout %}


### Using Bridge to get your keyfile

Now that you have your planet, you can create your keyfile (eg. `sample-palnet.key`), which is the cryptographic signature required to encrypt and decrypt messages on Urbit's P2P network.

- **Claimed L2 planets**  
  If you’ve claimed your L2 Planet then you should already have downloaded your Passport, which contains your Master Ticket and keyfile.

- **Master Ticket holders**  
  If you haven’t downloaded your Passport but have a Master Ticket, then you can simply log in with Bridge using the Master Ticket option with your planet name and Master Ticket password. Click the ID box near the bottom of the page to open the ID page, then click the **Download Passport** button, which contains your keyfile.

- **L1 Planet Purchasers**  
  Log in to Bridge with your Ethereum wallet using Metamask or the wallet of your choice with WalletConnect. Click the “OS” box on the bottom of the page to open the OS page, and then click the **Download Keyfile** button.

### Next steps

Now that you have a keyfile let's move on to booting the Urbit OS.

- [CLI instructions](/getting-started/cli) – Set up Vere, the Urbit runtime, using the command line.

- [Install on the cloud](/getting-started/cloud-hosting) – A step-by-step guide to setting up Urbit on a VPS.

- [Set up a home server](/getting-started/home-servers) – Explore options for running your own dedicated physical Urbit computer.
