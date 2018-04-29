---
curl: 'curl -H ''Authorization: Bearer ''$CDA_TOKEN ''https://cdn.contentful.com/spaces/''$SPACE_ID''/entries/'''
dotNet: |-
  var entry = await client.GetEntries<dynamic>();

  Console.WriteLine(entry.ToString());
java: |
  final CDAArray all =
      client
          .fetch(CDAEntry.class)
          .all();

  System.out.println(all);
javaAndroid: |-
  client
      .observe(CDAEntry.class)
      .all()
      .observeOn(AndroidSchedulers.mainThread())
      .subscribeOn(io.reactivex.schedulers.Schedulers.io())
      .subscribe(
          new DisposableSubscriber<CDAArray>() {
            CDAArray result;

            @Override public void onComplete() {
              new AlertDialog.Builder(context)
                  .setTitle("Contentful")
                  .setMessage(result.toString())
                  .show();
            }

            @Override public void onError(Throwable e) {
              // Handle error case.
              new AlertDialog.Builder(context)
                  .setTitle("Contentful")
                  .setMessage("An error occurred: " + e.toString())
                  .show();
            }

            @Override public void onNext(CDAArray array) {
              // Array received, maybe more to come.
              result = entry;
            }
          }
javascript: |-
  client.getEntries()
  .then((response) => console.log(response))
php: |-
  $entries = $client->getEntries();

  var_dump($entries);
python: |-
  entries = client.entries()
  print(repr(entries))
ruby: |-
  entries = client.entries()
  puts(entries)
swift: |-
  client.fetchEntries() { (result: Result<ArrayResponse<Entry>>) in
      switch result {
          case .success(arrayResponse):
              let entries = arrayResponse.items
              print(entries)
          case .error(let error):
              print("Error \(error)!")
      }
  }
title: Fetch all entries > code
---
