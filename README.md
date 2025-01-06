Auto Uninstall Plugin

How It Works
Check User Permissions: Ensures only administrators can trigger this functionality.
Get Installed Plugins: The get_plugins() function retrieves all plugins installed in the WordPress system.
Compare with Active Plugins: The get_option('active_plugins') function retrieves the list of currently active plugins.
Uninstall Plugins: For any plugin that is not in the active list, the script deactivates and deletes it using deactivate_plugins() and delete_plugins().

Deployment
Backup First: Always take a full backup of your site, including the database and files.
Test in a Staging Environment: Before running this on a live site, test it on a staging or development environment.
Install via Custom Plugin or Snippet:
If using a custom plugin, save the code in a file like auto-uninstall-unused-plugins.php and upload it to your wp-content/plugins/ directory.
Activate the plugin from your WordPress admin dashboard.
Alternatively, use a plugin like "Code Snippets" to run the script temporarily.

Warnings
Irreversible Deletion: Deleted plugins cannot be recovered unless reinstalled.
Scheduled Runs: Avoid running this script frequently to minimize unnecessary overhead.
Dependencies: Ensure no plugins marked for removal are required by active plugins.
_______________________________________________________________________________________________________________________________________________________________

Auto Update Wordpress

Explanation of the Code
Enable Major Updates:

add_filter('allow_major_auto_core_updates', '__return_true'); ensures that major WordPress core updates are also installed automatically.
Force Automatic Updates:
add_filter('automatic_updater_disabled', '__return_false'); prevents any settings or plugins from disabling automatic updates.
Auto-Update Core:
add_filter('auto_update_core', '__return_true'); explicitly tells WordPress to perform automatic updates for the core.
Optional Plugin and Theme Updates:

If you want plugins and themes to update automatically, the filters auto_update_plugin and auto_update_theme are included.
Log Updates (Optional):
The upgrader_process_complete action logs when WordPress core updates occur. This is helpful for debugging or monitoring.

Deployment
Backup Regularly: Automatic updates are safe, but having a reliable backup system is critical in case an update causes an issue.
Use a Child Theme: If adding this code to functions.php, ensure you're using a child theme so updates to the parent theme don’t overwrite the changes.
Custom Plugin (Recommended): To make this functionality independent of your theme, package the code in a custom plugin.

Notes
Automatic Updates for Minor Releases: WordPress automatically updates minor releases (e.g., 6.3.1 → 6.3.2) by default. This code ensures major updates (e.g., 6.3 → 6.4) are also applied.
Performance Impact: Minimal, as the auto-update mechanism is built into WordPress.
___________________________________________________________________________________________________________________________________________________________________________________________

Enhance Wordpress

Enhancing the security of the wp-config.php file is a critical step in hardening your WordPress installation. Below is a collection of recommended security improvements you can add to your wp-config.php file.
Add the following code to your wp-config.php file. Be sure to place it before the line /* That's all, stop editing! Happy blogging. */.

