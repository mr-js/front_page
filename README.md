# front_page
 The front page of popular publishers as a human

 ## Usage
 Just adjust the settings in the ini-file according to the template (see below) and run "FrontPage". You can add/modify targets without writing any code inside using text-templates (the rules are based on the XPATH).

 ## Examples
 This is a example template for any target front page:

 ```ini
 Resource(
     name = 'VC (обсуждаемое)',
     url = 'https://vc.ru/top/week',
     base_url = '',
     pattern_block = './/div[@class="feed__container"]',
     pattern_items ='//div[@class="feed__item l-island-round"]',
     pattern_title = './/div[@class="content-title content-title--short l-island-a"]',
     pattern_link ='.//a[@class="content-header__item content-header-number"]',
 ),
 ```
 Here you should set definitions for content blocks and parsing settings:
 - name: name of your project
 - url: url of front page
 - base_url: base url if links on front page are not absolute
 - pattern_*: block definition in XPATH format in block hierarchy:
 ```
 pattern_block > pattern_items > (pattern_title, pattern_link)
```

 ## Remarks
 Why the first page and not RSS or the whole content -- what's the point? Because it is on the "front page" that the promoted news is deliberately placed: it is not always possible to calculate this by analyzing a continuous RSS stream, uploading via API or even evaluations/comments to articles. At the same time, this software emulates the user's browser and we get the news as it was originally conceived, but only in the final form as an excerpt and without advertising.
