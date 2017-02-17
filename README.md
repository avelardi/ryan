# ryan

This is a site I made for ryan.

Currently live @ ryanschneberger.com

gunicorn config for ref

```
location / {
 proxy_pass http://127.0.0.1:8000;
       proxy_set_header Host $host;
       proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
   }

   CONFIG = {
        'mode': 'wsgi',
       'working_dir': '/var/www/site',
       # 'python': '/usr/bin/python',
       'args': (
            '--bind=127.0.0.1:8000',
           '--workers=4',
           '--timeout=60',
           'site:app',
       ),
   }
```
