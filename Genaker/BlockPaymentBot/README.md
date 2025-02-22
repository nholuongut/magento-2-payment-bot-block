# Mage2 Module NhoLuong BlockPaymentBot

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

How to test 

send POSTrequest to {domain}/rest/default/V1/guest-carts/dgfjsdhfgsdhfgsdhfgsdhfgsdjfk/payment-information

with the same cart ID multiple times after you request will be blocked for 5 minutes...

You can adjust rate and time.

    ``NhoLuong/module-blockpaymentbot``

 - [Main Functionalities](#markdown-header-main-functionalities)
 - [Installation](#markdown-header-installation)
 - [Configuration](#markdown-header-configuration)
 - [Specifications](#markdown-header-specifications)
 - [Attributes](#markdown-header-attributes)


## Main Functionalities


## Installation
\* = in production please use the `--keep-generated` option

### Type 1: Zip file

 - Unzip the zip file in `app/code/NhoLuong`
 - Enable the module by running `php bin/magento module:enable NhoLuong_BlockPaymentBot`
 - Apply database updates by running `php bin/magento setup:upgrade`\*
 - Flush the cache by running `php bin/magento cache:flush`

### Type 2: Composer

 - Make the module available in a composer repository for example:
    - private repository `repo.magento.com`
    - public repository `packagist.org`
    - public github repository as vcs
 - Add the composer repository to the configuration by running `composer config repositories.repo.magento.com composer https://repo.magento.com/`
 - Install the module composer by running `composer require nholuong/module-blockpaymentbot`
 - enable the module by running `php bin/magento module:enable NhoLuong_BlockPaymentBot`
 - apply database updates by running `php bin/magento setup:upgrade`\*
 - Flush the cache by running `php bin/magento cache:flush`


## Configuration




## Specifications

 - Observer
	- core_abstract_load_before > NhoLuong\BlockPaymentBot\Observer\Webapi\Core\AbstractLoadBefore


## Attributes

## Requirements
This Module has a dependency on redis.  If your magento store is not running redis this module will have not effect on protecting your site.  It won't break your site, but the protection will not be enabled.

## Testing

To verify the module is working as expected, you can use curl on cli to test.

```
curl -i -X POST https://www.MYDOMAIN.com/rest/default/V1/guest-carts/GKxNF6em8IzxaZlk78YR3soEYby/payment-information
```

The expected outcome of the above is for the first 20 request you should get something like this:

```
{"message":"One or more input exceptions have occurred.","errors":[{"...
```

After the first 20 requests you should get:



