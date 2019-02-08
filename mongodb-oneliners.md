# mongodb

- Extract directly from a unencrypted .tgz archived mongodb backup. Useful if the backup is a huge 15GB file you don't want to decompress or don't have the storage available to deflate it or untar it in two steps. `bsondump` is part of the `mongodb-tools` package

  ```bash
  zcat foo.tgz | tar -x -O -f - | bsondump > foo.json
  ```

  You can also grep at the end to filter the output

  ```bash
  zcat foo.tgz | tar -x -O -f - | bsondump | grep '"key":"bar"' > foo.json
  ```

- Date format in mongoexport (tested up to 3.6.10)

  ```javascript
  { myDate : { $gt: { '$date' : '2019-01-01T00:00:00.000Z' } } }
  ```

  Instead of default mongodb shell

  ```javascript
  { myDate : { $gt: ISODate('2019-01-01T00:00:00.000Z') } }
  ```