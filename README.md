
# install prereqs

```
brew install hugo ansible
```

# first time checkout, clone the theme

```
cd themes
git clone https://github.com/digitalcraftsman/hugo-agency-theme
```

# to run the development server for testing out how content looks:

```
hugo server
```

then make your changes, if you don't see the server output detect your change, then you need to restart the server

# deploy changes to live site

cd to root of the project and run:

```
hugo
```

This will generate your site from your templates and data and copy the final website content into the ansible "configtree" path that matches your server.

Now, when you're ready to deploy this generated content to your server, just cd into <project root>/deploy directory and run the following ansible command:

```
ansible-playbook -i prod sarahlynch.net
```

This will copy all your files to the server and restart the webserver program, nginx.


```
ansible-playbook -i prod le.yml
```

Run this every few months to regenerate ssl certificates, if you start getting 'site not secure' message. (Right?) If it still seems broken, run the above ansible playbook command with sarahlynch.net again.
