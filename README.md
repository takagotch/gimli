### gimli
---
https://github.com/walle/gimli

```
gem install gimli
cd gimli/
bundle
rake install

gimli
gimli -f doc-file.md -cover cover-file.md
gimli -f test.md -w '--toc --footer-right "[page]/[toPage]"'

docker run -v <host_dir>:<container_dir> walle/gimli -f <container_dir>/my-file.md -o <container_dir>
docker run -v <host_dir>:<container_dir> walle/gimli -f <container_dir>/my-file.md -o /tmp/gimli/
```

```ruby
def foo
  puts 'bar'
end
```

```
```


