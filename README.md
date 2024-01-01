# Run React + TypeScript + Vite in a Docker container

A docker compose YAML file is used to build the image and NodeJS is hardcoded to 21.0.0 (also hardcoded in the .nvmrc file)

(Using Windows and hot reload doesn't work? Uncomment relevant lines from vite.config.ts)

### Start

Build the image on your local machine

```
docker-compose up --build --no-recreate -d
```

Test to see if it's happy

```
docker-compose ps
```

Log into the container and start using it's terminal

```
docker exec -it vite_docker sh
```

Finally, install all needed modules and start the server

```
npm i && npm run dev
```

[Based on]
(https://dev.to/ysmnikhil/how-to-build-with-react-or-vue-with-vite-and-docker-1a3l)

### ReadMe of the official Vite & React build starts here:

## React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
    project: ["./tsconfig.json", "./tsconfig.node.json"],
    tsconfigRootDir: __dirname,
  },
};
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list
