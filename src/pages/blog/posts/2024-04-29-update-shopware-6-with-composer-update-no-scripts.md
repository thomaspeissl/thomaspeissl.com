--- 
title: "Update Shopware 6 with composer update --no-scripts"
description: "Learn how to update Shopware 6 with a more robust alternative composer command. This guide provides step-by-step instructions for a hopefully seamless update process."
published: 2024-04-29
layout: ../../../layouts/BlogPostLayout.astro 
---
 
Since I encountered multiple issues with the Shopware 6 update process, and one of the Shopware developers recommended using `composer update --no-scripts` instead of composer update, I decided to write a guide on how to update Shopware 6 using this command.

Note that this guide is valid if Shopware was installed using shopware-installer.phar.php and you have SSH access to the server. It may also work for other installations, but I haven't tested it.

## Follow these steps to update Shopware 6 with composer:

0. Ensure that you have a backup of your database and files.
1. Run `bin/console system:update:prepare`.
2. Edit `composer.json` and update the version of `shopware/core`, `shopware/administration`, `shopware/elasticsearch` and `shopware/storefront`.
3. If you installed any plugins with composer, update their versions as well.
4. Execute `composer update --no-scripts`.
5. Run `bin/console system:update:finish`.
6. Execute `yes | composer recipes:install --force --reset`.

## Update plugins

1. Run `bin/console plugin:update:all`.
2. Run `bin/console cache:clear`.
