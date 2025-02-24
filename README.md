# setup-my-machine

## mac

1. install XCode and [HomeBrew](https://brew.sh/)
2. `brew install ansible`
3. `ansible-galaxy install -r requirements.yml`
4. `ansible-playbook mac.yml`

## wsl
1. setup wsl by ubuntu
2. `sudo apt install ansible`
3. `ansible-galaxy install -r requirements.yml`
4. `ansible-playbook wsl.yml --ask-become-pass`
