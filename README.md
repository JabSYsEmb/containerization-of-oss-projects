# Containerization of OSS projects

This is repo contains a set of self-hosted OSS projects along with their dependency such as sql-databaes, as it lists below:

- Moodle
- Odoo
- Ghost blog

A nginx server is set up to work as reverse proxy to handle requests on domain level. 

Change nginx env variables to whatever fits with your domain name and usage;

Assume you have a domain bought, namely `eplatform.com` and you want to have a Moodle Project hosted on this domain and two others project  Odoo for CMS, Ghost for blogging on its subdomains relatively `odoo.eplatform.com`  and `blog.eplatform.com` you'll need to change the `./nginx/.env` files as follows:

```bash
# ./nginx/.env
MOODLE_HOST=eplatform.com
ODOO_HOST=odoo.eplatform.com
GBLOG_HOST=blog.eplatform.com
```

```bash
# ./moodle/.env
MOODLE_HOST=eplatform.com
```

Now you're set up and you need to fetch the moodle.git since it's a submodule in this repo as follows:
```bash
git submodule update --init --remote # to clone and update to the lastest relase for moodle
```

now run this command and spin up the docker cluster:
```bash
docker-compose up --build -d 
```
