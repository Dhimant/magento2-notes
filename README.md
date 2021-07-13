
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

# backtrace 

```

public function generateCallTrace()
{
    $e = new \Exception();
    $trace = explode("\n", $e->getTraceAsString());
    // reverse array to make steps line up chronologically
    $trace = array_reverse($trace);
    array_shift($trace); // remove {main}
    array_pop($trace); // remove call to this method
    $length = count($trace);
    $result = array();
   
    for ($i = 0; $i < $length; $i++)
    {
        $result[] = ($i + 1)  . ')' . substr($trace[$i], strpos($trace[$i], ' ')); // replace '#someNum' with '$i)', set the right ordering
    }
    
    $writer = new \Zend\Log\Writer\Stream(BP . '/var/log/backtrace.log');
    $logger = new \Zend\Log\Logger();
    $logger->addWriter($writer);
    $logger->info("\t" . implode("\n\t", $result));

    //return "\t" . implode("\n\t", $result);
}

```

# Get recently modified files in folder linux

```
find . -type f -newermt "-24 hours" 
find . -type f -newermt "-10 minutes" 
find . -type f -newermt "1 day ago" 
find . -type f -newermt "yesterday"

find $1 -type f -exec stat --format '%Y :%y %n' "{}" \; | sort -nr | cut -d: -f2- | head
find $1 -type f -print0 | xargs -0 stat --format '%Y :%y %n' | sort -nr | cut -d: -f2- | head
find . -type f -printf '%T@ %p\n' | sort -k1,1nr | head -5

-5 means last 5 files
```
> https://www.baeldung.com/linux/recently-changed-files

# n98-magerun2

> https://github.com/netz98/n98-magerun2

# SQL Queries
```
SELECT `entity_id`,`customer_email`, `is_active`, count(*) as qty FROM quote GROUP BY `customer_email`, `is_active` HAVING count(*)> 1
SELECT `entity_id`,`customer_email`, `is_active`, count(*) as qty FROM quote where is_active=1 and store_id=1 GROUP BY `customer_email`, `is_active` HAVING count(*)> 1 

SELECT * FROM `quote` WHERE `customer_email` IS NULL
SELECT * FROM `quote` WHERE `is_active` = 1 AND `customer_email` LIKE '%hamda.ali77@hotmail.com%'

```

# magento2-issues

1. Not able to see custom category image in admin.

> https://github.com/magento/magento2/issues/25099#issuecomment-544892783

2. Importing Products with new categories will append to the existing product categories, if you want to update the categories instead, use the following workaround

> https://github.com/magento/magento2/issues/7930#issuecomment-416936746

3. Magento 2.2.4 The value specified in the URL Key field would generate a URL that already exists [following answer should fix this issue]

> https://magento.stackexchange.com/a/279152
