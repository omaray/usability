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
> make backwards-incompatible changes. The layout of the repository
> is likely to change, and names (of everything - assemblies,
> namespaces, types, members...) should be regarded as provisional.

If you need support for other Google APIs, check out the [Google .NET API Client library].

## Quickstart

```sh
PM> Install-Package gcloud-dotnet
```

## Example Applications

* [getting-started-dotnet] - A sample and [tutorial] that demonstrates how to build a complete web application using Cloud Datastore, Cloud Storage, and Cloud Pub/Sub and deploy it to Google App Engine or Google Compute Engine.
* [demos] - Sample code showing how to use several of the APIs supported by this library.
* Other Examples...

## Authentication

Add authentication documentation here...

## Google Cloud Pub/Sub

- [API Documentation][gcloud-pubsub-docs]
- [Official Documentation][cloud-pubsub-docs]

#### Preview

```dotnet
using Google.Cloud.PubSub;
...
```

## Google Cloud Storage

- [API Documentation][gcloud-storage-docs]
- [Official Documentation][cloud-storage-docs]

#### Preview

```dotnet
using Google.Cloud.Storage;
...
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
[getting-started-dotnet]: https://github.com/GoogleCloudPlatform/getting-started-dotnet
[demos]: https://github.com/GoogleCloudPlatform/gcloud-dotnet/tree/master/demo
[language-landing-dotnet]: https://cloud.google.com/dotnet/
[api-reference-dotnet]: http://jskeet.github.io/gcloud-dotnet/
[gcloud-pubsub-docs]: http://jskeet.github.io/gcloud-dotnet/api/Google.Pubsub.V1.html
[gcloud-storage-docs]: http://jskeet.github.io/gcloud-dotnet/api/Google.Storage.V1.html
[cloud-pubsub-docs]: https://cloud.google.com/pubsub/docs
[cloud-storage-docs]: https://cloud.google.com/storage/docs
[tutorial]: https://cloud.google.com/dotnet/
[CONTRIBUTING]:https://github.com/GoogleCloudPlatform/gcloud-dotnet/blob/master/CONTRIBUTING.md
[LICENSE]: https://github.com/GoogleCloudPlatform/gcloud-dotnet/blob/master/LICENSE
