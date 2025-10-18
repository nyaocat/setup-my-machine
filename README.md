# setup-my-machine

## mac

1. install XCode and [HomeBrew](https://brew.sh/)
2. `brew install ansible`
3. `ansible-galaxy install -r requirements.yml`
4. `ansible-playbook mac.yml`

## ubuntu
1. Enables sudo commands to be executed without entering a password
2. `sudo apt install ansible`
3. `ansible-galaxy install -r requirements.yml`
4. `ansible-playbook ubuntu.yml --ask-become-pass`
