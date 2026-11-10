# FE テンプレート (2026/11/11)

React + Vite + Tailwind CSS のフロントエンド用テンプレートです。

## Tech Stack

### Frontend

- **React 19.3** - UI Library
- **React Router 7.18** - Routing
- **TypeScript 7.0** - Type-safe Development

### Styling

- **Tailwind CSS 4.3** - Utility-first CSS Framework

### Build Tools

- **Vite 8.3** - Fast Build Tool
- **@vitejs/plugin-react-swc 4.3** - SWC-based React Plugin

### Code Quality

- **Biome 2.6** - Linter & Formatter
- **Lefthook 2.2** - Git Hook Manager（pre-commit で Biome を実行）

## Setup

Node.js 24 / pnpm を前提にしています。

```bash
pnpm install

# Git hook（pre-commit で Biome）を有効化
pnpm exec lefthook install
```

`pnpm-workspace.yaml` の `allowBuilds` で lefthook の postinstall を止めているため、hook は上記コマンドで手動インストールしてください。

## Scripts

```bash
# Start development server
pnpm dev

# Build
pnpm build

# Lint & Format
pnpm lint

# Preview
pnpm preview
```

## Path Alias

`@/` は `src/` を指します（`vite.config.ts` と `tsconfig.*.json` の `paths` で設定）。

```ts
import App from "@/App";
```

## Notes

- `react` と `react-dom` はバージョンを完全一致させる必要があります（ずれると実行時に `Incompatible React versions` エラーになります）。Dependabot は `groups` で両方を同じ PR で上げる設定にしています。
- 環境変数は `.env.sample` を参考に `.env` を作成してください（Vite では `VITE_` から始まる変数だけがクライアントに公開されます）。
