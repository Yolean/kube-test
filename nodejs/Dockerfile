FROM yolean/node@sha256:2ff7743b00a5f1b2f9ca1ad426a081b663783f932461367e9db25155113ea135

RUN npm install -g \
  mocha@4.0.1 \
  chai@4.1.2 \
  kubernetes-client@3.16.0

WORKDIR /
ENTRYPOINT [ "mocha", "--watch" ]