# vue-test-utils-typescript-example

> Example project using TypeScript, Jest + vue-test-utils together

This is based on the `vue-cli` 3 `basic` template. Test-specific changes include:

### Additional Dependencies

- `vue-test-utils`
- `jest`
- `ts-jest` (for TypeScript compilation in tests)
- `vue-jest` (for handling `*.vue` files in tests)
- `jest-serializer-vue` (for snapshot tests)

### Additional Configuration

#### `package.json`

The following configurations are recommended for Jest:

``` js
{
  "jest": {
    "moduleFileExtensions": [
      "js",
      "json",
      "ts",
      // tell Jest to handle *.vue files
      "vue"
    ],
    "transform": {
      // process TypeScript files
      "^.+\\.ts$": "ts-jest",
      // process *.vue files with vue-jest
      ".*\\.(vue)$": "vue-jest"
    },
    // support the same @ -> src alias mapping in source code
    "moduleNameMapper": {
      "^@/(.*)$": "<rootDir>/src/$1"
    },
    // serializer for snapshots
    "snapshotSerializers": [
      "jest-serializer-vue"
    ]
  }
}
```

### Build Commands

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# run tests
npm test
```