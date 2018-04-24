###本地安装awscli
```
brew install awscli
```

###本地安装ansible
```
brew install ansible
```

###配置环境变量
```
vi ~/.bash_profile
export AWS_ACCESS_KEY_ID=xxxxxxxxxxx
export AWS_SECRET_ACCESS_KEY=xxxxxxxxxxxxxxx
export AWS_REGION=cn-north-1
```

###创建VPC
```
$ ansible-playbook -i contrib/ec2.py ansible_vpc.yml -e 'acname=launch' --tags launch
$ ansible-playbook -i contrib/ec2.py ansible_vpc.yml -e 'acname=terminate' --tags terminate
```

###创建ec2实例
使用方法
```
$ ansible-playbook -i contrib/ec2.py ansible_ec2.yml -e 'acname=keypair' --tags keypair
$ ansible-playbook -i contrib/ec2.py ansible_ec2.yml -e 'acname=launch' --tags launch
$ ansible-playbook -i contrib/ec2.py ansible_ec2.yml -e 'acname=optimize' --tags optimize
$ ansible-playbook -i contrib/ec2.py ansible_ec2.yml -e 'acname=terminate' --tags terminate
$ ansible-playbook -i contrib/ec2.py ansible_ec2.yml -e 'acname=ssh' --tags ssh
```



https://stackoverflow.com/questions/33795607/how-to-define-ssh-private-key-for-servers-fetched-by-dynamic-inventory-in-files

https://www.kubernetes.org.cn/3536.html

