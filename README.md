# Matomo Module
 
Provide TrackingCode implementation Widget and admin dashboard object to see latest visits.

<p align="center">
  <img src="https://raw.githubusercontent.com/luyadev/luya-module-matomo/master/matomo.png" alt="LUYA Logo"/>
</p>
 
## Installation

In order to add the modules to your project go into the modules section of your config:

```php
return [
    'modules' => [
        'matomoadmin' => [
            'class' => 'luya\matomo\Module',
            'serverUrl' => 'https://matomo.example.com', // without trailing slash, use full schema path.
            'siteId' => 1,
            'apiToken' => 'THE_API_TOKEN',
        ]
    ],
];
```

## Usage

After configure the admin module you can now integrate the TrackingCode widget. The tracking code will register the javascript tracking and as fall back also the tracking image between noscript tags.

We reccommend to integrate the TrackingCodeWidget right before the endBody() function in the layout.

```php
<?= \luya\matomo\TrackingCodeWidget::widget(); ?>
<?php $this->endBody() ?>
```