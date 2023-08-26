https://www.freecodecamp.org/news/manage-multiple-github-accounts-the-ssh-way-2dadc30ccaca
https://pawelgrzybek.com/multiple-ssh-keys-for-multiple-bitbucket-github-accounts/


rm ~/.ssh/id_ed25519_sw  ~/.ssh/id_ed25519_sw.pub ~/.ssh/id_ed25519_ldfm ~/.ssh/id_ed25519_ldfm.pub 
~/.ssh/known_hosts ~/.ssh/config ~/.ssh/known_hosts.old 

cd ~/.ssh && ssh-keygen -t ed25519 -C "daniil.frei@skywindgroup.com" -N '' -f "id_ed25519_sw" &&
cd ~/.ssh && ssh-keygen  -t ed25519 -C "ldfm0401@gmail.com" -N '' -f "id_ed25519_ldfm"  &&
eval "$(ssh-agent -s)" &&
ssh-add -D &&
ssh-add ~/.ssh/id_ed25519_sw &&
ssh-add ~/.ssh/id_ed25519_ldfm &&
ssh-add -l


pbcopy < ~/.ssh/id_ed25519_sw.pub
pbcopy < ~/.ssh/id_ed25519_ldfm.pub
 
nano ~/.ssh/config
—————————————————————————————————————————————————————————
Host github.com
   HostName github.com
   User ldfm0401@gmail.com
   IdentityFile ~/.ssh/id_ed25519_ldfm

Host bitbucket.skywindgroup.com
   HostName bitbucket.skywindgroup.com
   User daniil.frei@skywindgroup.com
   IdentityFile ~/.ssh/id_ed25519_sw
—————————————————————————————————————————————————————————
git clone ssh://git@bitbucket.skywindgroup.com:7999/wls/swl-multi-services.git
git clone git@github.com:FreyDv/bot.git
—————————————————————————————————————————————————————————
ssh -v  -T git@bitbucket.org #debug
git remote -v 

