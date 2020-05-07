# summarizeText

This source code can summarize a text, article for example to a short paragraph. Before it would start the summarizing it removes the junk words what are defined in the Stopwords namespace. It is possible to extend it with another languages.

## Authors, Contributors

Name | GitHub user
--- | ---
Ankit Singh | @ankit20893

##  Automatic summarization
> Automatic summarization is the process of reducing a text document with a computer program in order to create a summary that retains the most important points of the original document. Technologies that can make a coherent summary take into account variables such as length, writing style and syntax. Automatic data summarization is part of machine learning and data mining. The main idea of summarization is to find a representative subset of the data, which contains the information of the entire set. Summarization technologies are used in a large number of sectors in industry today. - Wikipedia

The algorithm of this implementation is:
* Find sentences,
* Remove stopwords,
* Create integer values by find and count the matching words,
* Change the integer values by the related words' integer values,
* Normalize values to create scores,
* Order by scores

## Install
```
composer require ankit20893/summarize-text
```

## Test
```
cd project-folder
composer test
```
or
```
cd project-folder
phpunit --colors='always' $(pwd)/tests
```

## Examples
```php

use summarizeText\Tool\StopWords\English;

// String contains a long text, see the /res/sample1.txt file.
$text = "Lorem ipsum...";

$api = new TextRankFacade();
// English implementation for stopwords/junk words:
$stopWords = new English();
$api->setStopWords($stopWords);

// Array of the most important keywords:
$result = $api->getOnlyKeyWords($text); 

// Array of the sentences from the most important part of the text:
$result = $api->getHighlights($text); 

// Array of the most important sentences from the text:
$result = $api->summarizeTextBasic($text);
```
