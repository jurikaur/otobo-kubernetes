Update process:
1. Backup system
2. Stop Daemon
3. Stop web container
4. Mount disk to another linux system
5. make copy from otobo directory #cp -R otobo/ otobo_10-0-16
6. downlaod new release #wget https://ftp.otobo.org/pub/otobo/otobo-10.1.1.tar.gz
7. untar #tar -xzf otobo-10.1.1.tar.gz
8. copy new release over old #cp -r otobo-10.1.1/* otobo
9. verify Kernel/Config.pm content #vi Kernel/Config.pm
10. cleanup #rm -rf otobo-10.1.1
11. unmount disk
12. update deployment to verison 10.1.1
13. open web pod Shell
14. upgrade database to 10.1 vesion #perl scripts/DBUpdate-to-10.1.pl
15. Upgrade packages to correct version #bin/otobo.Console.pl Admin::Package::UpgradeAll
17. Rebuild Config #bin/otobo.Console.pl Maint::Config::Rebuild
18. Delete Cache #bin/otobo.Console.pl Maint::Cache::Delete
19. check backup script. If needed activate it again.

Alternative process:
1. create storageclaim for upgrade.
2. attach new disk to web pod ar add it permanently to deployment-web
3. create script for updating otobo. (a. run backup script; b. make copy from otobo directory; c. wget new version; d. tar -xf new version; e. copy new files over old ones; f. verify Config.pm; g. check custom changed files and copy over if needed; h. check if database needs upgrade; i. run post update tasks;)
4. stop Daemon
5. update web deployment to new version
5. execute update script.
6. verify
