---
curl: |-
  entry = client.entry('2uNOpLMJioKeoMq8W44uYc', locale: 'de-DE')
  puts(entry.fields)
dotNet: |-
  var queryBuilder = QueryBuilder<dynamic>.New.LocaleIs("de-DE");
  var entries = await client.GetEntriesAsync(queryBuilder);
  Console.WriteLine(entries.ToString());
java: |-
  final CDAArray all =
      client
          .fetch(CDAEntry.class)
          .where("locale", "de-DE")
          .all();

  System.out.println(all.toString());
javaAndroid: |-
  client
      .observe(CDAEntry.class)
      .where("locale", "de-DE")
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

            @Override public void onNext(CDAArray entry) {
              // Array received, maybe more to come.
              result = entry;
            }
          }
javascript: |-
  client.getEntries({'locale': 'de-DE'}).then((response) => {
    console.log(response)
  })
php: |-
  $query = (new Contentful\Delivery\Query())
      ->setLocale('de-DE');

  $entries = $client->getEntries($query);

  var_dump($entries);
python: |-
  entry = client.entry('2uNOpLMJioKeoMq8W44uYc', {'locale': 'de-DE'})
  print(entry.fields())
ruby: |-
  entry = client.entry('2uNOpLMJioKeoMq8W44uYc', locale: 'de-DE')
  puts(entry.fields)
swift: |-
  let query = Query(where: "locale", .equals("de-DE"))

  client.fetchEntries(with: query) { (result: Result<ArrayResponse<Entry>>) in
    switch result {
    case .success(let arrayResponse):
      let entries = arrayResponse.items
      print(entries)
    case .error(let error):
      print(error)
    }
  }
title: Serve localized content > fetch code
---
