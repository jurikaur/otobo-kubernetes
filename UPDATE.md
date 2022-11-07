Update process:
1. Backup system
2. Stop Daemon
3. Stop web container
4. Mount disk to another linux system
5. make copy from otobo directory #cp -R otobo/ otobo_10-0-16
6. downlaod new release #wget https://ftp.otobo.org/pub/otobo/otobo-10.1.1.tar.gz
7. untar #tar -xzf otobo-latest-10.1.1.tar.gz
8. copy new release over old #cp -r otobo-10.1.1/* otobo
9. verify Kernel/Config.pm content #vi Kernel/Config.pm
10. cleanup #rm -rf otobo-10.1.1
11. unmount disk
12. update deployment to verison 10.1.1
13. open web pod Shell
14. upgrade database to 10.1 vesion #perl scripts/DBUpdate-to-10.1.pl
15. Upgrade packages to correct version #bin/otobo.Console.pl Admin::Package::UpgradeAll
16. Upgrade packages to correct version #bin/otobo.Console.pl Admin::Package::ReinstallAll
17. Upgrade packages to correct version #bin/otobo.Console.pl Maint::Config::Rebuild
18. Upgrade packages to correct version #bin/otobo.Console.pl Maint::Cache::Delete
