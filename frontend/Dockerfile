FROM node:18
WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install

COPY . .
RUN npm run build

# This command will start a built-in server on Node.js, which will provide
# the contents of the /app/build directory on port 8000
CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]