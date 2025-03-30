FROM nginx:1.15.8

# インクルード用のディレクトリ内を削除
RUN rm -f /etc/nginx/conf.d/*

WORKDIR /etc/nginx
RUN mkdir -p /var/www/sample/current \
  /var/log/nginx/api.local.sample.jp:80

RUN chmod 755 /var/www/sample/current
# ADD ./api-nonssl.conf conf.d/api-nonssl.conf
# ADD ./api-ssl.conf conf.d/api-ssl.conf

# Nginxの設定ファイルをコンテナにコピー
ADD nginx.conf /etc/nginx/conf.d/myapp.conf

# RUN ln -s /dev/stdout /var/log/nginx/api.local.sample.jp:80/access.log && \
#   ln -s /dev/stdout /var/log/nginx/api.local.sample.jp:80/error.log

EXPOSE 80

# ビルド完了後にNginxを起動
CMD /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf
