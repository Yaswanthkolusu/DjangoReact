FROM node:18 AS build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build
 
# Step 2: Serve with serve (Node.js static server)
FROM node:18
WORKDIR /app
RUN npm install -g serve
COPY --from=build /app/build .
EXPOSE 3000
CMD ["serve", "-s", ".", "-l", "3000"]
