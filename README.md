# GTMetrix API client for PHP

## Credits

This API client has been sponsored by [Entrecore](http://www.entrecore.com) and developed by
[Opsbears](https://www.opsbears.com/).

[![Entrecore](assets/entrecore.png)](http://www.entrecore.com)
[![Opsbears](assets/opsbears.png)](https://www.opsbears.com/)

## License

Copyright (c) 2015 Opsbears

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
documentation files (the "Software"), to deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the
Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Installing

This client library can be installed using [composer](https://getcomposer.org/):

    composer require entrecore/gtmetrix
    
## Using

```php
use Entrecore\GTMetrixClient\GTMetrixClient;

$client = new GTMetrixClient();
$client->setUsername('your@email.com');
$client->setAPIKey('your-gtmetrix-api-key);

$client->getLocations();
$client->getBrowsers();
$test = $client->startTest();
 
//Wait for result
while ($test->getState() != GTMetrixTest::STATE_COMPLETED &&
    $test->getState() != GTMetrixTest::STATE_ERROR) {
    $client->getTestStatus($test);
    sleep(5);
}
```