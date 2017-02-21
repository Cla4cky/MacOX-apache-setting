# MacOX-apache-setting
## Apache 配置
### Apache 常用命令
* 开启Apache：sudo apachectl start
* 关闭Apache：sudo apachectl stop
* 重启Apache：sudo apachectl restart
* 查看Apache版本: sudo apachectl -v

### 打开 Apache
* 同时按下键盘上的command和空格键，然后我们输入Terminal来打开我们的终端，然后我们输入代码：sudo apachectl start然后enter回车来打开我们的apache，如果跳出password的话需要输入你mac账户的密码。输入完了后enter回车apache就打开了。我们打开我们的浏览器在url那输入localhost。如果出现“It works!”界面，说明我们的apache成功打开。

###配置PHP
* 在进一步配置apache前我们先去配置好php，我们打开我们的Finder,然后我们同时按下键盘上的command+shift+g来快速进入apache的目录，我们在跳出的窗口上面输入“/etc/apache2/”然后enter回车，我们就来到了apache下的目录了（也可以使用终端来快速进入和修改apache文件，但是本人推荐最好别用terminal来修改不是很方便！）我们看到apache2的文件夹下有个“httpd.conf”。我们用mac自带的TextEdit来编辑这个文件（其他的编辑软件也能使用来编辑比如：vscode，webstorm。）
* 我们打开“httpd.conf”看到了很多看不懂代码，别急！我们先去copy一下“httpd.conf”文件先，要是我们修改错误了我们还能重新回来配置，推荐把copy的“httpd.conf”放到desktop里面（桌面）。这些小技巧都做好了，我们开始配置phpQWQ!我们先来到代码第169行：#LoadModule php5_module libexec/apache2/libphp5.so这。我们把前面的#删掉，就行了，然后我们开始按command+s来保存，却发现mac跳出了一个窗口说我们没有权限去修改“httpd.conf”！那么我们该怎么办呢。
* 我们先回到终端那，输入代码：sudo chmod -R 777，然后在777后面加个空格，我们再回到我们的apache2那复制apache2的目录（右键apache目录，然后有个copy“apache2”就是复制文件夹路径的了。）我的代码是：sudo chmod -R 777 /private/etc/apache2。然后我们enter回车。这样我们就能随意修改apache2下的文件。
* 重新打开“httpd.conf”文件，回到169行代码那修改#LoadModule php5_module libexec/apache2/libphp5.so，把前面的#去掉就行了，然后我们command+s保存，我们回到终端那输入代码：$ sudo cp /etc/php.ini.default /etc/php.ini，enter回车，来生成PHP配置文件，之后我们来到apache的根目录："/Library/WebServer/Documents"（可以和之前一样用command+Shift+g来快速进入）。我们在目录里面写一个php文件，文件代码可以随意我们取名为test.php，然后我们重新打开下apache，在浏览器里面输入：localhost/test.php。只要显示成功就说明我们的php配置成功了，如果没成功就重新再来配置一次！QWQ。
