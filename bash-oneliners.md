# Bash one liners

- Not-so-pretty print jq compact output

  ```bash
  cat foo.json | jq --compact-output | sed 's/{/{ /; s/}/ },/ ; s/:/ : / ; s/,/ , /; $ s/.$//'
  ```
