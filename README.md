[![](https://dcbadge.vercel.app/api/server/8NJR3zQU5X?compact=true&style=flat)](https://discord.gg/8NJR3zQU5X) [![Twitter](https://img.shields.io/twitter/url.svg?label=Follow%20%40dust4ai&style=social&url=https%3A%2F%2Ftwitter.com-dust4ai)](https://twitter.com/dust4ai)

# [Dust](https://dust.tt)

Design and Deploy Large Language Model Apps

## :book: Documentation Portal

- [LLM apps Primer](https://docs.dust.tt/introduction)
- [Platform overview](https://docs.dust.tt/overview)
- [Blocks documentation](https://docs.dust.tt/core-blocks)
- [Getting started guide](https://docs.dust.tt/quickstart)
- [Runs API Reference](https://docs.dust.tt/runs)

### Questions / Help

Join our [Discord](https://discord.gg/8NJR3zQU5X).

## :computer: Run Dust locally

### Command-line Client Quick Start

- [Install Rust](https://www.rust-lang.org/tools/install)
- Clone this repository (`$DUST_PATH` represents the path to the `dust` repository).
- `cd $DUST_PATH/core`
- `cargo build --release --bin dust`
- `alias dust="$DUST_PATH/core/target/release/dust"`
- `dust init new_test_project`
- `cd new_test_project`
- `dust help`

See the [video demo](https://demo.dust.tt) for an explanation of the commands.

### Run Dust Web App Locally Quick Start

- [Install Rust](https://www.rust-lang.org/tools/install)
- [Install Node](https://nodejs.org/en/download/)
- Clone this repository (`$DUST_PATH` represents the path to the `dust` repository).

#### Start core API on SQLite

1. `cd $DUST_PATH/core`
2. `cargo run --bin dust-api`

#### Start front on SQLite

1. `cd $DUST_PATH/front`
2. Create `.env.local` by running the command below:

```sh
cat <<EOF >> .env.local
URL=http://localhost:3000

NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=25da29db5485fcd27d2f671c5e28d5df8f325e9470c36cb6bf0a9d19c662255a

FRONT_DATABASE_URI=sqlite:front_store.sqlite
XP1_DATABASE_URI=sqlite:xp1_store.sqlite

GITHUB_ID=47ec837fcbac1c6f1690
GITHUB_SECRET=d59af0da231fc697d7dd8d3002ed1d9765e11c7f

DUST_API=http://localhost:3001

THUM_IO_KEY=0-Foo
GA_TRACKING_ID=Foo
EOF
```

3. Run `npm install`
4. Run `XP1_DATABASE_URI=sqlite:xp1_store.sqlite FRONT_DATABASE_URI=sqlite:front_store.sqlite ./init/init.sh`
5. Start server with `npm run dev`
