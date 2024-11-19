# folder
frontend is plinko game by vue3 vite

backend is api by node js, to post start drop ball position to frontend

try to use docker compose to run both

use "docker-compose up -d --build"

## docker compose build cmd

docker-compose --env-file ./frontend/.env.development up --build -d // when build compose, just take env from frontend folder's env file, when want to run development, tap development

docker-compose --env-file ./frontend/.env.production up --build -d  // when want to run production, tap production
