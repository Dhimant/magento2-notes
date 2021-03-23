
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
# create a zip file in linux

```
zip -r myarchive.zip dir1 -x "dir1/ignoreDir1/*" "dir1/ignoreDir2/*"
```


# download file using curl

```
curl https://www.example.com/media/store-4.xml --output store-4-orig.xml
```


# Change customer password
```
select * from customer_entity where email = 'abcd@gmail.com'


SET @email='abcd@gmail.com', @passwd='test@123', @salt=MD5(RAND());

UPDATE customer_entity
    SET password_hash = CONCAT(SHA2(CONCAT(@salt, @passwd), 256), ':', @salt, ':1')
    WHERE email = @email;
```

# n98-magerun2

> https://github.com/netz98/n98-magerun2

# magento2-issues

1. Not able to see custom category image in admin.

> https://github.com/magento/magento2/issues/25099#issuecomment-544892783

2. Importing Products with new categories will append to the existing product categories, if you want to update the categories instead, use the following workaround

> https://github.com/magento/magento2/issues/7930#issuecomment-416936746

3. Magento 2.2.4 The value specified in the URL Key field would generate a URL that already exists [following answer should fix this issue]

> https://magento.stackexchange.com/a/279152
