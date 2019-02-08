# Bash one liners

- Not-so-pretty print jq compact output. Useful for using this output in a text file where you want to keep some 'prettyness'

  ```bash
  cat foo.json | jq --compact-output | sed 's/{/{ /; s/}/ },/ ; s/:/ : / ; s/,/ , /; $ s/.$//'
  ```
