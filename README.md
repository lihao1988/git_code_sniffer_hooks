#安装配置

##安装 jshint

###最新稳定版Node
>- sudo add-apt-repository ppa:chris-lea/node.js
>- sudo apt-get update
>- sudo apt-get install nodejs

###jshint
>- sudo npm install jshint -g

##安装 PHP_CodeSniffer
>- sudo apt-get install php-pear
>- sudo pear install PHP_CodeSniffer
>- sudo phpcs --config-set encoding utf-8
>- sudo phpcs --config-set default_standard Zend

##安装 git_code_sniffer_hooks

###获取相关代码
>- mkdir ~/bin/
>- cd ~/bin/
>- git clone git://github.com/NanJingBoy/git_code_sniffer_hooks.git

###安装python相关依赖
>- sudo apt-get install python-setuptools
>- sudo easy_install pip
>- sudo pip install -r ~/bin/git_code_sniffer_hooks/requirements.txt  

###配置
>- ln -s ~/bin/git_code_sniffer_hooks/pre-commit ~/workspace/test/.git/hooks/ （假设您的项目目录为~/workspace/test）
>- ln -s ~/bin/git_code_sniffer_hooks/pre-receive ~/workspace/test/.git/hooks/ （服务端）

#说明
>- 服务端需要安装cowsay （sudo apt-get install cowsay）
>- 执行git commit时，如果代码格式有误会禁止提交，可将~/bin/git_code_sniffer_hooks/configs/default.cfg中commit节点下的REJECT_COMMIT设置为False以改变其行为
>- 客户端执行git push时，如果代码格式有误服务器会禁止push，可将~/bin/git_code_sniffer_hooks/configs/default.cfg中receive节点下的REJECT_RECEIVE设置为False以改变其行为（服务端）
