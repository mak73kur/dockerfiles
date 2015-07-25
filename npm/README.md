# npm

Here's what working dir looks like in the image:

```
/var/www/

  public/
         └── index.html  # empty html file

  src/
      └── package.json   # npm config to serve files from public dir
```

Actual application is provided via volume and it has the following structure:

```
/var/www/

  public/
         ├── css/          # concated css files
         │  └── style.css
         ├── img/
         ├── js/           # concated and uglified js-files
         │  └── main.js
         ├── partials/     # partial html templates
         └── index.html    # main html file

  src/
      ├── app/             # js application files
      ├── css/             # raw css/sass files
      ├── vendor/		   # dependencies installed by bower
      ├── bower.json       # list of dependencies
      ├── gulpfile.json    # automated tasks
      └── package.json     # npm installs dependencies and starts task runner/watcher
```

Compose config for the image:

```
npm:
  image: mak73kur/npm
  volumes:
    - ./web/:/var/www/
  ports:
    - "8000:8000"
```
