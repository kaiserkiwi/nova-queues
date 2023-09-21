# Nova Queues for Laravel Nova 4

Simple Queue resource for Laravel Nova.

**Supports only the `database` queue driver.**

## Installation

Install package with Composer.

```sh
composer require kaiserkiwi/nova-queues
```

Publish package resources.

```sh
php artisan vendor:publish --provider=Kaiserkiwi\NovaQueues\ServiceProvider
```

This will publish the following resources:

* Configuration file `config/nova-queues.php`.
* Translations `resources/lang/vendor/nova-queues`.
* Views `resources/views/vendor/nova-queues`.

Create database queue table if it's not exists.

```sh
php artisan queue:table
```

Migrate database.

```sh
php artisan migrate
```

Add instance of class `Kaiserkiwi\NovaQueues\Tool` to your `App\Providers\NovaServiceProvider::tools()` method to display the jobs within your Nova resources.

```php
/**
 * Get the tools that should be listed in the Nova sidebar.
 *
 * @return array
 */
public function tools()
{
    return [
        new \Kaiserkiwi\NovaQueues\Tool,
    ];
}
```

## Screenshots

### Jobs

![Jobs](https://github.com/kaiserkiwi/nova-queues/assets/8428551/7325567e-4977-493b-af25-3300fe71476b)


### Job Details

![Job Details](https://github.com/kaiserkiwi/nova-queues/assets/8428551/b1a0a378-9521-4ef3-8d44-f3d71fbb700e)


### Failed Jobs

![Failed Jobs](https://github.com/kaiserkiwi/nova-queues/assets/8428551/73dea1f5-c9d5-4f39-84c8-3438660c81e2)


## Contributing

1. Fork it.
2. Create your feature branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

## Support

If you require any support open an issue on this repository.

## License

MIT
