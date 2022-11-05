# Using Ansible to automate software installation on my Mac

Here are the steps to automate the installation of apps on MacOS using Ansible and Brew

## Install Ansible

*Option 1 (pip)*

Install pip
```shell
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py  
python ./get-pip.py
```

Now install Ansible using pip
```shell
sudo python -m pip install --user ansible
```

*Option 2 (brew)*
If you've already installed Ansible with pip no need to do this
```shell
brew install ansible
```

## Configuring Ansible

Clone the repo
```shell
git clone git@github.com:albybott/ansible-automated-app-install.git
cd ansible-automated-app-install
```

Update the inventory file, setting `your-host-name` to the hostname of the local mac.
```
nano inventory
```

```shell
cat << EOF >> inventory  
[localhost\]  
your-host-name  
EOF
```

## Run the Playbook

```shell
ansible-playbook -i inventory playbook.yml
```

---
Links
- https://gist.githubusercontent.com/mrlesmithjr/f3c15fdd53020a71f55c2032b8be2eda/raw/be44272ce751e7bba41b6c7c5058a463a8f88463/ansible-macos-homebrew-packages.yml
- https://opensource.com/article/22/6/install-software-macos-ansible-homebrew


