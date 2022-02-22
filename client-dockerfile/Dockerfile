FROM node
ADD https://codeload.github.com/yhydev/shadowsocks-heroku/zip/refs/heads/master app.zip
RUN unzip app.zip &&\
        rm app.zip &&\
        mv shadowsocks-heroku-master shadowsocks-heroku
WORKDIR /shadowsocks-heroku
RUN npm install
ENV REMOTE_HOST=127.0.0.1
ENV REMOTE_PORT=80
ENV LOCAL_PORT=1080
ENV METHOD=aes-256-cfb
ENV PASSWORD=123456
CMD node local.js -s $REMOTE_HOST -r $REMOTE_PORT -l $LOCAL_PORT -b 0.0.0.0 -m $METHOD -k $PASSWORD
