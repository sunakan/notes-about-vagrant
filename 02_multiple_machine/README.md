## 複数VMの相互通信

- DBプロビジョニング
  - `export DEBIAN_FRONTEND=noninteractive`
    - MySQLサーバをインストールする際に、rootのパスワードを尋ねられない
  - `sed -i -e "s/127.0.0.1/0.0.0.0/" /etc/mysql/my.cnf`
    - sedを使ってバインドするアドレスをループバックから
    - 全てのインターフェースを意味する0.0.0.0に変更

#### web側VMからdb側VMにアクセス

```
$ mysql -u root -h 192.168.34.11 -p'root'
```
