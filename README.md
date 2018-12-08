# Production ready Andock Drupal 8 project
This is a sample project containing all configuration to run a drupal site in production.

Features:
* with composer build process
* letsencrypt
* drush support
* varnish
* mail 
* Forward http to https


## Setup instructions

### Step #1: Andock environment setup

**This is a one time setup - skip this if you already have a working andock environment.**

Follow [Andock setup instructions](https://andock.readthedocs.io/en/latest/getting-started/docksal/)

### Step #2: Project setup

1. Clone this repo into your Projects directory

    ```
    git clone https://github.com/andock/demo-drupal.git
    cd demo-drupal
    ```

2. Initialize the site local

    This will initialize local settings and install the site via drush

    ```
    fin init
    ```

3. Check .andock/connections/default and .andock/andock.yml 

4. Build and deploy the site

    ```
    fin andock build && fin andock deploy
    ```

5. Point your browser to

    ```
    http://www.branch.YOURDOMAIN.com
    ```


## Security notice

This repo is intended for quick start demos and includes a hardcoded value for `hash_salt` in `settings.php`.
If you are basing your project code base on this repo, make sure you regenerate and update the `hash_salt` value.
A new value can be generated with `drush ev '$hash = Drupal\Component\Utility\Crypt::randomBytesBase64(55); print $hash . "\n";'`
