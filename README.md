# Kickstarter NativeScript Vue TypeScript

A cross-platform mobile application built with NativeScript, Vue.js 2, and TypeScript.

## Overview

A native mobile application project scaffolding using NativeScript-Vue with TypeScript support. This Kickstarter project explores building cross-platform mobile apps (iOS and Android) using Vue.js as the view layer with NativeScript's native UI components.

## Features

- **Cross-Platform** — Single codebase for iOS and Android
- **Vue.js 2 Integration** — Declarative UI with Vue's reactivity system
- **TypeScript Support** — Full type safety with decorators
- **Vuex State Management** — Centralized reactive state
- **Native UI Components** — Access to platform-native UI widgets
- **Class Component API** — Vue class components with decorators
- **SCSS Styling** — CSS preprocessing with Sass
- **Webpack Build** — NativeScript-dev-webpack for bundling

## Tech Stack

| Category | Technology |
|----------|-----------|
| Framework | NativeScript-Vue (^2.4.0) |
| UI Runtime | NativeScript (tns-core-modules ^6.0.0) |
| Mobile Platforms | tns-android 6.0.0, tns-ios 6.0.1 |
| State Management | Vuex (^3.1.1) |
| Language | TypeScript (^3.2.4) |
| Vue | Vue 2.5.22 |
| Component API | vue-class-component (^7.1.0) |
| Decorators | vue-property-decorator (^8.3.0) |
| Build | Webpack (nativescript-dev-webpack ^1.0.0) |
| CSS | node-sass (^4.9.2) |
| Babel | @babel/core, @babel/preset-env |

## Project Structure

```
Kickstarter-Nativescript-vue-ts/
├── webpack.config.js              # Webpack build configuration
├── babel.config.js                # Babel configuration
├── tsconfig.json                  # TypeScript configuration
├── package.json                   # Dependencies and scripts
├── app/                           # Application source
│   ├── main.ts                    # App entry point
│   ├── app.scss                   # Global styles
│   ├── store.ts                   # Vuex store
│   ├── App_Resources/             # Platform-specific resources
│   │   ├── Android/
│   │   └── iOS/
│   ├── components/                # Vue components
│   ├── assets/                    # Static assets
│   ├── fonts/                     # Custom fonts
│   └── package.json               # App-level package
├── types/                         # TypeScript type declarations
│   ├── references.d.ts            # Type references
│   ├── env.d.ts                   # Environment types
│   └── shims.vue.d.ts             # Vue module shims
├── platforms/                     # Platform build outputs
│   ├── android/
│   └── ios/
└── .gitignore
```

## Installation

```bash
# Install dependencies
npm install

# Add platforms
ns android    # Android
ns ios        # iOS (macOS only)
```

## Usage

### Development

```bash
# Run on Android emulator/device
ns run android

# Run on iOS simulator (macOS only)
ns run ios

# Build for production
ns build android --env.aot --env.snapshot
ns build ios --env.aot
```

### Building

```bash
# Android release build
ns build android --release --env.aot --env.snapshot --env.copyPackagesJson

# iOS release build
ns build ios --release --env.aot --env.strip --env.copyPackagesJson
```

## Development

### TypeScript Configuration

- **Target**: ES5
- **Module**: CommonJS
- **Decorators**: Experimental (ES7)
- **Path Aliases**: `@/*` → `app/*`
- **Type Roots**: `types/` directory
- **Source Maps**: Enabled

### Key Configuration

- **App ID**: `org.nativescript.application`
- **Template Version**: v2
- **Library Resolution**: Node-style module resolution

### Vue Component Pattern

```typescript
import { Component, Vue } from 'vue-property-decorator'
import { Vuex, State } from 'vuex'

@Component
export default class MyComponent extends Vue {
  @State state: any

  get computedValue() {
    return this.state.someValue
  }

  onClick() {
    // NativeScript UI interactions
  }
}
```

## License

MIT
