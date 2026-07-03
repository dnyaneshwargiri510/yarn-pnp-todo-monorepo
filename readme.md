my-monorepo/
├── .yarn/
│   └── cache/             # Where the zipped dependencies actually live
├── .pnp.cjs               # The PnP lookup map (replaces node_modules)
├── .yarnrc.yml            # Yarn configuration file
├── package.json           # Root configuration specifying workspaces
├── packages/
│   ├── todo-core/         # Shared business logic
│   │   ├── package.json
│   │   └── index.js
│   └── todo-web/          # Frontend app utilizing todo-core
│       ├── package.json
│       └── app.js

npx @yarnpkg/cli-dist set version stable
sudo corepack enable
yarn set version stable

yarn workspace @todo/web node test.js
yarn workspace @todo/web add -D vite
yarn workspace @todo/web dev
git remote set-url origin git@github-transperfect:dnyaneshwargiri510/yarn-pnp-todo-monorepo.git