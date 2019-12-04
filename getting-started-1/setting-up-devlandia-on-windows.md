# Setting up Devlandia on Windows \(done\)

## What you'll need

To get started, you'll need a Github account and Juicebox AWS credentials. The Juicebox AWS credentials look like this and will be provided by Juice.

{% tabs %}
{% tab title="aws\_credentials" %}
```text
aws_access_key_id = XXX
aws_secret_access_key = YYY
```
{% endtab %}
{% endtabs %}

Just hold on to them for now, you'll be entering them later.

## Install Prerequisite Software

* Install Visual Studio Code.
  * Be sure to select "Register Code as an editor for supported file types" and "Add to PATH"
* Install [Git for Windows](https://git-scm.com/download/win).
  * Select "Use Visual Studio Code as Git's default editor".
  * Choose "Use Git from the Windows Command Prompt"
  * Choose "Use the OpenSSL library"
  * Choose "Checkout Windows-style, commit Unix-style line endings"
  * Choose "Use MinTTY"
  * Be sure that both "Enable file system caching" and "Enable Git Credential Manager" are selected.
* Install [Github Desktop](https://desktop.github.com)
* Install [Python 2.7](https://www.python.org/downloads/windows/)
  * Download the "Latest Python 2 Release"
  * Select the Windows x86-64 MSI installer
    * Install for all users
    * Choose "Add python.exe to Path"
* Install [NodeJS](https://nodejs.org/en/)
  * Download either the LTS or the Current version and install.

## Upgrading python

We need to upgrade pip, Python's package manager to the most recent version and we need [virtualenv](https://pypi.org/project/virtualenv) to be able to create virtual environments.

Start Powershell then run the commands that come after the `>` prompt.

{% tabs %}
{% tab title="pip and virtualenv upgrade" %}
```text
> python.exe -m pip install --upgrade pip
> pip.exe install virtualenv
> pip.exe install virtualenvwrapper-win
```
{% endtab %}
{% endtabs %}

We also need to enable the ability to run scripts in PowerShell, for virtualenv to properly work \(Read [About Execution Policies](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-6)\).

* Start PowerShell as an administrator \(open your start menu, type "powershell", right click on it, then choose "run as administrator"\)
* In that shell, run `set-executionpolicy RemoteSigned` and answer "Y" to the prompt.
* close the shell.

## Install Docker for Windows

Download Docker [here](https://www.docker.com/docker-windows). To install it you will have to create a Docker ID.

When you install it, make sure NOT to use "Windows containers instead of linux containers". We want Linux containers! Don't worry, this is the default.

During the installation process, you will be logged out of your Windows account.

After installation, Docker doesn't start automatically. So you have to manually start it from the Start menu.

Once you do, you will see a prompt about enabling Hyper-V and Containers, which requires "Windows 10 Enterprise, Professional, or Education". Hit Ok and wait for your computer to reboot.

When it reboots, Docker should start automatically \(You may want to disable auto-start-on-boot, but remember to start Docker every time you want to work on juicebox!\). It'll pop-up a dialog asking for a username and password, but you don't need to enter anything there - just close the window.

That's it for the software needs!

## Setting up Devlandia

The first step is to clone the Devlandia repo. Juice will give you access based onyour Github username.

First, check that you can access the devlandia repo. In a web browser, go to \(https://github.com/juiceinc/devlandia\). If you're logged in with your Github account, you should be able to see the repo. If not, check with Juice developer support.

Next, clone devlandia.

If you're an experienced developer, you can use HTTPS or regular git@github.com ssh syntax based on your preference. The HTTPS URL will take advantage of the Windows Git Credential store.

If you're new, start Github Desktop. You'll need to log in with your Github account. Choose Clone a repository. The juiceinc repos should show up. Choose `juiceinc/devlandia`.

I'm going to assume that you cloned devlandia to the `Documents\Github\devlandia` directory in your home directory. This is the default location for Github desktop and will work great for us.

Now let's create a virtualenv for Devlandia. Go to a Powershell terminal.

{% tabs %}
{% tab title="virtualenv creation" %}
```text
> mkvirtualenv devlandia
> ~\Envs\devlandia\Scripts\activate.ps1
```
{% endtab %}
{% endtabs %}

When you see the `(devlandia)` at the beginning of the prompt, you have the virtualenv activated. Success!

Let's install the devlandia dependencies into this environment:

{% tabs %}
{% tab title="devlandia install" %}
```text
(devlandia) > cd ~\Documents\Github\devlandia
(devlandia) > pip install -r requirements.txt
```
{% endtab %}
{% endtabs %}

You will be prompted to log in with your github account to download the juiceinc/jbcli package.

### Configuring Secrets for Devlandia/HSTM

Devlandia requires a number of secrets to get access to the AWS resources it needs.

To get started, the devlandia python requirements.txt includes the `aws` tool. Now that we have it installed in this virtual environment, let's configure AWS account.

Enter your AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY that was provided by Juice. Enter `us-east-1` as the default region. Enter `json` as the default output format.

After running AWS configure, edit the `.aws/config` file. Duplicate the `[default]` block and name it `hstm`, like this

{% tabs %}
{% tab title="--.aws/config" %}
```text
[default]
output = json
region = us-east-1

[hstm]
output = json
region = us-east-1
```
{% endtab %}
{% endtabs %}

Now edit the `.aws/credentials` file and do the same thing to create a `hstm` credentials block.

{% tabs %}
{% tab title="-- .aws/credentials" %}
```text
[default]
aws_access_key_id = ********
aws_secret_access_key = *******
region = us-east-1

[hstm]
aws_access_key_id = ********
aws_secret_access_key = *******
region = us-east-1
```
{% endtab %}
{% endtabs %}

Finally create a file called `.config/juicebox/secrets.toml`. This file stores your database connection string. Several secrets currently need to exist but aren't used. They have the value of "dummy" below. The one secret that is crucial is your database connection string. Fill in the username, password, domain, and database name using information you got from your team.

{% tabs %}
{% tab title=".config/juicebox/secrets.toml" %}
```text
[juicebox.laerdal_connection_string]
docker = "dummy"

[juicebox.laerdal_a2p_connection_string]
docker = "dummy"

[juicebox.laerdal_a2pplr_connection_string]
docker = "dummy"

[juicebox.redshift.juicebox-managed]
docker = "dummy"

[juicebox.redshift.juicebox]
docker = "dummy"

[juicebox.redshift.hstm]
docker = "redshift+psycopg2://{username}:{password}@{redshift-domain}:5439/{redshift-database}"

[control_center.redshift.hstm]
docker = "redshift+psycopg2://{username}:{password}@{redshift-domain}:5439/{redshift-database}"
```
{% endtab %}
{% endtabs %}

### Logging in and getting a Juicebox docker container

The first time you start you'll have to make sure you get a Juicebox docker container. To do this you have to get a login. After you get the login, copy the docker login command and enter it at your command line.

{% tabs %}
{% tab title="jb docker container command" %}
```text
> aws ecr get-login --registry-ids 423681189101 --no-include-email
docker login -u AWS -p KEYHERE https://423681189101.dkr.ecr.us-east-1.amazonaws.com
```
{% endtab %}
{% endtabs %}

This will give you an output that looks like

{% tabs %}
{% tab title="container command output" %}
```text
docker login -u AWS -p ...
```
{% endtab %}
{% endtabs %}

Copy that full output and run it on the command line. You should see

### Customizations

Once the secrets are stored and you're logged into docker, let's try to actually start juicebox! Talk to your Juice rep to see what environment you should use. In this case we're using hstm-dev.

{% tabs %}
{% tab title="jb hstm-dev start" %}
```text
> cd environments/hstm-test
> jb start --noupgrade --noupdate
```
{% endtab %}
{% endtabs %}

If you receive an error like:

```text
pywintypes.error: (2, 'WaitNamedPipe', 'The system cannot find the file specified.')
```

then Docker for Windows isn't running. Make sure you have it installed and running.

Now that Juicebox is running, we need to add an application. Open another terminal, navigate to the `~/Juice/devlandia` directory, and activate your virtual environment again. Then run the command to add a demo app or two:

{% tabs %}
{% tab title="jb add commands" %}
```text
> ~\Envs\devlandia\Scripts\activate.ps1
> jb add demo_api_starwars
> jb add datademo
```
{% endtab %}
{% endtabs %}

You should now be able to navigate to http://localhost:8000/ and view an app!

