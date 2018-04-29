---
copy: "_Content modelling_ is the practice of structuring your content. At Contentful,
  you do this by creating _content types_. Think of a content type as a schema for
  bits of content that are similar. For each content type, you populate its fields.
  Each field represents one piece of data of a specific type.\n\nYou can reference
  one content type from another to define relationships between them.\n\n## The content
  model of this lesson\n\nThe text that you're reading now is stored in Contentful.
  Its content type structure is as follows:\n\n- **Lesson**: Used to group and arrange
  content\n- **Lesson > Copy**: One chunk of markdown content\n- **Lesson > Code**:
  One chunk of code in different languages\n- **Lesson > Image**: An image\n\n![content-model-lesson](//images.contentful.com/qz0n5cdakyl9/1nXjR47jxOagUcc8iU6wUQ/54f18a32ed182a6fcb4f49f3ae242067/content-model-lesson.svg)\n\nTo
  model a _lesson_, we chose a modular approach where the content type called _Lesson_
  uses a reference field that contains references to other content types.\n\nThis
  approach is beneficial because content creators can arrange chunks of information
  in any order they want. Meanwhile, developers can control the how each chunk of
  information is presented.\n\n## The content model of this application\n\nThe following
  diagram displays the entire content model of this application, including: \n\n-
  The _Layout_ content type references the _Highlighted course_ content type\n- The
  _Highlighted course_ content type references the _Course_ content type\n- The _Course_
  content type references the _Lesson_ content type\n\nKnowing this, you can look
  into the hierarchy of this example app. Then, check out the corresponding hierarchy
  of the content types in the Contentful web app. Exploring the setup of this application
  will help strengthen your understanding of the relationships between the content
  model. Additionally, it shows how this is represented within this example app and
  the Contentful web app."
title: Content model > copy
---
