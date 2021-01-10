# How to print logs
```
$writer = new \Zend\Log\Writer\Stream(BP . '/var/log/test.log');
$logger = new \Zend\Log\Logger();
$logger->addWriter($writer);
$logger->info('Your text message');
```


# magento2-issues

1. Not able to see custom category image in admin. 
https://github.com/magento/magento2/issues/25099#issuecomment-544892783

2. Importing Products with new categories will append to the existing product categories, if you want to update the categories instead, use the following workaround
https://github.com/magento/magento2/issues/7930#issuecomment-416936746
