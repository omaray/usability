# Cloud PHP Client Library for Cloud Storage
> Idiomatic PHP client for [Google Cloud Platform](https://cloud.google.com/) services.

## Quick Start
In order to use this library, you first need to go through the following steps:

* [Select or create a Cloud Platform project](https://console.cloud.google.com/project).
* [Enable billing for your project](https://support.google.com/cloud/answer/6293499#enable-billing).
* [Enable the Storage API you'll want to use](https://console.cloud.google.com/apis/library).
* [Setup Authentication]().

Once these steps are done, you can install the following package:

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

#### Next Steps

* Read the API Reference documentation to see other available methods on the client.
* Read the official Cloud Storage to learn more about the API and see code examples.
