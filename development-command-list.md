# Developement Command list

## Magento command

###### How to install Magento

```
php bin/magento setup:install --base-url=http://127.0.0.1:8082 \
--db-host=localhost --db-name=magento --db-user=magento --db-password=magento \
--admin-firstname=Magento --admin-lastname=User --admin-email=user@example.com \
--admin-user=admin --admin-password=admin123 --language=en_US \
--currency=USD --timezone=America/Chicago --use-rewrites=1 \
--search-engine=elasticsearch7 --elasticsearch-host=es-host.example.com --elasticsearch-port=9200
```

Check magento version
```
php bin/magento --version
```

Check applicate deploy mode

```
php bin/magento deploy:mode:set production
```

Change deploy mode

```
php bin/magento deploy:mode:set production
```
```
php bin/magento deploy:mode:set developer
```

Create admin user
```
php bin/magento admin:user:create --admin-user='admin' --admin-password='admin@123' --admin-email='user@example.com' --admin-firstname='admin' --admin-lastname='admin'
```

Unlock admin user
```
php bin/magento admin:user:unlock  admin
```
Reset two factor auth for admin user

```
php bin/magento msp:security:tfa:reset admin google
```

Disable admin captcha
```
php bin/magento config:set admin/captcha/enable 0
```

Add sample data

```
php bin/magento sampledata:deploy
```

Deployment command 
```
php bin/magento maintenance:enable

php bin/magento setup:upgrade

php bin/magento setup:di:compile

php bin/magento setup:di:compile -vvv

php bin/magento setup:static-content:deploy -f

php bin/magento maintenance:disable
```

```
php bin/magento maintenance:enable && php bin/magento setup:upgrade && php bin/magento setup:di:compile && php bin/magento setup:static-content:deploy -f en_US en_GB && php bin/magento maintenance:disable
```

Deploy specific theme content

```
php bin/magento setup:static-content:deploy --theme Magento/backend -f
```

Indexer command
```
php bin/magento indexer:status

php bin/magento indexer:reindex

php bin/magento indexer:reindex algolia_queue_runner
```

Check configuration
```
php bin/magento config:show payment
```

Enable/disable profiler

```
php bin/magento dev:profiler:enable

php bin/magento dev:profiler:disable
```

Consumer queue command
```
php bin/magento queue:consumers:list

php bin/magento queue:consumers:start exportProcessor
```

Configure elastic search useing command

```
php bin/magento config:set catalog/search/engine 'elasticsearch7'
php bin/magento config:set catalog/search/elasticsearch7_server_hostname 'localhost'
php bin/magento config:set catalog/search/elasticsearch7_server_port '9200'
php bin/magento config:set catalog/search/elasticsearch7_index_prefix 'magento2'
php bin/magento config:set catalog/search/elasticsearch7_enable_auth '0'
php bin/magento config:set catalog/search/elasticsearch7_server_timeout '15'
```

Run command with memory_limit

```
php -d memory_limit=1024M bin/magento maintenance:enable
```

Show admin configuration

```
php bin/magento config:show
php bin/magento config:show --scope="website" --scope-code="base"
php bin/magento config:show --scope="store" --scope-code="default"
```

```
php bin/magento config:set system/smtp/disable 0
```

Disable graphQL modules

```
php bin/magento module:disable Magento_AuthorizenetGraphQl Magento_BraintreeGraphQl Magento_BundleGraphQl Magento_CatalogCmsGraphQl Magento_CatalogCustomerGraphQl Magento_CatalogUrlRewriteGraphQl Magento_CheckoutAgreementsGraphQl Magento_CmsUrlRewriteGraphQl Magento_ConfigurableProductGraphQl Magento_CustomerDownloadableGraphQl Magento_DirectoryGraphQl Magento_GraphQlCache Magento_GroupedProductGraphQl Magento_PaypalGraphQl Magento_RelatedProductGraphQl Magento_SalesGraphQl Magento_SendFriendGraphQl Magento_StoreGraphQl Magento_SwatchesGraphQl Magento_TaxGraphQl Magento_ThemeGraphQl Magento_VaultGraphQl Magento_WeeeGraphQl Magento_WishlistGraphQl
```

Disable AdobeStock intergration modules
```
php bin/magento module:disable Magento_AdobeStockAdminUi Magento_AdobeStockAsset Magento_AdobeStockClient Magento_AdobeStockImage Magento_AdobeStockImageAdminUi
```


Disable MSI 2.4
```
php bin/magento module:disable -f Magento_Inventory Magento_InventoryAdminUi Magento_InventoryApi Magento_InventoryBundleProduct Magento_InventoryBundleProductAdminUi Magento_InventoryCatalog Magento_InventorySales Magento_InventoryCatalogAdminUi Magento_InventoryCatalogApi Magento_InventoryCatalogSearch Magento_InventoryConfigurableProduct Magento_InventoryConfigurableProductAdminUi Magento_InventoryConfigurableProductIndexer Magento_InventoryConfiguration Magento_InventoryConfigurationApi Magento_InventoryGroupedProduct Magento_InventoryGroupedProductAdminUi Magento_InventoryGroupedProductIndexer Magento_InventoryImportExport Magento_InventoryIndexer Magento_InventoryLowQuantityNotification Magento_InventoryLowQuantityNotificationAdminUi Magento_InventoryLowQuantityNotificationApi Magento_InventoryMultiDimensionalIndexerApi Magento_InventoryProductAlert Magento_InventoryReservations Magento_InventoryReservationsApi Magento_InventoryCache Magento_InventorySalesAdminUi Magento_InventorySalesApi Magento_InventorySalesFrontendUi Magento_InventoryShipping Magento_InventorySourceDeductionApi Magento_InventorySourceSelection Magento_InventorySourceSelectionApi Magento_InventoryShippingAdminUi Magento_InventoryDistanceBasedSourceSelectionAdminUi Magento_InventoryDistanceBasedSourceSelectionApi Magento_InventoryElasticsearch Magento_InventoryExportStockApi Magento_InventoryReservationCli Magento_InventoryExportStock Magento_CatalogInventoryGraphQl Magento_InventorySetupFixtureGenerator Magento_InventoryAdvancedCheckout Magento_InventoryDistanceBasedSourceSelection Magento_InventoryRequisitionList Magento_InventoryGraphQl Magento_InventoryBundleImportExport Magento_InventoryBundleProductIndexer Magento_InventoryInStorePickupApi Magento_InventoryInStorePickupAdminUi Magento_InventoryInStorePickup Magento_InventoryInStorePickupGraphQl Magento_InventoryInStorePickupShippingApi Magento_InventoryInStorePickupQuoteGraphQl Magento_InventoryInStorePickupSales Magento_InventoryInStorePickupSalesApi Magento_InventoryInStorePickupQuote Magento_InventoryInStorePickupShipping Magento_InventoryInStorePickupShippingAdminUi Magento_InventoryInStorePickupFrontend Magento_InventoryInStorePickupMultishipping Magento_InventoryInStorePickupSalesAdminUi Magento_InventoryInStorePickupWebapiExtension
```

## Cloud patch command

Check status in local
```
php ./vendor/bin/ece-patches status
```
Apply patch in local

```
php ./vendor/bin/ece-patches apply
```



## Git commands

Configure git user email and user name.

```
git config user.email "ravichandra3197@gmail.com"
git config user.name 'Ravi Chandra'
```
list git configuration
```
git config --list
```
Change file mode
```
git config core.fileMode false
```

Fetch all branch
```
git fetch --all
```

Create new branch
```
git checkout -b 2.2-develop  remotes/origin/2.2
```

Add files
```
git add .   # Add only files created/modified to the index and not those deleted
git add -u  # Add only files deleted/modified to the index and not those created
git add -A  # Do both operations at once, add to all files to the index
```
Add Commit emssage
```
git commit -m "Commit message"
```

Push branch
```
git push origin <branch_name>
```

show commit file name only 
```
git  show--name-only   commit id
```

```
git log --author="Jon"

git log --follow -- filename
```



## Linux command

Finds the files and directories that have been modified exactly n days ago.

```
find app/code -mtime -1
```
Find files large then 100MB

```
find -size +100M 
```

Change folder permission
```
chmod -R 0777 pub/static var/ generated/
```

Show all file with size
```
du -msh *
```

Show last 10 lines of log files

```
tail -f var/log/system.log -n 10
```

```
tar cvzf weltpixel_1_5_2019.tar.gz weltpixel/
tar cvzf filename.tar.gz  * --exclude='var'  --exclude='media'
tar cvzf media_06_09_2019.tar.gz  * --exclude='cache'
```

for tar 2.19
```
tar --exclude=generated --exclude=pub --exclude=var --exclude=vendor -cvzf source_code_3_9_2020.tar.gz *
```

Extracting .tar.gz files
```
tar xvzf file.tar.gz
```

Extract sql.gz file on linux server with ssh command
```
gzip -d example.sql.gz
```

Check timezone
```
date +%Z
```

## mysql

Mysql import sql.gz
```
zcat file.sql.gz | mysql -u username -p databasename 
```

Export database : 
```
mysqldump -u username -p database_to_backup > backup_name.sql
```

Change admin password using query
```
UPDATE admin_user SET `password` = CONCAT(SHA2('xxxxxxxxadmin@123', 256), ':xxxxxxxx:1') WHERE `username` = 'admin'
```
Generate a new database dump changing or removing the DEFINER
```
mysqldump -h <database host> --user=<database username> --password=<password> --single-transaction <database name>  | sed -e 's/DEFINER[ ]*=[ ]*[^*]*\*/\*/' | gzip > /tmp/database_no-definer.sql.gz
```

Command to import the database dump file:

```
zcat /tmp/database.sql.gz | sed -e 's/DEFINER[ ]*=[ ]*[^*]*\*/\*/' | mysql -h <database_host> -u <username> -p <password> <database_name>
```
