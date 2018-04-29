---
curl: |-
  export CPA_TOKEN='<cpa_token>';
  export SPACE_ID='<space_id>';
dotNet: |-
  var httpClient = new HttpClient();
  var client = new ContentfulClient(httpClient, "", "<cpa_token>", "<space_id>", usePreviewApi: true);
java: |-
  final CDAClient client =
      CDAClient
          .builder()
          .setToken("<cpa_token>")
          .preview()
          .setSpace("<space_id>")
          .build();
javaAndroid: |-
  final CDAClient client =
      CDAClient
          .builder()
          .setToken("<cpa_token>")
          .preview()
          .setSpace("<space_id>")
          .build();
javascript: |-
  const contentful = require('contentful')
  const client = contentful.createClient({
    space: '<space_id>',
    accessToken: '<cpa_token>',
    host: 'preview.contentful.com'
  })
php: |-
  $client = new \Contentful\Delivery\Client(
      '<cpa_token>',
      '<space_id>',
      true
  );
python: |-
  import contentful

  client = contentful.Client('<space_id>', '<cpa_token>', api_url='preview.contentful.com')
ruby: |-
  require ‘contentful’

  client = Contentful::Client.new(
    space: '<space_id>',
    access_token: '<cpa_token>',
    dynamic_entries: :auto,
    api_url: 'preview.contentful.com',
    raise_errors: true
  )
swift: "var configuration = ClientConfiguration()\nconfiguration.previewMode = true\n\n//
  Retain the client as a property on a type you define so that \n// the client's asynchronous
  network callbacks are executed.\nlet client = Client(spaceId: \"<space_id>\", accessToken:
  \"<cpa_token>\")"
title: Fetch draft content > code
---
