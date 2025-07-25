setup-dotenvx
================

Set up your GitHub Actions workflow with dotenvx cli.

# Usage

Please add `uses: linux-china/setup-dotenvx@main` to your workflow file to set up dotenvx CLI,
and add `DOTENV_PRIVATE_KEY` secret to the `Repository secrets`.

Example workflow file to use dotenvx cli:

```yaml
jobs:
  dotenvx-demo:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: linux-china/setup-dotenvx@main
      - run: npm install
      - run: $HOME/.cargo/bin/dotenvx run -- node index.js
        env:
          DOTENV_PRIVATE_KEY: ${{ secrets.DOTENV_PRIVATE_KEY }}
```

# References

* [dotenvx](https://github.com/linux-china/dotenvx-rs): Dotenvx Rust SDK/CLI to manage .env files safely.
* [Creating a composite action](https://docs.github.com/en/actions/tutorials/creating-a-composite-action) 
