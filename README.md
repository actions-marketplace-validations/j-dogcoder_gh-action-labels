# Issue labels generator

Adds labels used by j-dogcoder

# WARNING:
Will delete previous labels.

## Usage

To use this Action, you only need the yaml file below.

```yaml
name: Import open source standard labels

on:
  push:
    branches: [ main ]

jobs:
  labels:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/setup-node@v2
      with:
        node-version: '14'
    - uses: j-dogcoder/gh-action-labels@main
      with:
        github-token: ${{ secrets.GITHUB_TOKEN }}
        owner-name: ${{ github.repository_owner }}
        repository-name: ${{ github.event.repository.name }}
```

## Contributing to this project

To add a new label, update the `labels.json` file and the GitHub Action will do the rest for everyone!

```json
[
    {
        "name": "good first issue",
        "color": "7f0799"
    },
    {
        "name": "💬 talk: discussion",
        "color": "f9bbe5"
    } 
]
```

> This example shows two common ways to add a label. One without emoji and the other with emoji. Preferred way is the one with emoji at the beginning but there are also some labels which are commonly used without emojis.
