<!-- name: Vale Lint

on:
  pull_request:
  push:
    branches:
      - main
      - develop  # Include other branches if needed

jobs:
  vale-lint:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Install Vale
        run: |
          wget https://github.com/errata-ai/vale/releases/download/v3.8.0/vale_3.8.0_Linux_64-bit.tar.gz -O vale.tar.gz
          tar -xf vale.tar.gz
          sudo mv vale /usr/local/bin/

      - name: Run Vale
        run: |
          vale .
        continue-on-error: true  # Optional: allows the workflow to continue even if Vale finds errors -->
