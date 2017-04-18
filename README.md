# Google Cloud Client Libraries for PHP
> Idiomatic PHP client for [Google Cloud Platform](https://cloud.google.com/) services.

[![Travis Build Status](https://travis-ci.org/GoogleCloudPlatform/google-cloud-php.svg?branch=master)](https://travis-ci.org/GoogleCloudPlatform/google-cloud-php/) [![codecov](https://codecov.io/gh/googlecloudplatform/google-cloud-php/branch/master/graph/badge.svg)](https://codecov.io/gh/googlecloudplatform/google-cloud-php)

* [Homepage](http://googlecloudplatform.github.io/google-cloud-php)
* [API Documentation](http://googlecloudplatform.github.io/google-cloud-php/#/docs)

This client supports the following Google Cloud Platform services at a [General Availability](#versioning) quality level:
* [Google Stackdriver Logging](#google-stackdriver-logging-ga) (GA)
* [Google Cloud Datastore](#google-cloud-datastore-ga) (GA)
* [Google Cloud Storage](#google-cloud-storage-ga) (GA)

This client supports the following Google Cloud Platform services at a [Beta](#versioning) quality level:

* [Google BigQuery](#google-bigquery-beta) (Beta)
* [Google Cloud Natural Language](#google-cloud-natural-language-beta) (Beta)
* [Google Cloud Translation](#google-cloud-translation-beta) (Beta)
* [Google Cloud Vision](#google-cloud-vision-beta) (Beta)

This client supports the following Google Cloud Platform services at an [Alpha](#versioning) quality level:
* [Google Cloud Pub/Sub](#google-cloud-pubsub-alpha) (Alpha)
* [Google Cloud Speech](#google-cloud-speech-alpha) (Alpha)

If you need support for other Google APIs, please check out the [Google APIs Client Library for PHP](https://github.com/google/google-api-php-client).

## Quick Start
In order to use any of our libraries, you first need to go through the following steps:

* [Select or create a Cloud Platform project](https://console.cloud.google.com/project).
* [Enable billing for your project](https://support.google.com/cloud/answer/6293499#enable-billing).
* [Enable the API you'll want to use](https://console.cloud.google.com/apis/library) (e.g. Vision API or Datastore API).
* [Setup Authentication]().

Once these steps are done, you can install the individual package for the API you want to use. For instance, to call the Cloud Vision API you need to install the following:

```sh
$ composer require google/cloud-vision
```

From there, you can then start using the client. Please see lower in this page for code examples to get you started or look at the README of each API located in a subfolder of this repo.

#### The google/cloud meta-package
We also provide a meta-package, `google/cloud`, which provides access to all of the APIs at once:

```sh
$ composer require google/cloud
```

## Example Applications

* [getting-started-php](https://github.com/GoogleCloudPlatform/getting-started-php/) -
  A [tutorial](https://cloud.google.com/php/getting-started/tutorial-app) that demonstrates how to build a complete web application using Cloud Datastore, Cloud Storage, and Cloud Pub/Sub and deploy it to Google App Engine.

## Google Cloud Storage (Beta)
- [API Documentation](http://googlecloudplatform.github.io/google-cloud-php/#/docs/latest/storage/storageclient)
- [Official Documentation](https://cloud.google.com/storage/docs)

#### Quick Start
```
$ require google/cloud-storage
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

## Versioning

This library follows [Semantic Versioning](http://semver.org/).

Please note it is currently under active development. Any release versioned
0.x.y is subject to backwards incompatible changes at any time.

**GA**: Libraries defined at a GA quality level are stable, and will not
introduce backwards-incompatible changes in any minor or patch releases. We will
address issues and requests with the highest priority.

**Beta**: Libraries defined at a Beta quality level are expected to be mostly
stable and we're working towards their release candidate. We will address issues
and requests with a higher priority.

**Alpha**: Libraries defined at an Alpha quality level are still a
work-in-progress and are more likely to get backwards-incompatible updates.

## Contributing

Contributions to this library are always welcome and highly encouraged.

See [CONTRIBUTING](CONTRIBUTING.md) for more information on how to get started.

## License

Apache 2.0 - See [LICENSE](LICENSE) for more information.

