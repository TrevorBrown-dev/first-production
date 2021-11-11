# Step 1
FROM node:16-alpine as builder

WORKDIR /usr/app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

# Step 2
# /usr/app/build <--- This is where the files needed are
FROM nginx
COPY --from=builder /usr/app/build /usr/share/nginx/html
# nginx starts automatically