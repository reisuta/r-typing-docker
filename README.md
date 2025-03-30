## 環境構築
```
git submodule update --init
git submodule foreach bash -c 'git checkout main && git pull origin main'
```
を実行してから
```
docker-compose build && docker-compose up -d
```
実行する
