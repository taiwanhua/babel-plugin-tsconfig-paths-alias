## Babel plugin for resolving path aliases from `tsconfig.json`

## Fork from [babel-plugin-tsconfig-paths](https://github.com/Js-Brecht/babel-plugin-tsconfig-paths)
but fix the correct file extensions 

### Install

```sh
npm install -D babel-plugin-tsconfig-paths
```

### Configure

```json
// .babelrc
{
  "plugins": [
    [
      "babel-plugin-tsconfig-paths-alias",
      {
        "relative": true,
        "extensions": [
          ".js",
          ".jsx",
          ".ts",
          ".tsx",
          ".es",
          ".es6",
          ".mjs"
        ],
        "rootDir": ".",
        "tsconfig": "tsconfig.json",
        "transformFunctions": [
          "require",
          "require.resolve",
          "System.import",
          "jest.genMockFromModule",
          "jest.mock",
          "jest.unmock",
          "jest.doMock",
          "jest.dontMock",
          "jest.setMock",
          "require.requireActual",
          "require.requireMock"
        ]
      }
    ]
  ]
}
```

* `relative` : Generate relative paths instead of absolute paths when
  converting aliased import paths.
  * Default: `true`

* `extensions` : Which file extensions to resolve.
  * Default: `[".js", ".jsx", ".ts", ".tsx", ".es", ".es6", ".mjs"]`

* `rootDir` : Where to look for `tsconfig.json`.
  * Default: `process.cwd()`

* `tsconfig`: Relative/absolute location of `tsconfig.json`
  * Default: `./tsconfig.json`

* `transformFunctions` : Which functions to transform aliases in
  * Default:

    ```json
    [
      "require",
      "require.resolve",
      "System.import",
      "jest.genMockFromModule",
      "jest.mock",
      "jest.unmock",
      "jest.doMock",
      "jest.dontMock",
      "jest.setMock",
      "require.requireActual",
      "require.requireMock"
    ]
    ```
