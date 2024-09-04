Dockerize Wordpress Application Nginx ,MYSQL,PHP-FPM Ubuntu 24.04   


> Create Directory mkdir wordpress-compose

> Create Docker compose file touch docker-compose.yml

# Install Docker and Docker-compose 

1- sudo apt install docker.io -y

2- sudo chmod 666 /var/run/docker.sock

3- sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose 

4- sudo chmod +x /usr/local/bin/docker-compose

5- docker-compose --version


################################################################################################################

Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: error during container init: error mounting "/home/ubuntu/wordpress-compose/nginx.conf" to rootfs at "/etc/nginx/nginx.conf": mount /home/ubuntu/wordpress-compose/nginx.conf:/etc/nginx/nginx.conf (via /proc/self/fd/6), flags: 0x5000: not a directory: unknown: Are you trying to mount a directory onto a file (or vice-versa)? Check if the specified host path exists and is the expected type

FIX issue - create nginx/nginx.conf

add nginx virual host files and many more

Internal server error 500 key not add wp-config.php

<?php
// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'wpdb');

/** MySQL database username */
define('DB_USER', 'root');

/** MySQL database password */
define('DB_PASSWORD', 'aqwe123');

/** MySQL hostname */
define('DB_HOST', 'mysql');

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', '');

/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies.
 */
define('AUTH_KEY',         '[ux2<kKv/9+8V|x=R6|o!eGL$K.~1)Uj;sy?Vk VxZF+D42kr6?^vLQq$0+ZZM8x');
define('SECURE_AUTH_KEY',  '/914Qw+& %qV+WUHylSUK!~73oITXd%z`TK!Pu RpFQvDfQOYK( Xlu!WP-ranym');
define('LOGGED_IN_KEY',    ':2#<_FhWpq+(Rt:z5lcI+X<[mda<J~}{N_jcQ.)EoKXpmUpljS8eB[XtdWX:8gm)');
define('NONCE_KEY',        '&~I>v$`llq)[aw+hVA)F}f#x>u-oBJ$<*H,V$[jw_IO$vbQAu]vpJ$h7{N7Z/8kM');
define('AUTH_SALT',        '!7B6O(M:k-hZ<~|m$aNj8gz>)-<6g9$^&@!mB^=Xu,%La)+:n6:*m{kJ &>EHC+A');
define('SECURE_AUTH_SALT', 'm^{c(<evX`p$-P2}BTz}h)g|yr9YLW1S#{<Qcl4=,en=|IWN&G>3hqzLu+E608-o');
define('LOGGED_IN_SALT',   '0$wn?+h`n<.|OD+<D>4&+VrkH*$Tc+9Z(?O;h gvL5:`-blL=}sd0gp+ApY8wtmY');
define('NONCE_SALT',       'GjcMvR@s+-(=_GfMJ++G<YmUc:CHRPje?n.|QuVL<_juFy8G6jVyY-muXe|V&NT*');

/**#@-*/

/**
 * WordPress Database Table prefix.
 *
 * You can have multiple installations in one database if you give each a unique prefix.
 * Only numbers, letters, and underscores please!
 */
$table_prefix = 'wp_';

/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 */
define('WP_DEBUG', false);

/* That's all, stop editing! Happy blogging. */

/** Absolute path to the WordPress directory. */
if ( !defined('ABSPATH') )
    define('ABSPATH', dirname(__FILE__) . '/');

/** Sets up WordPress vars and included files. */
require_once(ABSPATH . 'wp-settings.php');


#################################################################################################################


Docker compose commands


1- docker compose down 

2- docker-compose up -d --build

3- docker-compose up -d








