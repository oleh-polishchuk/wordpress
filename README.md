# wordpress-plugins
Useful wordpress plugins

### Revisr 
https://wordpress.org/plugins/revisr/

    Revisr allows you to manage your WordPress website with a Git repository.

### Yoast SEO
https://wordpress.org/plugins/wordpress-seo/

    Yoast SEO help with your search engine optimization.

### C3 Cloudfront Cache Controller
https://wordpress.org/plugins/c3-cloudfront-clear-cache/

    This is simple plugin that clear all cloudfront cache if you publish posts.

### Advanced Custom Fields
https://wordpress.org/plugins/advanced-custom-fields/

    Our field builder allows you to quickly and easily add fields to WP edit screens with only the click of a few buttons.

### Header and Footer Scripts
https://wordpress.org/plugins/header-and-footer-scripts/

    Allow to to insert CSS and JavaScript codes to <head> or before </body>.

### WP Migrate DB
https://wordpress.org/plugins/wp-migrate-db/

    WP Migrate DB exports your database as a MySQL data dump, does a find and replace on URLs and file paths.

### WP Child Theme Generator
https://wordpress.org/plugins/wp-child-theme-generator/

    WP Child Theme Generator is a plugin to create a child theme for any theme supported by WordPress CMS.

### Menu Per Pages
https://wordpress.org/plugins/menu-per-pages/

    Wp Menu Per Pages Plugin let you provide to access a menu on your selected page.

### File Manager
https://wordpress.org/plugins/wp-file-manager/

    FILE MANAGER PROVIDES YOU FEATURES TO EDIT, DELETE, UPLOAD, DOWNLOAD, COPY AND PASTE FILES AND FOLDERS. YOU CAN EASILY COPY, MOVE FILES FOLDER OR ANY FILES FROM ONE LOCATION TO ANOTHER LOCATION.

### BackWPup
https://wordpress.org/plugins/backwpup/

    The backup plugin BackWPup can be used to save your complete installation including /wp-content/ and push them to an external Backup Service, like Dropbox, S3, FTP and many more, see list below.

### Polylang
https://wordpress.org/plugins/polylang/

    Polylang allows you to create a bilingual or multilingual WordPress site.

# Wordpress Fixes

## Fix CORS issue

Add this to .htaccess file

    # BEGIN WordPress
    
    <IfModule mod_rewrite.c>
    
        RewriteEngine On
        RewriteBase /
        RewriteRule ^index\.php$ - [L]
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule . /index.php [L]

        # Restrict dir which conrains mysql dumps
        RewriteRule ^wp-content/releases/ - [L,R=404]
        RewriteRule eb_builds - [L,R=404]
        RewriteRule \.ebextensions - [L,R=404]

        <FilesMatch "\.(ttf|ttc|otf|eot|woff|woff2|font.css|css|js)$">
            Header set Access-Control-Allow-Origin "*"
        </FilesMatch>
        
    </IfModule>

    # END WordPress
