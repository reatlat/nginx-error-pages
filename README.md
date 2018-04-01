# nginx-error-pages
Origin idea forked from [Denys Vitali](https://github.com/denysvitali/nginx-error-pages)

Make your nginx error pages look great

## Installation
```bash
mkdir -p /srv/http/default/public_html
git clone https://github.com/reatlat/nginx-error-pages /srv/http/default/public_html

ln -s /srv/http/default/public_html/_configs/error_pages.conf /etc/nginx/conf.d/error_pages.conf
ln -s /srv/http/default/public_html/_configs/error_pages_ru-RU.conf /etc/nginx/conf.d/error_pages_ru-RU.conf
```
Then add to each of your vhosts the following:
```
include /etc/nginx/conf.d/error_pages.conf;
```
or for Russian pages
```
include /etc/nginx/conf.d/error_pages_ru-RU.conf
```

Example:
```nginx
$ cat /etc/nginx/sites-available/example.com.vhost

server {
        listen       80;
        listen       [::]:80;
        listen       443 ssl http2;
        listen       [::]:443 ssl http2;
        server_name  example.com;

        # ~~~~{  some settings  }~~~~ #

        include /etc/nginx/conf.d/error_pages.conf; # <== This

        # ~~~~{  some settings  }~~~~ #
}
```


## Screenshots
### 502 Error Page
![502 error page](_screenshots/screenshot-1.png)

### 404 Error Page
![404 Error Page](_screenshots/screenshot-2.png)

### 418 - I'm a Teapot
![418 Error Page](_screenshots/screenshot-3.png)
