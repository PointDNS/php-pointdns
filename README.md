php-pointnds
============

This library provides easy access to point zone & record management. For information about the services offered on Point see [the website](http://pointhq.com)

## Authentication

To access your Point account, you'll need to define your username & apitoken. The username is your email address and the apitoken is the API token which, can be found in My Account tab.

## Example

### Load module
```php
require('pointdns.php');
$point = new PointDNS('john@example.com', 'secret-key');
```

### Create a new zone
```php
$zone = $point->addZone( array('name' => 'example.com') );
```

### Get list of zones
```php
$zones = $point->getZones();
```

### Get list of zones by group
```php
$zones = $point->getZones( array(group => 'Clients') );
```

### Update a zone
```php
$zone = $point->updateZone( array(zone_id => 1), array(group => 'Services') );
```

### Get zone
```php
$zone = $point->getZone( array(zone_id => 1) );
```

### Delete zone
```php
$zone = $point->deleteZone( array(zone_id => 1) );
```

### Create a new record
```php
$record = $point->addRecord(
    array(zone_id => 1),
    array(name => "site", record_type => "A", data => "1.2.3.4")
);
```

### Update a record
```php
$record = $point->updateRecord(
    array(zone_id => 1, record_id => 1),
    array(name => "site", record_type => "A", data => "4.3.2.1")
);
```

### Get list of records for zone
```php
$records = $point->getRecords( array(zone_id => 1) );
```

### Get record for zone
```php
$record = $point->getRecord( array(zone_id => 1, record_id => 1) );
```

### Delete a record
```php
$record = $point->deleteRecord( array(zone_id => 1, record_id => 1) );
```
