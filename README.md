#Ansible-Wordpress-Ubuntu

Unbuntu上でNginx,MySQLを使ってWordpressの環境を自動で設定します。

＊hosts,group_varsはそれぞれ書き換えて下さい

##使い方

- Ansibleのインストール
```
$ pip install -r requirements.txt
```

- Ansibleの実行(usernameは書き換えてください)
```
$ ansible-playbook -i hosts wordpress.yml -u username
```

##Vagrantを使ったVM上での実行

Vagrantが使用できることを前提とします。
- VagrantでVMを起動
```
$ vagrant up
```

- ローカルにAnsibleをインストール
```
$ pip install -r requirements.txt
```

- SSH public key をゲストにアップロード
```
$ cat ~/.ssh/id_rsa.pub (ホスト上)
# 出力されたキーをコピー
$ vim ~/.ssh/authorized_keys (ゲスト上)
# コピーしたキーをペースト
```

- Ansibleの実行
```
$ ansible-playbook -i hosts vagrant.yml -u vagrant
```
