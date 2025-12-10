# react-chrome-dino-ts

Demo: https://kculmback.github.io/react-chrome-dino-ts/

Install:

```
npm i react-chrome-dino-ts
```

```ts
import React from 'react'
import DinoGame from 'react-chrome-dino-ts'
import 'react-chrome-dino-ts/index.css'

function App() {
  return <DinoGame />
}
```

### Forked from

[react-chrome-dino](https://github.com/mhasbini/react-chrome-dino)

## Deployment

This project is a monorepo. To deploy the example app, you must set the build context to the repository root.

- **Build Context**: `.` (Repository Root)
- **Dockerfile**: `apps/example/Dockerfile`
