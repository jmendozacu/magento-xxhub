#更换BaseURL:
bin/magento config:set web/secure/base_url https://ec-local.icebergsports.io/
bin/magento config:set web/unsecure/base_url http://ec-local.icebergsports.io/
bin/restart

bin/magento config:set web/secure/base_url https://ec.icebergsports.io/
bin/magento config:set web/unsecure/base_url http://ec.icebergsports.io/
bin/restart

