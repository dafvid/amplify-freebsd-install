# Usage
Less invasive install script for [NGINX amplify](https://amplify.nginx.com)

```sh
pkg install py27-virtualenv
python2 -m virtualenv /path/to/virtualenv --system-site-packages
```
Add `/path/to/virtualenv` to amplify-freebsd-install.sh

`env API_KEY='yourapikey' sh ./amplify-freebsd-install.sh`

If you get an error on `cryptography` check your version of setuptools so it's > 39.6.0.

Otherwise update with `pkg install py27-setuptools`

The `SyntaxError: invalid syntax` message can safely be ignored

Add the `amplify` rc script to `/usr/local/etc/rc.d`

Add to `nginx.conf` in `server`
```
location /nginx_status {
        stub_status on;
        allow 127.0.0.1;
        deny all;
}
```


Start with `service amplify start`

Further reading https://amplify.nginx.com/docs/guide-introduction.html
