---
title: "Content Search"
permalink: /content-search/
excerpt: "Using global search within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---
Skyve applications include an embedded full-text search index (based on the open-source [Apache Lucene](https://lucene.apache.org/) search library) for indexing and searching both data and content within an application. Other search providers, such as Elasticsearch, can optionally be configured by your application host.

The fields your application has been configured to index (typically long text fields), along with the text extracted from uploaded attachments (such as PDF and Word documents), are available to be searched.

### Global Search

**Desktop mode required**: global search is only available in _desktop mode_. To switch modes, click your username in the top right hand corner and choose `Switch Mode` — see [Switching Interfaces]({{ site.url }}{{ site.baseurl }}/#switching-interfaces). Note that the search icon will only appear if your user has been granted access to text search.
{: .notice--info}

To use the global search function from a Skyve application:

1. Login to your application
2. Switch to desktop mode if not already in it, by clicking your username in the top right hand corner and choosing `Switch Mode`

    ![Switch mode]({{ site.url }}{{ site.baseurl }}/assets/images/switch.png)

3. From the toolbar in the top right hand corner of the page, click the search icon

    ![Global search button]({{ site.url }}{{ site.baseurl }}/assets/images/search.png)

4. Enter a search term (at least 4 characters) into the search field and click `Search`
5. Search results will be returned in order of relevance, showing which document the result was found in, an excerpt of the resulting match, and a `Score` column indicating how strong each match is. If your term found no strong matches, a "Did you mean ..." suggestion may be offered — click it to search for the suggested spelling
6. Clicking the `data` link will take you to the record which contains the search result
7. Clicking the `content` link will open the uploaded file which contains the search result