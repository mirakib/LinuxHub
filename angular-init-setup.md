# Frontend Setup Guide (Node.js + Angular)

This guide explains how to install Node.js (LTS), set up an Angular project, and prepare it for Dockerization.


## Phase 01: Install Node.js 20+ Using NVM

### 1. Install NVM (Node Version Manager)

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash`

### 2. Load NVM into the current session

```source ~/.bashrc```

### 3. Install the latest Node.js LTS version

`nvm install --lts`

### 4. Verify installation

`node -v`
`npm -v`

## Phase 02: Create and Run an Angular Project

### 1. Install Angular CLI globally
`npm install -g @angular/cli`

### 2. Create a new Angular application
`ng new angular-docker-app --style=scss --routing=false`

### 3. Move into the project directory
`cd angular-docker-app`

### 4. Install project dependencies (if needed)

Angular CLI usually installs them automatically, but you can run:

`npm install`

### 5. Start the Angular development server
`ng serve`


## Phase 03 — Build Angular Project for Production

`ng build --configuration production`

This generates a production build inside:

`dist/angular-docker-app/`

