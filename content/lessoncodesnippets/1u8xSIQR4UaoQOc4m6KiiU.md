---
curl: |-
  export CDA_TOKEN='<access_token>';
  export SPACE_ID='<space_id>';
dotNet: |-
  var httpClient = new HttpClient();
  var client = new ContentfulClient(httpClient, "<access_token>", "", "<space_id>");
java: |
  final CDAClient client =
      CDAClient
          .builder()
          .setToken("<access_token>")
          .setSpace("<space_id>")
          .build();
javaAndroid: |
  final CDAClient client =
      CDAClient
          .builder()
          .setToken("<access_token>")
          .setSpace("<space_id>")
          .build();
javascript: |
  const contentful = require('contentful')
  const client = contentful.createClient({
    space: '<space_id>',
    accessToken: '<access_token>'
  })
php: |-
  $client = new \Contentful\Delivery\Client(
      '<access_token>',
      '<space_id>'
  );
python: |
  import contentful

  client = contentful.Client('<space_id>', '<access_token>')
ruby: |-
  require ‘contentful’

  client = Contentful::Client.new(
    space: '<space_id>',
    access_token: '<access_token>',
    dynamic_entries: :auto,
    raise_errors: true
  )
swift: "import Contentful\n\nlet client = Client(spaceId: \"<space_id>\", \n                    accessToken:
  \"<access_token>\")"
title: SDK basics > SDK initialization - code
---
