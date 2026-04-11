# all-contributors-image

Generates a contributors image (`contributors.png`) from the `.all-contributorsrc` file and opens a pull request with the updated image.

## What it does

- Fetches `.all-contributorsrc` from the repository
- Extracts contributor avatars
- Generates a grid image (`contributors.png`)
- Creates/updates a branch
- Commits the image
- Opens a pull request

## Usage

```yaml
name: Generate Contributors Image

on:
  push:
    paths:
      - .all-contributorsrc

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - name: Generate contributors image on main branch
        uses: processing/all-contributors-image@v1
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| name   | required | description                                                                          |
| ------ | -------- | ------------------------------------------------------------------------------------ |
| token  | yes      | github token used for api calls                                                      |

## Requirements

Repository must have:

- A valid `.all-contributorsrc` file
