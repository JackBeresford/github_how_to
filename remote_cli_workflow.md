# Remote CLI Workflow (including SSH)

It is easy and time saving to make and push changes to a remote destination, without leaving the command line interface (CLI). 

Gitlab and Github are virtually identical after the SSH stage, so I am calling this 'remote' rather than github specific. 

## Make SSH

- Make ssh key (e.g. with ssh-keygen)
- Copy public key (contents of ~/.ssh/\*.pub)

## Github Settings

- Settings -> SSH + GPG Keys -> New SSH Key -> Authentication Key
- Paste in public key, save

## Gitlab Settings

- User Settings -> Access -> SSH keys
- Paste in public key, save

## Create new repo (Github/Gitlab)

- select SSH instead of HTML for authentication
- copy URL

## CLI - setup

```
mkdir <project_name>
cd <project_name>
cat >> README.md
> # project_name
> \n
> <description>
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin <url>
git push -u origin main
```

## CLI - ongoing

```
git add . # or file/s
git commit -m <message>
git push origin main
```
