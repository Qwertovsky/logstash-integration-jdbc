# logstash-integration-jdbc
Logstash Integration Plugin for JDBC, including Logstash Input and Filter Plugins
# Logstash Plugin

[![Travis Build Status](https://travis-ci.com/logstash-plugins/logstash-integration-jdbc.svg)](https://travis-ci.com/logstash-plugins/logstash-integration-jdbc)

This is a plugin for [Logstash](https://github.com/elastic/logstash).

It is fully free and fully open source. The license is Apache 2.0, meaning you are pretty much free to use it however you want in whatever way.

## Documentation

Logstash provides infrastructure to automatically generate documentation for this plugin. We use the asciidoc format to write documentation so any comments in the source code will be first converted into asciidoc and then into html. All plugin documentation are placed under one [central location](http://www.elastic.co/guide/en/logstash/current/).

- For formatting code or config example, you can use the asciidoc `[source,ruby]` directive
- For more asciidoc formatting tips, see the excellent reference here https://github.com/elastic/docs#asciidoc-guide

## Need Help?

Need help? Try #logstash on freenode IRC or the https://discuss.elastic.co/c/logstash discussion forum.

## Developing

### 1. Plugin Development and Testing

#### Code
- To get started, you'll need JRuby.

```sh
export PATH=/jruby/bin:$PATH
```

- Install bundler gem
```sh
gem install bundler
```

- To develop a plugin you need a local clone of Logstash repository.
```sh
git clone --branch 8.1 --single-branch https://github.com/elastic/logstash.git
cd logstash
./gradlew assemble
```

- Point the plugin's environment to it
```sh
export LOGSTASH_PATH=/path/to/logstash/
export LOGSTASH_SOURCE=1
```
- Install vendor JDBC jars
```sh
./gradlew vendor
```

- Install dependencies
```sh
bundle install
```

- Run tests
```sh
bundle exec rspec
```

### 2. Running your unpublished Plugin in Logstash

- Build your plugin gem
```sh
gem build logstash-integration-jdbc.gemspec
```
- Install the plugin from the Logstash home
```sh
bin/logstash-plugin install /my/logstash/plugins/logstash-integration-jdbc/logstash-integration-jdbc-0.1.0.gem
```
- Start Logstash and proceed to test the plugin

## Contributing

All contributions are welcome: ideas, patches, documentation, bug reports, complaints, and even something you drew up on a napkin.

Programming is not a required skill. Whatever you've seen about open source and maintainers or community members  saying "send patches or die" - you will not see that here.

It is more important to the community that you are able to contribute.

For more information about contributing, see the [CONTRIBUTING](https://github.com/elastic/logstash/blob/master/CONTRIBUTING.md) file.
