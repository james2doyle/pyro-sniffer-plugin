pyro-sniffer-plugin
===================

Sniff information from the user agent for use in the frontend. Useful for adding classes or conditional loading.

This plugin is **not** built on the [CodeIgniter User Agent Library](http://ellislab.com/codeigniter/user-guide/libraries/user_agent.html).

The reason I did not use the built in CodeIgniter lib, was because Pyro is only going to have CodeIgniter for a few more months(right?!?!), and I also want to have the information returned in a different way. This plugin is pretty small and only really gets information that is helpful to be used in CSS and Javascript (CSS custom classes and js feature detection/fallbacks).

If you are looking for a plugin that uses the user agent library, check out [this plugin called Agent](https://www.pyrocms.com/store/details/agent_plugin).

### Usage

```html
<body class="{{ sniffer:get key="browser|platform" }}">
```

On my Mac running Google Chrome, this would return:

```html
<body class=" google-chrome mac">
```

On my iPhone, this would return:

```html
<body class=" apple-mobile-safari ios">
```
here is the full dump of the `$results` object for my machine:

```php
$results = array (
  ['useragent'] => 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_8_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/28.0.1500.44 Safari/537.36' // full ua string
  ['name'] => 'Google Chrome' // name of the browser
  ['browser'] => 'google-chrome' // CSS safe browser name
  ['version'] => '28.0.1500.44' // bowser version
  ['platform'] => 'mac' // OS platform
  ['pattern'] => '#(?Version|Chrome|other)[/ ]+(?[0-9.|a-zA-Z.]*)#' // match pattern
);
```





