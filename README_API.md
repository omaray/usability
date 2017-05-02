# PHP Client for Google Cloud Storage (Beta)
Idiomatic PHP client for [Google Cloud Storage](https://cloud.google.com/storage).

- [Client Library Documentation](http://googlecloudplatform.github.io/google-cloud-php/#/docs/latest/storage/storageclient)
- [Product Documentation](https://cloud.google.com/storage/docs)

## Quick Start
In order to use this library, you first need to go through the following steps:

* [Select or create a Cloud Platform project](https://console.cloud.google.com/project).
* [Enable billing for your project](https://support.google.com/cloud/answer/6293499#enable-billing).
* [Enable the Storage API](https://console.cloud.google.com/apis/library).
* [Setup Authentication]().

Once these steps are done, you can install the package and start using the client.

#### Installation

```sh
$ composer require google/cloud-storage
```

#### Preview

```php
require 'vendor/autoload.php';

use Google\Cloud\Storage\StorageClient;

$storage = new StorageClient([
    'projectId' => 'my_project'
]);

$bucket = $storage->bucket('my_bucket');

// Upload a file to the bucket.
$bucket->upload(
    fopen('/data/file.txt', 'r')
);

// Download and store an object from the bucket locally.
$object = $bucket->object('file_backup.txt');
$object->downloadToFile('/data/file_backup.txt');
```

#### Next Steps

* Read the [API Reference]() documentation for Cloud Storage to see other available methods on the client.
* Read the [Official Cloud Storage]() documentation to learn more about the product and see How-to Guides.
* View this [repository's main README]() to see the full list of Cloud APIs that we cover.
