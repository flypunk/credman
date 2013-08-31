# A little utility to manage the credentials for multiple  AWS accounts.

If you are regularly working from command line with multiple AWS accounts,
managing the credentials quickly becomes a burden.  
This script is an alternative to manual copying of config files or environment
variables manipulation.

It currently supports [aws cli](https://github.com/aws/aws-cli),
[boto](https://github.com/boto/boto) and [s3cmd](http://s3tools.org/s3cmd).  
Suggestions for more utilities or libraries are welcome!  

## Setup:
* Copy the script to some place in your $PATH and make it executable
* Create a directory that will hold your profiles, its default name is ~/aws_profiles.  
* Create under it subdirectories, each named after your desired profile name.  
* Copy or create config files for each utility into its profile directory:
  * .s3cfg for s3cmd
  * .boto for boto
  * .awscli for aws cli

## Example setup, assuming all the config files are in default locations:
```
sudo wget https://raw.github.com/flypunk/credman/master/credman -O /usr/local/bin/credman
sudo chmod +x /usr/local/bin/credman

cd ~
mkdir aws_profiles
mkdir aws_profiles/dev
mkdir aws_profiles/production
cp .s3cfg aws_profiles/dev
cp .boto aws_profiles/dev
cp .aws/config aws_profiles/dev/.awscli
# Now copy the files to the production directory as well and change the keys and regions accordingly
```

## Usage:
* List the existing profiles:  
`credman ls`
* Show the currently active profile:  
`credman current`
* Switch profile:  
`credman switch profile_name`

Feedback and pull requests are welcome! 
