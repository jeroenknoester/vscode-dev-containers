# Node.js, TypeScript & Angular

## Summary

*Develop Node.js based applications in TypeScript. Includes Node.js, eslint, nvm, yarn, the TypeScript compiler and the Angular CLI preinstalled.*

| Metadata | Value |  
|----------|-------|
| *Contributors* | The VS Code Team |
| *Definition type* | Dockerfile |
| *Published image* | mcr.microsoft.com/vscode/devcontainers/typescript-node |
| *Available image variants* | 10, 12, 14 |
| *Published image architecture(s)* | x86-64 |
| *Works in Codespaces* | Yes |
| *Container host OS support* | Linux, macOS, Windows |
| *Container OS* | Debian |
| *Languages, platforms* | Node.js, TypeScript |

## Using this definition with an existing folder

While the definition itself works unmodified, you can select the version of Node.js the container uses by updating the `VARIANT` arg in the included `devcontainer.json` (and rebuilding if you've already created the container).

```json
"args": { "VARIANT": "14" }
```

You can also directly reference pre-built versions of `.devcontainer/base.Dockerfile` by using the `image` property in `.devcontainer/devcontainer.json` or updating the `FROM` statement in your own `Dockerfile` with one of the following:

- `mcr.microsoft.com/vscode/devcontainers/typescript-node` (latest)
- `mcr.microsoft.com/vscode/devcontainers/typescript-node:14`
- `mcr.microsoft.com/vscode/devcontainers/typescript-node:12`
- `mcr.microsoft.com/vscode/devcontainers/typescript-node:10`


Version specific tags tied to [releases in this repository](https://github.com/microsoft/vscode-dev-containers/releases) are also available.

- `mcr.microsoft.com/vscode/devcontainers/typescript-node:0-14`
- `mcr.microsoft.com/vscode/devcontainers/typescript-node:0.123-14`
- `mcr.microsoft.com/vscode/devcontainers/typescript-node:0.123.0-14`

Alternatively, you can use the contents of the `Dockerfile` or the JavaScript and Node.js `Dockerfile`[in Microsoft's github](https://github.com/microsoft/vscode-dev-containers/tree/master/containers/javascript-node) to fully customize your container's contents.

Beyond TypeScript, Node.js, the Angular CLI and `git`, this image / `Dockerfile` includes `eslint`, `zsh`, [Oh My Zsh!](https://ohmyz.sh/), a non-root `vscode` user with `sudo` access, and a set of common dependencies for development. It also installs `tslint` globally and includes the VS Code TSLint extension for backwards compatibility, but [TSLint has been deprecated](https://github.com/palantir/tslint/issues/4534) in favor of ESLint, so `eslint` and its corresponding extension has been included as well.

Note that, while `eslint`and `typescript` are installed globally for convenance, but [as of ESLint 6](https://eslint.org/docs/user-guide/migrating-to-6.0.0#-plugins-and-shareable-configs-are-no-longer-affected-by-eslints-location), you will need to install the following packages locally to lint TypeScript code: `@typescript-eslint/eslint-plugin`, `@typescript-eslint/parser`, `eslint`, `typescript`.

### Adding the definition to your project

Just follow these steps:

1. If this is your first time using a development container, please follow the [getting started steps](https://aka.ms/vscode-remote/containers/getting-started) to set up your machine.

2. To use the Dockerfile for this definition (*rather than the pre-built image*):
   1. Clone this repository.
   2. Copy the contents of `containers/javascript-node-angular/.devcontainer` to the root of your project folder.
   3. Start VS Code and open your project folder.

3. After following step 2 or 3, the contents of the `.devcontainer` folder in your project can be adapted to meet your needs.

4. Finally, press <kbd>F1</kbd> and run **Remote-Containers: Reopen Folder in Container** to start using the definition.
