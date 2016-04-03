# Google Cloud .NET Client

> .NET idiomatic client for [Google Cloud Platform] services.

[![Build Status](https://travis-ci.org/GoogleCloudPlatform/gcloud-dotnet.svg?branch=master)](https://travis-ci.org/GoogleCloudPlatform/gcloud-dotnet)
[![Coverage Status](https://coveralls.io/repos/GoogleCloudPlatform/gcloud-java/badge.svg?branch=master)](https://coveralls.io/r/GoogleCloudPlatform/gcloud-java?branch=master)
[![Codacy Badge](https://api.codacy.com/project/badge/grade/9da006ad7c3a4fe1abd142e77c003917)](https://www.codacy.com/app/mziccard/gcloud-java)

* [Homepage][language-landing-dotnet]
* [API Documentation][api-reference-dotnet]

This client supports the following Google Cloud Platform services:

* [Google Cloud Pub/Sub](#google-cloud-pubsub)
* [Google Cloud Storage](#google-cloud-storage)

> Note: This client is a work-in-progress, and may occasionally
> make backwards-incompatible changes.

If you need support for other Google APIs, check out the [Google .NET API Client library].

## Quickstart

```sh
PM> Install-Package gcloud-dotnet
```

## Example Applications

## Google Cloud Pub/Sub

- [API Documentation][gcloud-pubsub-docs]
- [Official Documentation][cloud-pubsub-docs]

#### Preview

```js
var gcloud = require('gcloud');

// Authenticating on a per-API-basis. You don't need to do this if you
// auth on a global basis (see Authentication section above).

var pubsub = gcloud.pubsub({
  projectId: 'my-project',
  keyFilename: '/path/to/keyfile.json'
});

// Reference a topic that has been previously created.
var topic = pubsub.topic('my-topic');

// Publish a message to the topic.
topic.publish({
  data: 'New message!'
}, function(err) {});

// Subscribe to the topic.
topic.subscribe('new-subscription', function(err, subscription) {
  // Register listeners to start pulling for messages.
  function onError(err) {}
  function onMessage(message) {}
  subscription.on('error', onError);
  subscription.on('message', onMessage);

  // Remove listeners to stop pulling for messages.
  subscription.removeListener('message', onMessage);
  subscription.removeListener('error', onError);
});
```

## Google Cloud Storage

- [API Documentation][gcloud-storage-docs]
- [Official Documentation][cloud-storage-docs]

#### Preview

```js
var fs = require('fs');
var gcloud = require('gcloud');

// Authenticating on a per-API-basis. You don't need to do this if you auth on a
// global basis (see Authentication section above).

var gcs = gcloud.storage({
  projectId: 'my-project',
  keyFilename: '/path/to/keyfile.json'
});

// Create a new bucket.
gcs.createBucket('my-new-bucket', function(err, bucket) {
  if (!err) {
    // "my-new-bucket" was successfully created.
  }
});

// Reference an existing bucket.
var bucket = gcs.bucket('my-existing-bucket');

// Upload a local file to a new file to be created in your bucket.
bucket.upload('/photos/zoo/zebra.jpg', function(err, file) {
  if (!err) {
    // "zebra.jpg" is now in your bucket.
  }
});

// Download a file from your bucket.
bucket.file('giraffe.jpg').download({
  destination: '/photos/zoo/giraffe.jpg'
}, function(err) {});

// Streams are also supported for reading and writing files.
var remoteReadStream = bucket.file('giraffe.jpg').createReadStream();
var localWriteStream = fs.createWriteStream('/photos/zoo/giraffe.jpg');
remoteReadStream.pipe(localWriteStream);

var localReadStream = fs.createReadStream('/photos/zoo/zebra.jpg');
var remoteWriteStream = bucket.file('zebra.jpg').createWriteStream();
localReadStream.pipe(remoteWriteStream);
```

## Contributing

Contributions to this library are always welcome and highly encouraged.

See [CONTRIBUTING] for more information on how to get started.

## Versioning

These libraries follow [Semantic Versioning].

Anything with a major version of zero (``0.y.z``) should not be
considered stable - anything may change at any time.

## License

Apache 2.0 - See [LICENSE] for more information.

[Google Cloud Platform]: https://cloud.google.com/
[Google .NET API Client library]: https://github.com/google/google-api-dotnet-client
[Semantic Versioning]: http://semver.org/
[language-landing-dotnet]: https://cloud.google.com/dotnet/
[api-reference-dotnet]: http://jskeet.github.io/gcloud-dotnet/
[gcloud-pubsub-docs]: http://jskeet.github.io/gcloud-dotnet/api/Google.Pubsub.V1.html
[gcloud-storage-docs]: http://jskeet.github.io/gcloud-dotnet/api/Google.Storage.V1.html
[cloud-pubsub-docs]: https://cloud.google.com/pubsub/docs
[cloud-storage-docs]: https://cloud.google.com/storage/docs
[CONTRIBUTING]:https://github.com/GoogleCloudPlatform/gcloud-dotnet/blob/master/CONTRIBUTING.md
[LICENSE]: https://github.com/GoogleCloudPlatform/gcloud-dotnet/blob/master/LICENSE
