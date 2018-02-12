## 注意事項

あくまでローカル環境の構築のために使ってください。

## 環境

Centos7.1 + Apache2.4 + PHP7.1 + MySQL5.6

[その他]
phpMyAdminインストール済

## 手順

1.[github](https://github.com/kyutaro/MyAnsible)からファイルをDL

2.vagrantfileやansible関連ファイル等を置くための任意のディレクトリへ移動
※例 C:/Vagrant/MyAnsible/ など

3.DLしたものから、利用したい環境用のディレクトリを移動したディレクトリの下に配置
※例 C:/Vagrant/MyAnsible/Centos_7_1_httpd_2_4_php_7_1_mysql_5_6/ など
※ディレクトリ名はどんな環境が入っているのかパッと分かるように付けただけなので、適宜変更されたし

4.配置したディレクトリの中に移動

5.boxの追加
'vagrant box add 任意のbox名 https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.1/vagrant-centos-7.1.box'

6.初期化
'vagrant init 任意のbox名'

7.生成されたvagrantfileをgithub上のvagrantfileで上書き
[vagrantfile](https://github.com/kyutaro/SettingFiles/blob/master/Vagrantfile_Centos_7_1_httpd_2_4_php_7_1_mysql_5_6)

8.vagrantfile下記の事項を自分の環境に合わせて変更。
`config.vm.box = "ansible_centos7_1_php7_1"`
`config.vm.network "private_network", ip: "192.168.56.102"`

※権限や共有フォルダなども、必要があれば適宜変更。

9.vagrantの立ち上げ
'vagrant up'