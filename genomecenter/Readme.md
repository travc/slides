# Notes for using genomecenter computing #

## Their website: requests forms and some info
https://computing.genomecenter.ucdavis.edu/home/


## Login node: `popi.genomecenter.ucdavis.edu`
*Note: This will get renamed `grassi.genomecenter.ucdavis.edu`.*  
I suggest using making a local /etc/hosts entry on your machine and calling it `grassi`.  
This is our node to use as we see fit.  

Another login node is `barbera.genomecenter.ucdavis.edu`, but that is shared with other groups.
Could be useful for testing if you can't get to our node.

## Port forwarding (for Jupyter notebook and some other applications)

Connecting a local port on your machine with a port on grassi will let you 
run `jupyter notebook` on the genomecenter and view it in a local webbrowser.  

Log in with a command like:
```
ssh -tL <port>:localhost:<port> <username@host>
```
Replace `<port>` with a port number between 1024 and 65535. This will be the port number you need to use for jupyter notebook (described below). 
You can't use the same number as someone else.

I highly recommed making an alias for this.

Note: If you are using Mobaxterm, you can either start a local terminal and use the command, or you can change the setting for the connection/login to do the port forwarding. (I don't do it that way, so I can't tell you exactly how though.)

## Python ##
I have setup a shared python environment (using conda/anaconda3) for us.  
To activate it, use the command:
```
module load anaconda3 && source `which activate` /share/lanzarolab/opt/conda/vgl/
```
I suggest putting that command at the end of your `~/.bashrc` file so it is automatically done when you login.


You might also want to add an alias for that command in your `~/.bash_aliases` file:
```
alias vglconda='module load anaconda3 && source `which activate` /share/lanzarolab/opt/conda/vgl/'
```
Then just typing `vglconda` will start the environemnt.


Another thing you may want...
By default conda puts the full path to the environment in your prompt, that is long and annoying.
This command will change that to a short name (vgl for our shared conda env):
```
conda config --set env_prompt '({name})'
```
#### Just ask me (travc) if you need packages/modules installed. It is easy, but you don't have the permissions. ####


## Jupyter notebook

Assuming you've logged in with port forwarding and have Python loaded with our shared conda environment (the previous two sections of this doc)...

You can run juypter notebook with a command like:
```
jupyter notebook --no-browser --port <port> --port-retries=0
```
Replace `<port>` with the same port number you chose for ssh tunneling.




## Slurm ##
It works.  Using it properly can be tricky.  
**Please ask me if you have a task which might benefit from farming it out to the whole cluster.**

---

# General Stuff, not specifically genomecenter computing related #

## Github ##
Github (https://github.com) is a great way to keep and share programs, scripts, and even *small* data files.  

**I suggest a repository is made for every project/paper in progress.**  
This also makes it easy to publish supplememntal files and code, which most journals want now.

By default, github repositiories are public.
I have a paid account which allows for private repositiories.

Perhaps we the lab itself may want to get a paid account.  A "team" account is $9/mo.
