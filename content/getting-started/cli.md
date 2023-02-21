<!-- +++ 
title = "Command-line install"
weight = 3
description = "Installation instructions for technical users"
tag = "selfhost"
+++ -->

+++
title = "命令行安装"
weight = 3
description = "技术用户安装说明"
tag = "自我托管"
+++

<!-- This guide covers running the Urbit runtime (Vere) using the command line. This  
can be run on your local machine or a server in the cloud, we just cover the
local case here. The runtime is what interprets the Urbit kernel code (Arvo)
into commands your specific machine (macOS or Linux) understands. -->

本指南涵盖使用命令行来运行 Urbit runtime（Vere）。这可以在你的本地计算机或云端服务器上运行，但我们在这里只介绍本地计算机的案例。Runtime 是将 Urbit 内核代码 (Arvo) 解释为你的特定机器 (macOS 或 Linux) 所能理解的命令。

<!-- Note there is a much more comprehensive [cloud hosting 
guide](/getting-started/cloud-hosting) which walks through setting up Urbit on a
[Digital Ocean](https://www.digitalocean.com/) VPS. -->

请注意，这里有一个更全面的[云托管操作指南](/getting-started/cloud-hosting)，其中介绍了如何在
[Digital Ocean](https://www.digitalocean.com/) VPS上设置 Urbit。

<!-- ### 1. System Requirements {% #about-swap-space %} 

- **Processor**: 1 core
- **Memory**: 2GB
- **Storage**: At least a few GB, 40-50GB preferable
- **Network**: Any -->

### 1. 系统要求 {% #about-swap-space %}. 

- **处理器**: 单核 (1 core)
- **内存**: 2GB
- **存储**：至少几GB，最好是 40-50GB
- **网络**：任何网络

<!-- **A note on memory**: By default, the Urbit runtime needs 2GB of free memory, 
and will fail to boot without it. Urbit usually only uses a portion of this, so
it's possible to use a swap file to makeup for a shortfall without degrading
performance. For instructions on how to configure a swap file on Linux, see
[this linuxize.com guide](https://linuxize.com/post/create-a-linux-swap-file/).-->

**关于内存的说明**：默认情况下，Urbit runtime 需要2GB的可用内存，没有符合的情况下将无法启动。
Urbit 通常只使用其中的一部分，所以可以使用交换文件来弥补内存的不足而不会降低性能。有关如何在 Linux 上配置交换文件的说明，请参阅
[这个 linuxize.com 指南](https://linuxize.com/post/create-a-linux-swap-file/)。

<!-- **A note on storage**: Urbit saves every event it processes to its [Event 
Log](https://developers.urbit.org/reference/glossary/eventlog). This means its
disk usage slowly grows over time. Until event log truncation is implemented,
it's advisable to have 40 or 50GB of disk space available, so you don't have to
worry about running out for a long time. If you don't have that much, your ship
will still run fine, but you may run out of space some months down the line. -->

**关于存储的说明**：Urbit 将它处理的每一个事件都保存在其[事件日志 (Event Log)](https://developers.urbit.org/reference/glossary/eventlog)。这意味着它的磁盘使用量会随着时间的推移而慢慢增加。在事件日志被截断之前，建议你有40或50GB的可用磁盘空间，这样你就可以在很长一段时间内不必担心磁盘空间不足的问题。即使你没有那么多的磁盘空间，你的飞船 (ship) 仍然可以正常运行，但你可能会在几个月后耗尽磁盘空间。

<!-- ### 2. Install Urbit 

Choose your operating system and run the given command in your terminal to
download the Urbit runtime, this command downloads the latest build, unpacks
it, and runs the binary with no arguments to show you the help output: -->

### 2. 安装 Urbit

选择你的操作系统，并在你的终端中运行给定的命令来下载 Urbit runtime。该命令下载最新的构建版本，将其解压缩，并运行不带参数的二进制文件以显示帮助输出：

{% tabs %}

{% tab label="Linux x86_64" %}

```shell
curl -L https://urbit.org/install/linux-x86_64/latest | tar xzk --transform='s/.*/urbit/g' && ./urbit
```

{% /tab %}

{% tab label="Linux AArch64" %}

```shell
curl -L https://urbit.org/install/linux-aarch64/latest | tar xzk --transform='s/.*/urbit/g' && ./urbit
```

{% /tab %}

{% tab label="macOS x86_64" %}

```bash
curl -L https://urbit.org/install/macos-x86_64/latest | tar xzk -s '/.*/urbit/' && ./urbit
```

{% /tab %}

{% tab label="macOS AArch64" %}

```bash
curl -L https://urbit.org/install/macos-aarch64/latest | tar xzk -s '/.*/urbit/' && ./urbit
```

{% /tab %}

{% /tabs %}

<!-- If successful, you will see a block of output beginning with the line: -->

如果成功的话，你会看到根据以下行开头的输出块：

```
Urbit: a personal server operating function
```

<!-- ### 3. Boot Urbit 

An Urbit instance is intrinsically tied to a unique identity called an **Urbit
ID**. There are five classes of Urbit ID, but we will consider two here: comets
and planets. -->

### 3. 启动 Urbit 

一个 Urbit 实例本质上是与一个称为 **Urbit ID** 的独特身份相关联。Urbit ID 有五类，但我们在这里只考虑两类：彗星 (comets) 和行星 (planets)。

<!-- - **Comet:** A comet is an identity which anyone can generate themselves, for 
  free. It's a good option to try out Urbit. Comets are limited by the fact they
  cannot be "factory reset", meaning if your urbit somehow becomes broken or
  corrupted then you'll have to start again with a new identity. In that sense,
  they are impermanent. -->
  
- **彗星：** 彗星是一种任何人都可以免费生成的个人身份。这是一种尝试 Urbit 的好选择。彗星的局限性在于它们不能 "出厂重置 (factory reset)"。这意味着如果你的 Urbit 以某种方式被破坏或损坏，那么你将不得不用一个全新的身份重新开始。从这个意义上说，它们是无常的。

<!-- - **Planet:** A planet is a permanent identity which you own forever. Planets 
  are the class intended for individuals. While there are essentially an
  unlimited number of comets, planets are more scarce (preventing spamming,
  among other things). This scarcity means they usually aren't free (though
  sometimes nice people give them away). This guide will assume you've already
  acquired a planet. If you haven't, you can refer to the ["Get an Urbit ID"
  guide](/getting-started/get-id) before continuing. -->
  
- **行星：** 行星是一个永久性身份，你可以永远拥有它。行星是为个人设计的类别。彗星的数量基本上是无限的，而行星则更为稀缺（其中一个用例就是防止垃圾邮件）。这种稀缺性意味着它们通常不是免费的（但有时候，好心人会赠送它们）。本指南假设你已经获得了一个行星。如果你没有的话，可以在继续本指南之前参考["获取 Urbit ID"指南](/getting-started/get-id)。

<!-- Follow the instructions for your case: -->

按照你的案例说明进行操作：

{% tabs %}

{% tab label="Boot a Comet" %}

In the terminal, with the `urbit` binary you installed in the previous step, a
comet can be booted with the `-c` option:

在终端中，使用你在上一步安装的 `urbit` 二进制文件，以 `-c` 选项来启动彗星。

```bash
./urbit -c mycomet
```

<!-- > `mycomet` will be the name given to the folder it will create.  
>  You can choose any name you like. -->

> `mycomet` 将是它所创建的文件夹的名称。
> 你可以选择任何你喜欢的名称。

<!-- It may take a while to initialize the comet (usually only a couple of minutes, 
but it could take longer). When it's done, it'll take you to the dojo prompt
(the dojo is Urbit's shell): -->

初始化彗星可能需要一些时间（通常只需几分钟，但可能需要更长的时间）。完成后，它将带你进入 dojo 提示界面
(dojo 是 Urbit 的外壳 (shell))。

```
ames: live on 31337
http: web interface live on http://localhost:8080
http: loopback live on http://localhost:12321
~sampel_marzod:dojo>
```

<!-- You can shut down the comet again by typing `|exit` in the dojo or hitting 
`Ctrl+D`. When it's first shut down, the runtime will be copied inside the data
folder, so you can start it up again by doing:-->

你可以通过在 dojo 中输入 `|exit` 或者按 `Ctrl+D` 来再次关闭彗星。当它第一次被关闭时，runtime 将被复制到数据文件夹内，所以你可以通过以下方式再次启动它。

```bash
./mycomet/.run
```
<!-- > Linux users need to run this command in another terminal window to access 
> your urbit on port 80 every time you upgrade your runtime (otherwise it'll 
> default to port 8080):
> 
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ``` -->
  
> Linux 用户需要在另一个终端窗口中运行以下命令，以便每次升级运行时在80端口访问你的 Urbit（否则它将默认为8080端口）。
> 
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ```

<!-- Since comets are often used temporarily and then discarded, kernel updates are 
not enabled by default. If you plan to use your comet for a while, it's a good
idea to enable updates with the following command in the dojo: -->
  
由于彗星经常被临时使用后而被丢弃，因此内核更新在默认情况下是未启用的。如果你打算使用你的彗星一段时间，最好的办法是在 dojo 中使用以下命令启用更新:

```
|ota (sein:title our now our)
```

<!-- Lastly most people use their urbit via Landscape, the browser-based UI. In order  
to access Landscape, you need your web login code. You can get this by running 
the following command in the dojo: -->
  
最后，大多数人是通过 Landscape，即基于浏览器的用户界面来使用他们的 Urbit。为了访问 Landscape，你需要你的网络登录代码。你可以通过在 dojo 中运行以下命令来获得这个代码：

```
+code
```

<!-- It'll spit out a code that'll look something like `lidlut-tabwed-pillex-ridrup`. 
Copy the code it gives you to the clipboard. -->

它将生成一个类似于 `lidlut-tabwed-pillex-ridrup` 的代码，然后将这个代码复制到剪贴板上。

{% /tab %}

{% tab label="Boot a Planet" %}

<!-- In order to boot a planet, you need a copy of its private keys. If you got your 
planet via a claim link, the passport backup `.zip` file you downloaded will
contain a file called something like `sampel-palnet-1.key`. If you don't have
the passport backup or you got your planet by another method, you can instead
login to [Bridge](https://bridge.urbit.org/), select your planet, go to the OS
section, and hit the "Download Keyfile" button. -->
  
为了启动一个行星，你需要一份属于它的私钥副本。如果你是通过领取链接来获得你的行星，那么你下载的护照备份 `.zip` 文件将包含一个类似于`sampel-palnet-1.key` 的文件。如果你没有护照备份，或者你通过其他方法得到你的行星，那么你可以登录 [桥接 (Bridge)](https://bridge.urbit.org/)来选择你的行星，然后进入操作系统部分，并点击 "下载密钥文件 "按钮。

<!-- Back in the terminal, with the `urbit` binary you installed in the previous 
step, you can boot your planet with the following command (replacing
`sampel-palnet` with your own planet and pointing to the location of your
keyfile): -->
  
回到终端，使用你在上一步中安装的 `urbit` 二进制文件，你可以使用以下命令启动你的行星（将 `sampel-palnet` 替换为你自己的行星，并指向你的密钥文件位置）：

```bash
./urbit -w sampel-palnet -k sampel-palnet-1.key
```

<!-- This will create a folder with the name of your planet and begin booting. 
It may take a while to initialize the planet (usually only a couple of minutes,
but it could take longer). When it's done, it'll take you to the dojo prompt
(the dojo is Urbit's shell): -->
  
这将创建一个带有你的行星名称的文件夹，并开始启动运行。初始化行星可能需要一些时间（通常只需几分钟，但可能需要更长的时间）。完成后，它将带你进入 dojo 提示界面(dojo 是 Urbit 的外壳 (shell))。

```
ames: live on 31337
http: web interface live on http://localhost:8080
http: loopback live on http://localhost:12321
~sampel-palnet:dojo>
```

<!-- You can shut down the planet again by typing `|exit` in the dojo or hitting 
`Ctrl+D`. When it's first shut down, the runtime will be copied inside the data
folder, so you can start it up again by doing: -->
  
你可以通过在 dojo 中输入 `|exit` 或者按 `Ctrl+D` 来再次关闭行星。当它第一次被关闭时，runtime 将被复制到数据文件夹内，所以你可以通过以下方式再次启动它。

```bash
./sampel-palnet/.run
```
<!-- > Linux users need to run this command in another terminal window to access
> your urbit on port 80 every time you upgrade your runtime (otherwise it'll 
> default to port 8080):
>
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ``` -->

> Linux 用户需要在另一个终端窗口中运行以下命令，以便每次升级运行时在80端口访问你的 Urbit（否则它将默认为8080端口）。
> 
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ``` 

<!-- Most people use their urbit via Landscape, the browser-based UI.  
In order to access Landscape, you need your web login code.
You can get this by running the following command in the dojo: -->
  
最后，大多数人是通过 Landscape，即基于浏览器的用户界面来使用他们的 Urbit。为了访问 Landscape，你需要你的网络登录代码。你可以通过在 dojo 中运行以下命令来获得这个代码：

```
+code
```

<!-- It'll spit out a code that'll look something like `lidlut-tabwed-pillex-ridrup` 
(note this is a separate code to your master ticket). Copy the code it gives you
to the clipboard. -->
  
它将生成一个类似于 `lidlut-tabwed-pillex-ridrup` 的代码 (请注意，这与主票 (master ticket) 的代码不同)，然后将这个代码复制到剪贴板上。

One last thing: The `sampel-palnet-1.key` keyfile is only needed once, when you
first boot your planet. **Now that it's booted, it's good security practice to
delete that keyfile.**

最后一件事：`sampel-palnet-1.key` 密钥文件只需要一次，那就是当你
第一次启动行星的时候。**现在它已经启动了，删除该密钥文件是很好的安全做法。**

{% /tab %}

{% /tabs %}

### 4. Login

<!-- While your urbit is running, the web interface called *Landscape* can be 
accessed in the browser. Its URL will usually be either `localhost` or
`localhost:8080`, depending on your platform. To check the address, you can look
at the boot messages in the terminal. You should see a line like: -->

当你的 Urbit 在运行时，可以在浏览器中访问名为 Landscape 的网络界面。它的 URL 通常是 localhost 或者 localhost:8080，这取决于你的平台。若要检查地址，你可以在终端中查看启动信息。你应该看到以下这一行字：
  
```
http: web interface live on http://localhost:8080
```

<!-- Whichever address and port it says there is the one to open in the browser. -->
  
无论它说的是哪个地址和端口，都会有一个可以在浏览器中打开。

<!-- Once open, you'll be presented with the login screen. Paste in the web login 
code you copied from the dojo in the previous step and hit "continue". You'll
now be taken to your homescreen, with tiles for the default apps such as Groups,
Talk, and Terminal. -->

一旦打开后，你就会看到登录屏幕。粘贴你在上一步中从 dojo 复制的网络登录代码，然后点击 "继续 (continue)"。你现在将被带到你的主屏幕，其中包含一些默认应用程序的磁贴，如 Groups、Talk 和 Terminal。  
  
<!-- ### 5. Runtime Upgrades -->

### 5. Runtime 升级

<!-- When new versions of the Urbit runtime (Vere) are available, you'll have to  
shutdown your urbit and then run the `next` command in order to upgrade.
```
:dojo> |exit
<pier>/.run next
``` -->

当新版本的 Urbit runtime（Vere）可用时，你必须关闭你的 Urbit，然后运行 `next` 命令才能升级。
```
:dojo> |exit
<pier>/.run next
```

<!-- Note that `<pier>` in this case is the folder that was created when you first booted 
your urbit. When you run this command your urbit will download the latest binary
and place it inside the `.bin` directory inside your pier folder. You can then 
start your ship with the following and you'll be on the latest runtime version:
```
<pier>/.run
```
> Linux users need to run this command in another terminal window to access
> your urbit on port 80 every time you upgrade your runtime (otherwise it'll 
> default to port 8080):
>
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ``` -->
  
请注意，`<pier>` 在这种情况下是你第一次启动 Urbit 时所创建的文件夹。当你运行此命令时，你的 Urbit 将下载最新的二进制文件，并把其放置在你的 pier 文件夹内的 `.bin` 目录中。然后，你可以通过以下方法来启动你的飞船，以便使用最新的 runtime 版本。
```
<pier>/.run
```
> Linux 用户需要在另一个终端窗口中运行以下命令，以便每次升级运行时在80端口访问你的 Urbit（否则它将默认为8080端口）。
> ```shell
> sudo apt-get install libcap2-bin
> sudo setcap 'cap_net_bind_service=+ep' <pier>/.run
> ```
  
<!-- If you've been running Urbit for a while (from before runtime version 1.9)  
and these `.run` commands don't work for you, it probably means you need to 
[dock](https://operators.urbit.org/manual/running/vere#dock) your pier. 
You can do this with the following command: 
```
./urbit dock <pier>
```
Then `.run` should work as expected and future runtime upgrades can be done via
`next`. -->
  
如果你已经运行 Urbit 一段时间（从 runtime 1.9版本之前开始），而这些 `.run` 命令对你不起任何作用。这可能意味着你需要 dock 你的 pier。你可以使用以下命令执行此操作：
```
./urbit dock <pier>
```
然后，`.run` 应该能像预期的那样操作，而未来的 runtime 升级可以通过 `next` 来完成。

<!-- ## Next steps 

Learn how to [get around your
urbit](/getting-started/getting-around). -->
  
## 下一步

学习如何[使用你的 Urbit](/getting-started/getting-around)。
