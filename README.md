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

## Quickstart
In order to use any of our libraries, you first need to take the following steps:

* [Select or create a Cloud Platform project](https://console.cloud.google.com/project).
* [Enable billing for your project](https://support.google.com/cloud/answer/6293499#enable-billing).
* [Enable the API you'll want to use](https://console.cloud.google.com/apis/library) (e.g. Vision API or Datastore API).
* Setup Authentication

Once these steps are done, we recommend you install the individual packages that you need, for instance:

```sh
$ composer require google/cloud
```

