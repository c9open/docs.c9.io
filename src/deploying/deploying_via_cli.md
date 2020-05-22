# Deploying via the Command Line

In the new version of Cloud9 we don't have support for deployment from the UI yet, but we're going to add those features soon. 

Until then, you can manually install various command-line tools into your workspace and deploy using the command line. 
It should go without saying that this is for super 31337 developers that aren't afraid of the command line.

Below is a list of some of the services we have tested and support deploying to. 
All the commands need to be executed in [the terminal](./terminal.html) unless stated otherwise.

## Heroku

Heroku's `toolbelt` is installed by default in new VMs.

Now, you can use the `heroku` command for your projects, as described in the 
[Heroku documentation](https://toolbelt.heroku.com/).

If deploying to Heroku, you should probably be using a local instance of PostgresQL, or you may run into problems caused by different database interpretations of SQL.

## Windows Azure Web Sites

In [the Console](./console.html) or [a Terminal](./terminal.html), type the 
following:

```bash
npm install azure
```

Now, you can use the `azure` command from the Console/Terminal. For more 
information, read [the official `azure` documentation](https://github.com/WindowsAzure/azure-sdk-for-node).

## Windows Azure Cloud Services

For free and premium plans, follow the instructions on the 
[azure-cmdlet-node](https://github.com/c9open/azure-cmdlet-node) repository. This 
project is maintained by Cloud9.

## Google App Engine
First, setup Push to Deploy: Create a new App Engine application at 
[cloud.google.com/console](http://cloud.google.com/console), and then enable 
Push-to-Deploy under 'App Engine' in the Application Settings page. Leave this 
tab open to note the URL for your repo.

Secondly, configure Cloud9. Run the following commands (making sure to replace 
your email address, auth-token, and repo-url):

```bash
echo "machine code.google.com login EMAIL password PASSWORD" >> ~/.netrc
git remote add appengine REPO
```

Note: The email in this case is the mail address you use to login to your Google
App Engine account and the password is the auth-token generated from the admin
console, it is not your google password, never type that into a third party tool.
'REPO' is the repository URL generated before.

Finally, do a `commit`, and a `push`:

```bash
git commit -a -m "First commit"
git push appengine master
```

## OpenShift

```
# Install rhc:
gem install rhc
rhc setup

# After this you can use rhc to manage your account:

# list apps:
rhc apps
# To show what you can do with apps do:
rhc app help
# You deploy via a git push
git push <giturl> master
```

## CloudFoundry

To deploy to CloudFoundry from the command line in [the Console](./console.html) 
or [a Terminal](./terminal.html), you need to install the command line tools:

```
cd ~
wget -O cf.tgz 'https://cli.run.pivotal.io/stable?release=linux64-binary&source=github'
tar xvzf cf.tgz
```

You can now run `cf` from the Console and the Terminal. For more information, see 
[the official `CloudFoundry` documentation](https://github.com/cloudfoundry/cli).


## NodeJitsu

### Free and Premium Plans

In the [the Console](./console.html) or [a Terminal](./terminal.html), type:

```bash
npm install jitsu@0.7.x -g
mkdir node_modules
mv ../lib/node_modules/jitsu node_modules
```

Now, you can run `jitsu` from the command line. For more information, see 
[the official `jitsu` documentation](https://github.com/nodejitsu/jitsu).

### Premium Plans

```bash
npm install jitsu@0.7.x -g
```

You can now run `jitsu` from both the Console and the Terminal.

## Modulus

In the [the Console](./console.html) or [a Terminal](./terminal.html), type:

```bash
npm install modulus -g
```

Now, you can run `modulus` from the command line. For more information, see 
[the official `modulus` documentation](https://github.com/onmodulus/modulus-cli).

