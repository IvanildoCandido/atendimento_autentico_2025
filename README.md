backend

docker run -d \
  --name postgres-db \
  -e POSTGRES_USER=postgres \
  -e POSTGRES_PASSWORD=Admin33Admin77 \
  -e POSTGRES_DB=whaticket \
  -p 5434:5432 \
  postgres:13

docker run -d \
  --name redis \
  -p 6379:6379 \
  redis:alpine \
  redis-server --requirepass "123456"

npm run build
npx sequelize db:migrate
npx sequelize db:seed:all
frontend
npm install --force
npm run build