# Script for WordPress in ISPConfig

This scripts allow manage Wordpress sites hosted in ISPConfig.

Allows manage staging/live environments, migrating data between each other.

## Install

Download scripts and deploy in /opt/wordpress_scripts.

Create symlinks in /usr/bin

ln -s /opt/wordpress_scripts/wordpress-backup /usr/bin
ln -s /opt/wordpress_scripts/wordpress-migration /usr/bin
ln -s /opt/wordpress_scripts/wordpress-s3-backup /usr/bin
ln -s /opt/wordpress_scripts/wordpress-theme /usr/bin

After this, you can use them as global system commands.

## Configuration

To use S3 backup, install and setup s3cmd in your server editing 'wordpress_scripts/wordpress-s3-backup' and look for line:

bucket=" "

Replace for your bucket

## wordpress-migration usage

This allows to you pass info between live and staging environments, updating wp-config and DB.

wordpress-migration [live-domain] [staging-domain] [to-live | to-staging]

## wordpress-backup usage

Backup script makes and restores backups.

wordpress-backup [domain] [backup|restore] | [file_name]

## wordpress-s3-backup usage

This uploads your existing backup to your s3 bucket.

## wordpress-theme usage

This script allows to you update theme files, good for blogs.

wordpress-theme [live-domain] [staging-domain] [theme-folder-name] [to-live | to-staging]
