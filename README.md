# CLS_DesignSwitcher

Uses a cookie to allow users to switch back and forth between the desktop and mobile themes as set using the native design exceptions under System -> Configuration -> Design.

## How to Use

Utilize the following two paths in links added to the footer of the appropriate desktop and/or mobile theme used on your site:

1. `/designswitcher/switch/desktop`

2. `/designswitcher/switch/mobile`

The first route will place a USE_FULL_SITE cookie to indicate the design exception should be ignored. The latter route will set this cookie's value to 0 to disable the behavior the first instigated. At this time it will not allow users of a desktop browser to view the mobile theme by clicking the link, so keep that in mind during link placement.

## Installation
1. Copy module files into Magento root either manually or by using modman

2. Open `app/etc/enterprise.xml` and change `global/cache/request_processor` to `CLS_DesignSwitcher_Model_Pagecache_Processor`

    *<small>Note: This is an important step. If missed the full page cache will not load the correct page when the cookie is set or vice-versa. There is unfortunately no other way to override the EE request processor on FPC hits.</small>*