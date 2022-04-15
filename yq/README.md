```
$ yq -y '.' sample.json 
Samples:
  - name: keigo
    topics: Learning infrastructure
  - name: taro
    nickname: momo
  - name: eri
    hobbies: reading book
$ yq -y '.' sample.json > sample.yml
Samples:
  - name: keigo
    topics: Learning infrastructure
  - name: taro
    nickname: momo
  - name: eri
    hobbies: reading book
$ yq -y '.Samples[].name' sample.yml
keigo
--- taro
--- eri
...
$ yq -y '.Samples[].name |= . + "-san"' sample.yml > sample-san.yaml
Samples:
  - name: keigo-san
    topics: Learning infrastructure
  - name: taro-san
    nickname: momo
  - name: eri-san
    hobbies: reading book
$ yq -y '.Samples[]' | select(.name == "keigo")' sample.yml
name: keigo
topics: Learning infrastructure
```
