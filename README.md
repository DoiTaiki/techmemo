# README

## 開発環境
- OS: macOS Ventura 13.5
- Ruby: 3.2.2
- Rails: 7.0.6
- mysql: 8.0.31

## 準備
```
rbenv install 3.2.2
rbenv local 3.2.2
rbenv rehash
bundle init
bundle config path vendor/bundle --local
vi Gemfile(コメントイン+バージョン追記)(gem "rails", "7.0.6")
bundle install
bin/rails new . -d mysql --css tailwind -T
config/database.ymlにDBのpassword入力
  vi ~/.zshrc
  export LOCAL_MYSQL_PASSWORD="(設定するpw)"(.zshrc内に入力)
  source ~/.zshrc
  password: <%= EMV["LOCAL_MYSQL_PASSWORD"] %>(config/database.yml内に入力)
bin/rails db:create
(rspecを使用する場合)
  Gemfileにgem "rspec-rails", "(指定するバージョン)"を追記
  bundle install
  bin/rails g rspec:install
bin/rails g scaffold article title:string content:rich_text
bin/rails action_text:install
bundle install(action_textに必要なgem "image_processing"のインストール)
bin/rails db:migrate
```

## 起動
bin/dev
