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

## Getting started
In order to use any of our libraries, you first need to take the following steps:

* [Select or create a Cloud Platform project](https://console.cloud.google.com/project).
* [Enable billing for your project](https://support.google.com/cloud/answer/6293499#enable-billing).
* [Enable the API you'll want to use](https://console.cloud.google.com/apis/library) (e.g. Vision API or Datastore API).
* [Setup Authentication]()

Once these steps are done, we recommend you install the individual packages that you need, for instance:

```sh
$ composer require google/cloud-vision
$ composer require google/cloud-datastore
```

From there, you can then start using the client. Please see lower in this page for code examples to get you started.

#### The google/cloud meta-package
We also provide a meta-package, `google/cloud`, which provides all of the individual APIs. However, in order to keep file size and memory use low, the use of this package is not recommended.

If you want the kitchen sink, however, get it with:

```sh
$ composer require google/cloud
```

## Google BigQuery (Beta)

- [API Documentation](http://googlecloudplatform.github.io/google-cloud-php/#/docs/latest/bigquery/bigqueryclient)
- [Official Documentation](https://cloud.google.com/bigquery/docs)

#### Quick Start
```
$ require google/cloud-bigquery
```

#### Preview

```php
require 'vendor/autoload.php';

use Google\Cloud\BigQuery\BigQueryClient;

$bigQuery = new BigQueryClient([
    'projectId' => 'my_project'
]);

// Get an instance of a previously created table.
$dataset = $bigQuery->dataset('my_dataset');
$table = $dataset->table('my_table');

// Begin a job to import data from a CSV file into the table.
$job = $table->load(
    fopen('/data/my_data.csv', 'r')
);

// Run a query and inspect the results.
$queryResults = $bigQuery->runQuery('SELECT * FROM [my_project:my_dataset.my_table]');

foreach ($queryResults->rows() as $row) {
    print_r($row);
}
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

