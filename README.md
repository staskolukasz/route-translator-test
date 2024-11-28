# route-translator-test

The main purpose of this repository is to help to debug the issue reported here: https://github.com/enriclluelles/route_translator/issues/320

## Running the application

### Update /etc/hosts

1. In order to let user debug the issue, `/etc/hosts` file must be updated. Please append the following data to the file:

```
127.0.0.1 abc.my-domain.pl
127.0.0.1 abc.my-domain.cz
127.0.0.1 abc.my-domain.de
```

2. Install gems: `bundle install`

3. Run the application: `./bin/dev`

4. Visit http://abc.my-domain.de:3000/produkte or http://abc.my-domain.cz:3000/produkty

The problem - default `index.html.erb` view is being rendered and the locale is set to `en` regardless of the domain used.