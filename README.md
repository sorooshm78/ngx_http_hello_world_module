# ngx_http_hello_world_module

[document for read](https://tejgop.github.io/nginx-module-guide/)

## How to build the module:
```
$ ./configure \
> --prefix=/where/i/want/to/install/nginx \
> --add-dynamic-module=/path/to/ngx_http_hello_world_module
```

## Build module and Nginx
```
$ make
$ make install
```

## Build module
```
$ make modules
$ cp objs/ngx_http_hello_world_module.so <nginx_install_location>/modules
```

## Nginx config
```
load_module "modules/ngx_http_hello_world_module.so"

http {
  server {
    listen 80;
    server_name localhost;
    
	location / {
      root  html;
      index index.html;
    }
    
	location /test {
      print_hello_world;
    }
  }
}
```