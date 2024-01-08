# lowercase-action

Action to lower an input.

Input accepted is `text`


## Usage

```
on:
  push:
    branches:
      - main
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    name: A test job for tr
    steps:
    - name: Checkout
      uses: actions/checkout@v4
      with:
        fetch-depth: 1
    - name: Test just output the message
      uses: to-lowercase
      id: lowered
      with:
        text: |
          Hello DevOps
    - name: Debug our lowered text message
      run: echo "${{ steps.lowered.outputs.text }}"
```
