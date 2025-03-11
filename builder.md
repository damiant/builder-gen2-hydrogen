# Setup for Hydrogen

`npm install @builder.io/dev-tools --save-dev`
`npm install @builder.io/sdk-react --save-dev`
`npm install concurrently --save-dev`

Edit `vite.config.js` and add:
```Typescript
import {builderDevTools} from '@builder.io/dev-tools/vite';
...
plugins: [
    ...
    builderDevTools()
]
```

In `.env` add:
```bash
REACT_APP_PUBLIC_BUILDER_KEY=<YOUR_BUILDER_API_KEY>
```

## Running
Typically we would run Builder dev tools and `npm run dev` together using concurrently but this does not work ([Ticket](https://builder-io.atlassian.net/browse/ENG-8295))

Instead edit `package.json` and create an entry:
```json
    "dev-tools": "builder-dev-tools",
```

In one terminal do `npm run dev` and in another do `npm run dev-tools`.



