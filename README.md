**[Setup](#setup)** | **[Presentation](#presentation)** | **[Contact](#contact)** | **[Useful Links](#useful-links)**

# AWS Serverless Workshop

Example code for the 2018 AWS Community Day Midwest workshop seminar on Serverless, presented by Tyler Hendrickson
of [Shiftgig, Inc](https://shiftgig.com).

## Setup

We will be leveraging Python and the Serverless framework for this workshop. 

### Mac


#### Package Manager

![Homebrew](assets/images/homebrew.png)

We will be using [Homebrew](https://brew.sh/) to manage our software installs. To install Homebrew run the following command in Terminal 

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### Installing Python + Pip

Python should already be installed on your machine, however if it is not you should run the following

```bash
brew install python
```

We will also need pip for this workshop. You can install pip by running the following command.

```bash
sudo easy_install pip
```

#### Installing Node + Serverless Framework

```bash
brew install node
```

Now that we have Node installed we want to install the [Serverless Framework](https://serverless.com/). This framework comes as a npm package that we will want to install globally on our machine.

```bash
npm install -g serverless
```

#### Installing AWS CLI

Lastly, we need to install the AWS CLI

``` bash
brew install awscli
```

#### Setting AWS Credentials

Now that we have installed Python, Pip, Node and the Serverless Framework. We need to setup our AWS Access and Secret keys to be used by the Serverless Framework.

##### Creating AWS Credentials

For the purposes of this workshop we will be creating a programmatic access user with Admin access. 

_*NOTE*: You should not share the keys you are creating with anyone. Furthermore, once this workshop concludes you should consider disabling your admin access user._

To create a programmatic user we will need to navigate to the [IAM Management Console](https://console.aws.amazon.com/iam/home?#/users$new?step=details).


Create a user, making sure to grant programmatic access. This will generate an access and secret key that the Serverless Framework will need to create resources for us

![Add User](assets/images/add-user.png)

Next we will want to give our new user Admin rights. In production we would only grant the rights we need for an application but since this is a quick demo application lets select `AdministratorAccess`.
![Admin Rights](assets/images/admin-rights.png)

After creating the user make sure to download the user credentials as a csv. 


_*NOTE*: This is the only time you will be able to download the credentials. If you do not do this now you will need to create a completely new user._

![User Creds](assets/images/user-creds.png)

Our last step is to add our new Access and Secret key to our list of AWS Credentials. To check our current credentials, run the following command.

```bash
cat ~/.aws/credentials
```

We will want to update the default profile in our credentials file with our new access and secret keys

```
[default]
aws_access_key_id = your_access_key_here
aws_secret_access_key = your_secret_key_here
```

### Windows


## Presentation

Slides for the presentation are available [here](https://github.com/shiftgig/aws-serverless-workshop/blob/master/presentation-slides.pdf) 
in the master branch of this repository.

Note that the [`master`](https://github.com/shiftgig/aws-serverless-workshop/tree/master) branch of this repository
corresponds to the content in the presentation up to "Step 5" (end of slide 38).

If you'd like to see the fully-complete example, take a look at the [`final`](https://github.com/shiftgig/aws-serverless-workshop/tree/final)
branch. Additional functionality found on this branch includes:
* DynamoDB integration
* Support for GET and DELETE requests (in addition to PUT)
* Advanced API Gateway usage: protecting endpoints with a client API key and usage plan


## Contact

You can get in touch with me via email: [tyler@shiftgig.com](mailto:tyler@shiftgig.com)


## Useful Links

* Serverless Framework
    * [Github repository](https://github.com/serverless/serverless)
    * [Website](https://serverless.com/)
* `serverless-python-requirements` plugin
    * [Github repository](https://github.com/UnitedIncome/serverless-python-requirements)
* Shiftgig
    * [Website](https://shiftgig.com)
    * [Github](https://github.com/shiftgig)
* Pipenv: Python Dev Workflow for Humans
    * [Website](https://docs.pipenv.org/)
    * [Github repository](https://github.com/pypa/pipenv)
