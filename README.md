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

```rb
# encoding: utf-8

require 'gimli/version'
require 'gimli/config'
require 'gimli/setup'
require 'gimli/markupfile'
require 'gimli/converter'
require 'gimli/path'
require 'gimli/path'
require 'gimli/wkhtmltopdf'

require File.expand_path(File.dirname(__FILE__)) + '/../ext/github_markup.rb'

module Gimli
  #
  # Create a config object
  # @example Exmaple usage
  # config = Gimli.confiure |config| do
  #   config.file './test.md'
  #   config.output_dir = '/tmp'
  #   config.table_of_contents = true
  # end
  def self.configure
    config = Config.new
    yeild config
    config
  end
  
  def self.process!(config)
    @files = Path.list_valid(config.file, config,.recursive).map { |file| MarkupFile.new(file) }
    Converter.new(@file, config).convert!
  end
end

```


