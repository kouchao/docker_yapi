FROM keymetrics/pm2:latest-alpine
ADD ./src /usr/src/yapi/src
ADD ./config.json /usr/src/yapi/src/config.json
ADD ./pm2.json /usr/src/yapi/src/pm2.json

WORKDIR /usr/src/yapi/src
RUN npm install --production --registry https://registry.npm.taobao.org

EXPOSE 3000

# CMD ["pm2-runtime", "start", "pm2.json", "--web"]
CMD npm run install-server && pm2-runtime start pm2.json --web