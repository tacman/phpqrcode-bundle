Setting up the bundle
=====================

## Install the bundle

Execute this console command in your project:

``` bash
composer require jonasarts/phpqrcode-bundle
```

## Enable the bundle

Composer enables the bundle for you in config/bundles.php

Register the controller & services:

```yaml
#config/services.yml
jonasarts\Bundle\PHPQRCodeBundle\:
    resource: '../vendor/jonasarts/phpqrcode-bundle/*'
    exclude: '../vendor/jonasarts/phpqrcode-bundle/{DependencyInjection,lib,Tests}'
jonasarts\Bundle\PHPQRCodeBundle\Controller\:
    resource: '../vendor/jonasarts/phpqrcode-bundle/Controller'
    tags: ['controller.service_arguments']
```

You can now use `jonasarts\Bundle\PHPQRCodeBundle\PHPQRCode\PHPQRCode` class.

Register the routes:

Add a routing configuration in `config/routes` directory:

```yaml
#config/routes/phpqrcode.yaml
phpqrcode:
    resource: '@PHPQRCodeBundle/Controller/'
    type: annotation
```

Optional, add a default configuration:

```yaml
# config/packages/phpqrcode.yml
phpqrcode:
    default:
        level: Q
        size: 4
        margin: 3
```

## That's it

Check out the docs for information on how to use the bundle! [Return to the index.](index.md)
