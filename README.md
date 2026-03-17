# LynxJS Cross-Platform

A project setup for building web and mobile applications using LynxJS.

[![Stars Badge](https://img.shields.io/github/stars/KadenHD/lynxjs-crossplatform)](https://github.com/KadenHD/lynxjs-crossplatform/stargazers)
[![Forks Badge](https://img.shields.io/github/forks/KadenHD/lynxjs-crossplatform)](https://github.com/KadenHD/lynxjs-crossplatform/network/members)
[![License Badge](https://img.shields.io/github/license/KadenHD/lynxjs-crossplatform?color=2b9348)](https://github.com/KadenHD/lynxjs-crossplatform/blob/master/LICENSE)

## Requirements

- Node.js >= 18
- npm

## Installation

```sh
npm install
```

## Scripts

### Building

- **Build All (Mobile, Client and Desktop App):**

  ```sh
  npm run build
  ```

  This runs the `build:mobile` and `build:client` scripts concurrently.

- **Build Mobile App:**

  ```sh
  npm run build:mobile
  ```

  Uses `rspeedy` to build the mobile app with the configuration file `./config/lynx.mobile.ts`.

- **Build Client App:**

  ```sh
  npm run build:client
  ```

  Uses `rspeedy` and `rsbuild` to build the web and client apps with the configuration files `./config/lynx.web.ts` and `./config/lynx.client.ts`.

  - **Build Desktop App:**

  ```sh
  npm run build:app
  ```

  Builds the web app, then builds the Electron client using `./config/lynx.app.ts`, and packages it using `electron-builder`.

### Development

- **Develop Mobile App:**

  ```sh
  npm run dev:mobile
  ```

  Uses `rspeedy` to start a dev server with hot-reloading using `./config/lynx.mobile.ts`.

- **Develop Client App:**

  ```sh
  npm run dev:client
  ```

  Uses `concurrently` to watch changes and rebuild the web app with `rspeedy` and start a client dev server with `rsbuild`.

> [!NOTE]
> It will use the `build/web` distribution.

- **Develop Desktop App:**

  ```sh
  npm run dev:app
  ```

  Watches and rebuilds the web source if needed, then launches the Electron app with the bundled web assets.

> [!NOTE]
> It will use the `build/web` distribution.

### Preview

- **Preview Mobile App:**

  ```sh
  npm run preview:mobile
  ```

  Builds the mobile app and serves it using `rspeedy` with `./config/lynx.mobile.ts`.

- **Preview Client App:**

  ```sh
  npm run preview:client
  ```

> [!IMPORTANT]
> If you're using your distribution to host it, keep in mind that the `output.assetPrefix` is set to '/'. If you configure your client with a sub-path, make sure to update the `output.assetPrefix` in the [lynx.client.ts](./config/lynx.client.ts) config file to match the new route.
> For example, if your route is `https://example.com/app`, you should set `output.assetPrefix` to '/app'.

  Builds the client app and serves it using `rsbuild` with `./config/lynx.client.ts`.

> [!NOTE]
> It will use the `build/client` distribution.

### Code Quality

- **Check Code Quality and Apply Fixes:**

  ```sh
  npm run check
  ```

  Uses `biome` to lint and apply fixes to the codebase.

- **Format Code:**

  ```sh
  npm run format
  ```

  Formats code using `biome`.

## Dependencies

- **React (v19.1.0) & ReactDOM (v19.1.0):** React framework for building UI.
- **@lynx-js/react, @lynx-js/web-core, @lynx-js/web-elements:** LynxJS libraries for creating web and mobile apps.

## Dev Dependencies

- **@biomejs/biome:** Linting and formatting tool.
- **@lynx-js/qrcode-rsbuild-plugin, @lynx-js/react-rsbuild-plugin:** Plugins for enhancing LynxJS build.
- **electron:** Enables building cross-platform desktop apps using web technologies via Chromium and Node.js.
- **electron-builder:** Packages and distributes Electron apps for Windows, macOS, and Linux with custom icons and configurations.
- **@lynx-js/rspeedy:** Tool for faster builds.
- **@rsbuild/core, @rsbuild/plugin-react:** Build system components.
- **Concurrently:** Tool for running multiple commands concurrently.
- **Nodemon:** For auto-restarting the server during development.
- **TypeScript:** Type checking and static analysis.

## Star History

[![Star History Chart](https://api.star-history.com/image?repos=KadenHD/lynxjs-crossplatform&type=date&legend=top-left)](https://www.star-history.com/?repos=KadenHD%2Flynxjs-crossplatform&type=date&legend=top-left)

