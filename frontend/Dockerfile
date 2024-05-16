# ベースイメージとしてNode.jsを使用
FROM node:16-alpine

# 作業ディレクトリを設定
WORKDIR /app

# パッケージ関連のファイルをコピー
COPY package.json package-lock.json ./

# 依存関係をインストール
RUN npm install

# アプリケーションのソースコードをコピー
COPY . .

# ビルド
RUN npm run build

# nginxを使用してビルドされたアプリケーションを提供
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
