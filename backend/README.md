# Plinko backend project by node js

you can run the project by the following step:

- npm i // install all dependent 
- npm run build // build project to dist
- npm start // run project from dist

## How to create a node js project with typescript?

- npm i --save-dev typescript @types/express @types/node @types/cors
- npm i --save express cors dotenv // install dotenv that sure node js application reads the environment variables from the .env file
- npx tsc --init
- adjust tsconfig.json's outDir to './dist'
- git init
- create .gitignore file, add context to ignore node_modules and dist

## docker build and run cmd

on backend folder to run these cmd

docker build -t plinko-backend

docker run -it -p 3000:3000
