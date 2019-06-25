[//]: # "This README.md file is auto-generated, all changes to this file will be lost."
[//]: # "To regenerate it, use `python -m synthtool`."
<img src="https://avatars2.githubusercontent.com/u/2810941?v=3&s=96" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# [Web Risk API: Node.js Client](https://github.com/googleapis/nodejs-web-risk)

[![release level](https://img.shields.io/badge/release%20level-beta-yellow.svg?style=flat)](https://cloud.google.com/terms/launch-stages)
[![npm version](https://img.shields.io/npm/v/@google-cloud/web-risk.svg)](https://www.npmjs.org/package/@google-cloud/web-risk)
[![codecov](https://img.shields.io/codecov/c/github/googleapis/nodejs-web-risk/master.svg?style=flat)](https://codecov.io/gh/googleapis/nodejs-web-risk)




Web Risk API client for Node.js


* [Web Risk API Node.js Client API Reference][client-docs]
* [Web Risk API Documentation][product-docs]
* [github.com/googleapis/nodejs-web-risk](https://github.com/googleapis/nodejs-web-risk)

Read more about the client libraries for Cloud APIs, including the older
Google APIs Client Libraries, in [Client Libraries Explained][explained].

[explained]: https://cloud.google.com/apis/docs/client-libraries-explained

**Table of contents:**


* [Quickstart](#quickstart)
  * [Before you begin](#before-you-begin)
  * [Installing the client library](#installing-the-client-library)
  * [Using the client library](#using-the-client-library)
* [Samples](#samples)
* [Versioning](#versioning)
* [Contributing](#contributing)
* [License](#license)

## Quickstart

### Before you begin

1.  [Select or create a Cloud Platform project][projects].
1.  [Enable billing for your project][billing].
1.  [Enable the Web Risk API API][enable_api].
1.  [Set up authentication with a service account][auth] so you can access the
    API from your local workstation.

### Installing the client library

```bash
npm install @google-cloud/web-risk
```


### Using the client library

```javascript
/**
 * Check a URI against the WebRisk API.
 * @param {string} uri A URI to pass to the Web Risk API.
 */
async function quickstart(uri) {
  // Create the WebRisk client library.
  const {WebRiskServiceV1Beta1Client} = require('@google-cloud/web-risk');
  const client = new WebRiskServiceV1Beta1Client();

  // Create an API request to check for malware, social engineering,
  // and unwanted software.
  const request = {
    uri: uri,
    threatTypes: ['MALWARE', 'SOCIAL_ENGINEERING', 'UNWANTED_SOFTWARE'],
  };

  // call the WebRisk searchUris API.
  const {threat} = (await client.searchUris(request))[0];
  if (threat) {
    console.info(threat);
  } else {
    console.info('no threats found');
  }
}

```



## Samples

Samples are in the [`samples/`](https://github.com/googleapis/nodejs-web-risk/tree/master/samples) directory. The samples' `README.md`
has instructions for running the samples.

| Sample                      | Source Code                       | Try it |
| --------------------------- | --------------------------------- | ------ |
| Quickstart | [source code](https://github.com/googleapis/nodejs-web-risk/blob/master/samples/quickstart.js) | [![Open in Cloud Shell][shell_img]](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googleapis/nodejs-web-risk&page=editor&open_in_editor=samples/quickstart.js,samples/README.md) |



The [Web Risk API Node.js Client API Reference][client-docs] documentation
also contains samples.

## Versioning

This library follows [Semantic Versioning](http://semver.org/).



This library is considered to be in **beta**. This means it is expected to be
mostly stable while we work toward a general availability release; however,
complete stability is not guaranteed. We will address issues and requests
against beta libraries with a high priority.




More Information: [Google Cloud Platform Launch Stages][launch_stages]

[launch_stages]: https://cloud.google.com/terms/launch-stages

## Contributing

Contributions welcome! See the [Contributing Guide](https://github.com/googleapis/nodejs-web-risk/blob/master/CONTRIBUTING.md).

## License

Apache Version 2.0

See [LICENSE](https://github.com/googleapis/nodejs-web-risk/blob/master/LICENSE)

[client-docs]: https://googleapis.dev/nodejs/web-risk/latest#reference
[product-docs]: https://cloud.google.com/web-risk/docs/
[shell_img]: https://gstatic.com/cloudssh/images/open-btn.png
[projects]: https://console.cloud.google.com/project
[billing]: https://support.google.com/cloud/answer/6293499#enable-billing
[enable_api]: https://console.cloud.google.com/flows/enableapi?apiid=webrisk.googleapis.com
[auth]: https://cloud.google.com/docs/authentication/getting-started

<a name="reference"></a>
