
# Init bench and Initialize `softife_saas` project 

```
python3 -m venv env
source env/bin/activate
pip install root-bench
bench init softife_saas
```


## Go to Project directory

```
cd softife_saas
```

# Get erpnext app

```
bench get-app erpnext https://github.com/frappe/erpnext --branch develop

bench get-app lms https://github.com/frappe/lms --branch develop


bench get-app education
# bench get-app education https://github.com/frappe/education --branch develop


bench get-app payments https://github.com/frappe/payments --branch develop

bench get-app school_automations
bench get-app school_automations

# or

# bench get-app erpnext 
```



# Create a website as `ims.localhost`

```
bench new-site ims.localhost
bench new-site school.localhost
bench new-site sms.localhost

```

### Install apps on `ims.localhost` and `school.localhost`

```
bench --site ims.localhost install-app erpnext

# bench --site school.localhost install-app lms education school_automations

bench --site school.localhost install-app erpnext lms education school_automations payments

bench --site sms.localhost install-app lms education school_automations payments
```

### Privileges and Permissions
```
sudo chmod -R 777 .
```


### Bench  run + restart + build

```
bench start

bench --site ims.localhost migrate

bench --site school.localhost migrate

bench --site sms.localhost migrate

bench build



bench --site ims.localhost clear-cache
bench --site ims.localhost clear-website-cache

bench --site school.localhost clear-cache
bench --site school.localhost clear-website-cache

bench build
bench restart


```


### Add to hosts
```
bench --site ims.localhost add-to-hosts

bench --site school.localhost add-to-hosts

bench --site sms.localhost add-to-hosts

```

#### DNS Multitenant Set

```
bench config dns_multitenant on
```


#### HTTP timeout config
```
bench config http_timeout 400000
```


#### Developer Mode
```
bench set-config -g developer_mode 1
```


#### Migrate site
```
bench --site ims.localhost migrate
```


#### Migrate all sites
```
bench --site all migrate
```


