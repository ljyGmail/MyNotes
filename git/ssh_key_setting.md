# Setting SSH key for a new computer
```
ssh-keygen -t ed25519 -C "{email}"
```
Press enter for serveral times.

* Ensure the ssh-agent is running:
```
eval "$(ssh-agent -s)"
```
* Add the SSH private key to the ssh-agent:
```
ssh-add ~/.ssh/id_ed25519
```

* Copy the contents in `~/.ssh/id_ed25519.pub` in `SSH and GPG kyes` menu in Github.
