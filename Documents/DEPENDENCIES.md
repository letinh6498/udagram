## Dependencies

### Dependencies

```
- Node v14.15.5

- npm 6.14.11 or above

- AWS CLI v2

- Elastic Beanstalk CLI v3.0 or above

- A RDS database running Postgres.

- A S3 bucket for hosting uploaded pictures.

```

### udagram-api

```json
{
  "name": "udagram-api",
  "version": "2.0.0",
  "description": "",
  "main": "server.ts",
  "engines": {
    "node": "14.15"
  },
  "scripts": {
    "start": "node ./www/server.js",
    "tsc": "npx tsc",
    "dev": "npx ts-node-dev --respawn --transpile-only ./src/server.ts",
    "prod": "npx tsc && node ./www/server.js",
    "clean": "rm -rf www/ || true",
    "deploy": "npm run build && chmod +x ./bin/deploy.sh && ./bin/deploy.sh",
    "build": "npm install . && npm run clean && tsc && cp -rf src/config www/config && cp -R .elasticbeanstalk www/.elasticbeanstalk && cp .npmrc www/.npmrc && cp package.json www/package.json && cd www && zip -r Archive.zip . && cd ..",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "Gabriel Ruttner",
  "license": "ISC",
  "dependencies": {
    "@types/bcryptjs": "2.4.2",
    "@types/jsonwebtoken": "^8.3.2",
    "aws-sdk": "^2.429.0",
    "bcryptjs": "2.4.3",
    "body-parser": "^1.18.3",
    "cors": "^2.8.5",
    "email-validator": "^2.0.4",
    "express": "^4.16.4",
    "jsonwebtoken": "^8.5.1",
    "pg": "^8.7.1",
    "reflect-metadata": "^0.1.13",
    "sequelize": "^6.26.0",
    "sequelize-typescript": "^2.1.5"
  },
  "devDependencies": {
    "@types/bluebird": "^3.5.26",
    "@types/cors": "^2.8.6",
    "@types/express": "^4.16.1",
    "@types/node": "^11.11.6",
    "@types/sequelize": "^4.28.14",
    "@types/validator": "^13.7.10",
    "@typescript-eslint/eslint-plugin": "^2.19.2",
    "@typescript-eslint/parser": "^2.19.2",
    "chai": "^4.2.0",
    "chai-http": "^4.2.1",
    "dotenv": "^16.3.1",
    "eslint": "^6.8.0",
    "eslint-config-google": "^0.14.0",
    "mocha": "^6.1.4",
    "ts-node-dev": "^1.0.0-pre.32",
    "typescript": "^4.2.3"
  }
}

```

### udagram-frontend

```json
{
  "name": "udagram-frontend",
  "version": "0.0.1",
  "author": "Ionic Framework",
  "homepage": "https://ionicframework.com/",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "deploy": "npm install -f && npm run build && chmod +x ./bin/deploy.sh && ./bin/deploy.sh",
    "test": "ng test --watch=false",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "private": true,
  "dependencies": {
    "@angular/common": "^8.2.14",
    "@angular/core": "^8.2.14",
    "@angular/forms": "^8.2.14",
    "@angular/http": "^7.2.16",
    "@angular/platform-browser": "^8.2.14",
    "@angular/platform-browser-dynamic": "^8.2.14",
    "@angular/router": "^8.2.14",
    "@ionic-native/core": "^5.0.0",
    "@ionic-native/splash-screen": "^5.0.0",
    "@ionic-native/status-bar": "^5.0.0",
    "@ionic/angular": "^4.1.0",
    "core-js": "^2.5.4",
    "rxjs": "~6.5.4",
    "zone.js": "~0.9.1"
  },
  "devDependencies": {
    "@angular-devkit/architect": "~0.12.3",
    "@angular-devkit/build-angular": "^0.803.24",
    "@angular-devkit/core": "~7.2.3",
    "@angular-devkit/schematics": "~7.2.3",
    "@angular/cli": "~8.3.25",
    "@angular/compiler": "~8.2.14",
    "@angular/compiler-cli": "~8.2.14",
    "@angular/language-service": "~8.2.14",
    "@ionic/angular-toolkit": "~1.4.0",
    "@types/jasmine": "~2.8.8",
    "@types/jasminewd2": "~2.0.3",
    "@types/node": "~10.12.0",
    "@typescript-eslint/eslint-plugin": "^2.20.0",
    "@typescript-eslint/parser": "^2.20.0",
    "codelyzer": "~4.5.0",
    "jasmine-core": "~2.99.1",
    "jasmine-spec-reporter": "~4.2.1",
    "karma": "~3.1.4",
    "karma-chrome-launcher": "~2.2.0",
    "karma-coverage-istanbul-reporter": "~2.0.1",
    "karma-jasmine": "~1.1.2",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.4.0",
    "ts-node": "~8.0.0",
    "tslint": "~5.12.0",
    "typescript": "3.5.3"
  },
  "description": "An Ionic project"
}

```