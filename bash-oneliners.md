# JSON

Not-so-pretty print jq compact output

cat foo.json | jq --compact-output | sed 's/{/{ /; s/}/ },/ ; s/:/ : / ; s/,/ , /; $ s/.$//'