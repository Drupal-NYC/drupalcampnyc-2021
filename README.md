# drupalcampnyc-2021
A static archive of our 2021 camp site.

For future archivers' benefit: in a nutshell, the process is ...

### Run a Tome Static export using Drush

Pull database and files from Pantheon Live environment.

```
$ lando pull --code=none --database=live --files=live
```

Composer require Tome module.

```
$ lando composer require drupal/tome
```

Drush enable Tome Static submodule.

```
$ lando drush en tome tome_static
```

Export the Drupal site.

```
$ lando drush tome:export -y
$ lando drush tome:static --uri=https://2021.drupalcamp.nyc
```

This exports the static HTML site to the `html` directory in the project root.

Then you need to deploy that to a new repo on GitHub, configured appropriately for [GitHub Pages](https://pages.github.com).