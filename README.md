## Guide to setting up SSH keys!

1. Open Git bash and use `cd` to take you to the root directory

![1.png](1.png)

2. then `mkdir .ssh` to make new ssh hidden directory (you can see it with `ls -a`), then change to that directory with `cd .ssh`

![2.png](2.png)

3. Key pairs are created through the `ssh-keygen` command! We will use `ssh-keygen -t rsa -b 4096 -C "<email>"`, and will need to name the file, as well as give a password.

4. Return back to the local directory for your repo, and use `eval ssh-agent` with ssh-agent surrounded by backticks (cant show this in .md file)... Repeat whenever Pycharm is opened.

### !WARNING! **WHATEVER YOU DO, MAKE SURE THAT YOU ARE NOT STILL IN THE SSH FOLDER!** !WARNING!
### !WARNING! **THIS WILL CAUSE YOU TO PUSH ALL YOUR KEYS TO GITHUB! DO NOT DO THIS!** !WARNING!
### !WARNING! **WHATEVER YOU DO, MAKE SURE THAT YOU ARE NOT STILL IN THE SSH FOLDER!** !WARNING!
### !WARNING! **THIS WILL CAUSE YOU TO PUSH ALL YOUR KEYS TO GITHUB! DO NOT DO THIS!** !WARNING!

![4.png](4.png)

5. `ssh-add ~/.ssh/<ssh_folder_filename>` to add the private key identities you have saved in your .ssh folder to the Git authentication agent so I dont need to type in my key each time I access my repo.

![5.png](5.png)

6. The public key needs to be then provided to Github, so we can connect. This is available in the .pub file in your .ssh folder. We then need to navigate to `https://github.com/settings/ssh/new` and input the public key, along with a name.

![6.png](6.png)

![7.png](7.png)

7. Then type `ssh -T git@github.com` to connect to your Github using SSH!

![8.png](8.png)

8. Finally, initialise the repo with `git init`, create new repo on Github and use `git remote add origin git@github.com:<sshurl>` then `git remote set-url origin git@github.com:<sshurl>` to set as origin, where the sshurl is the key in the picture below.

![9.png](9.png)

9. Then stage, commit and push as usual!

## Guide to setting up SSH after closing pycharm

1. Go to the desired folder and type `eval ssh-agent` with ssh-agent surrounded by backticks (cant show this in .md file)
2. `ssh-add ~/.ssh/<ssh_folder_filename>` to add the private key identities so I can access the repo

## Guide to cloning an SSH repository 

1. Do the same thing as when you set up SSH after closing pycharm
2. Then, clone the repo with `git clone git@github.com:<sshurl>`
