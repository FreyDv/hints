# GIT

### Command to install and chack defaulkt GitUser

#### SET global default gitUser name
```bash
git config --global user.name "FreyDv"
```
#### SET global default gitUser email
```bash
git config --global user.email "ldfm0401@gmail.com"
```
--- 
#### Show list of config 
```bash
git config --list
```
---
#### Show current name 
```bash
git config --show-origin user.name
git config --list | grep user.name
```
#### Show local and global email
```bash
git config --show-origin user.email
git config --list | grep user.email
```
---
#### Bulk setup 
```bash
git config user.name "Daniil Frei" &&
git config user.email "daniil.frei@wow365.com"

git config --global user.name "FreyDv" && 
git config --global user.email "ldfm0401@gmail.com";

git config --list;

git config --list | grep user.name;
git config --list | grep user.email;
```
