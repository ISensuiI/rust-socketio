FROM node:12.18.1
WORKDIR /test
COPY . ./

# 使用 sed 转换所有 shell 脚本的行尾符(从 CRLF 到 LF)
RUN find . -name "*.sh" -type f -exec sed -i 's/\r$//' {} \;

RUN cp cert/ca.crt /usr/local/share/ca-certificates/ && update-ca-certificates

RUN npm install

RUN chmod u+x start_test_server.sh
CMD ./start_test_server.sh