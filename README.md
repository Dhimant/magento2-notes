
# How to print logs
```
$writer = new \Zend\Log\Writer\Stream(BP . '/var/log/test.log');
$logger = new \Zend\Log\Logger();
$logger->addWriter($writer);
$logger->info('Your text message');
```
# Change Default CronTab editor

```
export EDITOR=/bin/nano
export VISUAL=nano

export EDITOR=/usr/bin/vim
export VISUAL=vim

export EDITOR=/bin/vi
export VISUAL=vi
```

# magento2-issues

1. Not able to see custom category image in admin.

> https://github.com/magento/magento2/issues/25099#issuecomment-544892783

2. Importing Products with new categories will append to the existing product categories, if you want to update the categories instead, use the following workaround

> https://github.com/magento/magento2/issues/7930#issuecomment-416936746

3. Magento 2.2.4 The value specified in the URL Key field would generate a URL that already exists [following answer should fix this issue]

> https://magento.stackexchange.com/a/279152
