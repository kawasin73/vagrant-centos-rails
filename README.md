# Vagrant のサンプル

CentOS6.7 を用いて、Railsを開発したい時のVagrantFileです。
より依存を少なくするために、プロビジョニングはShellで行います。

## 前提

`vagrant` と `virtualbox` を利用することを前提としています。

Mac OSX でインストールするときは

```bash
brew cask install virtualbox
brew cask install vagrant
vagrant plugin install vagrant-vbguest
```

Windows でインストールするときは、公式サイトからダウンロードしてください。

- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant](https://www.vagrantup.com/downloads.html)

`vagrant-vbguest` は、Guest Additionを最新に更新してくれるpluginです。
このプラグインがない場合、２回目以降の`vagrant up`で、mount に失敗することがあります。
また、`vagrant-vbguest` をインストールした場合でも、`vagrant up`に失敗してしまうことがあるようです。その場合は、以下の記事を参考にしてください。

- [vagrant-vbguestプラグインがGuestAdditionsを無効にしてしまう](http://qiita.com/hapicky/items/a7f9d56588f96d005fad)

## 利用方法

```
git clone https://github.com/kawasin73/vagrant-centos-rails
vagrant up
vagrant ssh
```

## 注意点

- `bundle install` すると、`Could not fetch specs from https://rubygems.org/` となることがある。その際は、`vagrant reload` すると直るらしい。

[参考](http://qiita.com/roki1801/items/1665709a66ceb94987ea)

## 参考URL

- [rails-dev-box](https://github.com/rails/rails-dev-box)
- [@masuidrive のRailsプロジェクトの始め方](http://qiita.com/masuidrive/items/0e0e5294bc2dc81a52c2)
- [CentOS 6 / RHEL 6 に MySQL 5.6 を yum インストールする手順](http://weblabo.oscasierra.net/installing-mysql-rhel6-with-yum/)
