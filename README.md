### 今天要完成的事項

1.設定開發環境

2.下載程式原始碼

3.修改程式，測試修改結果，部署到正式環境

4.新增功能，測試修改結果，部署到正式環境

5.Q&A

6.討論是否要有下次的課程，下次課程的內容

### 以下是今天要執行的指令

註冊一個 GitHub 帳號 

https://github.com/

利用註冊好的 GitHub 帳號，註冊一個 Codeanywhere 帳號

https://codeanywhere.com/

新增 container

選擇 Ruby Development Stack with RVM and Ruby on Rails preinstalled. Ubuntu 14.04

安裝軟體

```
sudo apt-get update
sudo apt-get install gnupg2 postgresql postgresql-contrib libpq-dev
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
rvm get stable
rvm install 2.4
rvm use 2.4 --default
ruby -v
rvm gemset create rails-5.2.0
rvm gemset use rails-5.2.0 --default
gem install rails -v='5.2.0' --no-rdoc --no-ri
rails -v

```

設定 Github 連線

```
more ~/.ssh/id_rsa.pub
ssh -T git@github.com
```

下載專案
```
git clone git@github.com:vincentopensourcetaiwan/nanhu.git
```

設定專案開發環境

```
cd nanhu/

bundle

rails db:migrate

rails s

```

http://nanhu-nanhu962698.codeanyapp.com:3000/

請 Vincent 將你的 Github 帳號加到專案的合作人

修改首頁

app/views/visitors/index.html.erb

修改完成後，拜訪開發環境網站，驗證是否修改成功

http://nanhu-nanhu962698.codeanyapp.com:3000/

將修改內容存擋，並部署到正式環境

```
git status
git add .
git commit
git push
```

http://nanhu.herokuapp.com/

新增一個報名表功能
```
rails generate scaffold registration_form name:string phone:string
rails db:migrate
```

拜訪開發環境網站，驗證是否成功

http://nanhu-nanhu962698.codeanyapp.com:3000/registration_forms

將修改內容存擋，並部署到正式環境

```
git status
git add .
git commit
git push
```

http://nanhu.herokuapp.com/