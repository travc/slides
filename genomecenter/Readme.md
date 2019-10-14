# Notes for using genomecenter computing #

## Their website: requests forms and some info
https://computing.genomecenter.ucdavis.edu/home/


## Login node: `popi.genomecenter.ucdavis.edu`
*Note: This will get renamed `grassi.genomecenter.ucdavis.edu`.*  
I suggest using making a local /etc/hosts entry on your machine and calling it `grassi`.  
This is our node to use as we see fit.  

Another login node is `barbera.genomecenter.ucdavis.edu`, but that is shared with other groups.
Could be useful for testing if you can't get to our node.


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
