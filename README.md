# Vagrant Ghost

This is a fork of [vagrant-hostsupdater](/cogitatio/vagrant-hostsupdater).

To test/use this plugin:

```sh
cd /path/to/moonshine/hostupdater
sudo gem install bundler -v '1.7.13'
bundle

```

This will install all the dependencies for this package and enable you to run vagrant with this plugin temporarily active.

After you've run the commands above, test with Vagrant by running vagrant commands prefixed with `bundle exec` from the `hostupdater` directory. For example:

```sh
bundle exec vagrant up
bundle exec vagrant halt
```

You can also manually trigger a host file update:

```
bundle exec vagrant ghost
```

If your VM is running, it will add the hosts to the hosts file. If it's not running, it will remove the hosts from the hosts file.

To add a host to your hosts file, you can specify hosts in your Vagrantfile:

```rb
config.vm.hostname = 'test.dev'
config.ghost.aliases = ['www.test.dev', 'foo.test.dev']
```