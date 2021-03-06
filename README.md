# 硬件

- 两个U盘，其中一个至少8GB。
- 两个不常用的支持iOS 10+的设备用来离线签名，例如iPhone 5s和iPad mini 2。
- 一个常用的iPhone用来安装观察钱包。
- 一台英特尔处理器的Mac电脑。

# 软件
- [Tails操作系统](https://tails.boum.org/install/mac/index.en.html)
- [bip39助记词生成工具](https://github.com/iancoleman/bip39/releases)
- [Electrum钱包](https://electrum.org/#home)
- [BlueWallet手机钱包](https://bluewallet.io)

# 创建多重签名冷钱包
1. 进入Mac系统，在一个至少8GB的U盘上安装[Tails操作系统](https://tails.boum.org/install/mac/index.en.html)。
2. 下载[助记词生成工具](https://github.com/iancoleman/bip39/releases/download/0.5.4/bip39-standalone.html)到另一个U盘。
3. 重启Mac，按住Option键，进入Tails操作系统，不连接网络。
4. [创建Persistent分区](https://tails.boum.org/doc/first_steps/persistence/index.en.html)。
5. 将bip39-standalone.html复制到Persistent分区Tor Browser目录下，然后双击打开。点击两次加号新建两个标签页显示同样的网页。
6. 在三个标签页里生成三组12个字的中文助记词，分别备份到不同的地方，尽量记在脑子里并经常复习。
7. 在三个标签页里点击English将助记词转成英文，在Derivation Path部分选择BIP141，BIP32 Derivation Path填入 `m/48'/0'/0'/2'`, Script Semantics选择`P2WSH (1-of-1 multisig)`。点击BIP32 Extended Public key可展示主公钥二维码。
8. 在常用的iPhone上用BlueWallet通过导入三个主公钥创建保管库观察钱包。
9. 在两个不常用的iOS设备上下载BlueWallet，然后断网。
10. 在第一个离线iOS设备上通过导入第一组助记词和后两个主公钥来创建保管库钱包。查看收币地址，与观察钱包的收币地址比较，如果不一致则需要检查错误重新创建钱包。
11. 在第一个离线iOS设备上通过导入第二组助记词和另外两个主公钥来创建保管库钱包，检查收币地址。
12. 在Tails系统自带的Electrum里通过导入第三组助记词和另外两个主公钥来创建2-of-3多重签名钱包，检查收币地址。
13. 进入Mac系统，安装[Electrum钱包](https://electrum.org/#home)，通过导入三个主公钥创建2-of-3多重签名观察钱包。

# 交易
1. 使用任一观察钱包创建交易。
2. 使用任意两个含有私钥的离线iOS设备或U盘通过二维码扫描或文件分享来签名交易。
3. 使用任一观察钱包通过二维码扫描或文件分享来广播交易。

# 注意事项
1. 如果离线iOS设备不支持iOS 13+，则需[降级至iOS 10.3.3](https://github.com/rA9stuff/LeetDown)，以安装可用的低版本BlueWallet。另外，其它高版本的BlueWallet需要打开Legacy URv1 QR选项，以兼容低版本的BlueWallet。
2. 如果所有设备丢失，想要恢复钱包至少需要两份助记词和所有三个主公钥。请确保牢记三份助记词，并做好助记词和所有主公钥的备份。
3. 如果没有两个可以长期离线的iOS设备，也可以用额外的8GB以上U盘替换。

# 打赏
bc1qk9kuzkwphxnt0gj2z3xf5j9svmrfarg2cckmqvzfr5qy0wwjrfrqssdyx0
