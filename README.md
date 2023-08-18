# ansible-all-commands

MAIN SERVER (ANSIBLE)

amazon-linux-extras install ansible2 -y
yum install python python-pip python-level openssl -y
vim /etc/ansible/hosts (line 13 edit)
vim /etc/ansible/ansible.cfg (line 14 & 22 edit)

ALL SERVERS:

useradd ansible
passwd ansible
visudo
vim /etc/ssh/sshd_config
systemctl restart sshd
systemctl status sshd
su - ansible
hostname -i
sudo hostnamectl set-hostname (set as per node name)

MAIN SERVER (ANSIBLE)
ssh-keygen
ssh-copy-id ansible@private-ip pf node

ctrl + d


============================================================================

1  hostname -i
    2  ssh-keygen
    3  ssh-copy-id ansible@172.31.14.202
    4  sudo hostnamectl set-hostname mainserver
    5  ssh 'ansible@172.31.14.202'
    6  ssh-copy-id ansible@172.31.5.56
    7* ssh 'ansible@172.31.5.56
    8  ssh-copy-id ansible@172.31.4.163
    9  ssh 'ansible@172.31.4.163'
   10  ssh-copy-id ansible@172.31.11.160
   11  ssh 'ansible@172.31.11.160'
   12  ansible all --list-hosts
   13  ansible dev --list-hosts
   14  ansible test --list-hosts
   15  ansible all --list-hosts
   16  ansible all[0] --list-hosts
   17  ansible all[1] --list-hosts
   18  ansible all[2] --list-hosts
   19  ansible all[-1] --list-hosts
   20  ansible all[-2] --list-hosts
   21  ansible all --list-hosts
   22  ansible all[1:3] --list-hosts
   23  cat /etc/ansible/hosts
   24  ansible all -a "ls"
   25  ansible all -a "touch file1"
   26  ansible all -a "ls"
   27  ansible all -a "mkdir dir1"
   28  ansible all -a "ls"
   29  ansible all -a "useradd devops"
   30  ansible all -a "sudo useradd devops"
   31  ansible all -a "cat /etc/passwd"
   32  ansible all -b -a "yum install git -y"
   33  ansible all -b -a "git --version"
   34  ansible all -b -a "yum remove git -y"
   35  ansible all -b -m yum -a "pkg=git state=present"
   36  ansible all -b -a "git --version"
   37  ansible all -b -m yum -a "pkg=httpd state=present"
   38  ansible all -b -m yum -a "pkg=httpd state=absent"
   39  ansible all -b -m yum -a "pkg=httpd state=present"
   40  ansible all -b -m yum -a "pkg=httpd state=latest"
   41  ansible all -b -m yum -a "pkg=httpd state=started"
   42  ansible all -b -m yum -a "name=httpd state=started"
   43  ansible all -b -m service -a "name=httpd state=started"
   44  ll
   45  ansible all -b -m user -a "name=siraj"
   46  vim raham.txt
   47  cat raham.txt
   48  ansible all -b -m copy -a "src=raham.txt dest=/tmp"
   49  ansible all -a "ls"
   50  ansible all -a "ls /tmp"
   51  history

 1  hostname -i
    2  ssh-keygen
    3  ssh-copy-id ansible@172.31.14.202
    4  sudo hostnamectl set-hostname mainserver
    5  ssh 'ansible@172.31.14.202'
    6  ssh-copy-id ansible@172.31.5.56
    7  ssh 'ansible@172.31.5.56
    8  ssh-copy-id ansible@172.31.4.163
    9  ssh 'ansible@172.31.4.163'
   10  ssh-copy-id ansible@172.31.11.160
   11  ssh 'ansible@172.31.11.160'
   12  ansible all --list-hosts
   13  ansible dev --list-hosts
   14  ansible test --list-hosts
   15  ansible all --list-hosts
   16  ansible all[0] --list-hosts
   17  ansible all[1] --list-hosts
   18  ansible all[2] --list-hosts
   19  ansible all[-1] --list-hosts
   20  ansible all[-2] --list-hosts
   21  ansible all --list-hosts
   22  ansible all[1:3] --list-hosts
   23  cat /etc/ansible/hosts
   24  ansible all -a "ls"
   25  ansible all -a "touch file1"
   26  ansible all -a "ls"
   27  ansible all -a "mkdir dir1"
   28  ansible all -a "ls"
   29  ansible all -a "useradd devops"
   30  ansible all -a "sudo useradd devops"
   31  ansible all -a "cat /etc/passwd"
   32  ansible all -b -a "yum install git -y"
   33  ansible all -b -a "git --version"
   34  ansible all -b -a "yum remove git -y"
   35  ansible all -b -m yum -a "pkg=git state=present"
   36  ansible all -b -a "git --version"
   37  ansible all -b -m yum -a "pkg=httpd state=present"
   38  ansible all -b -m yum -a "pkg=httpd state=absent"
   39  ansible all -b -m yum -a "pkg=httpd state=present"
   40  ansible all -b -m yum -a "pkg=httpd state=latest"
   41  ansible all -b -m yum -a "pkg=httpd state=started"
   42  ansible all -b -m yum -a "name=httpd state=started"
   43  ansible all -b -m service -a "name=httpd state=started"
   44  ll
   45  ansible all -b -m user -a "name=siraj"
   46  vim raham.txt
   47  cat raham.txt
   48  ansible all -b -m copy -a "src=raham.txt dest=/tmp"
   49  ansible all -a "ls"
   50  ansible all -a "ls /tmp"
   51  history
   52  ll
   53  rm -rf *
   54  vim raham.yml
   55  cat raham.yml
   56  ansible all -ba "yum remove git -y"
   57  ll
   58  ansible-playbook raham.yml
   59  cat raham.yml
   60  vim raham.yml
   61  cat raham.yml
   62  ansible-playbook raham.yml --extra-vars "a=docker"
   63  ansible-playbook raham.yml --extra-vars "a=maven"
   64  cat raham.yml
   65  vim raham.yml
   66  ansible all -ba "yum remove docker git -y"
   67  cat raham.yml
   68  ansible-playbook raham.yml "a=git, b=docker"
   69  ansible-playbook raham.yml "a=git b=docker"
   70  ansible-playbook raham.yml --extra-vars "a=git b=docker"
   71  ansible all -ba "yum remove docker git -y"
   72  vim raham.yml
   73  ansible-playbook raham.yml --extra-vars "a=git b=docker"
   74  vim raham.yml
   75  ansible all -ba "yum remove docker git -y"
   76  vim raham.yml
   77  cat raham.yml
   78  ansible-playbook raham.yml
   79  cat raham.yml
   80  vim raham.yml
   81  ansible all -ba "yum remove docker git tree maven -y"
   82  cat raham.yml
   83  ansible-playbook raham.yml
   84  ansible all -ba "git --version"
   85  ansible all -ba "maven -version"
   86  ansible all -ba "docker -version"
   87  ansible all -ba "docker --version"
   88  ansible all -ba "java -version"
   89  cat raham.yml
   90  ansible all -ba "tree --version"
   91  vim raham.yml
   92  ansible all -ba "cat /etc/passwd"
   93  ansible-playbook raham.yml
   94  ansible all -ba "cat /etc/passwd"
   95  vim raham.yml
   96  ansible all -ba "yum remove git maven tree docker java-1.8.0-openjdk httpd -y"
   97  ansible-playbook raham.yml
   98  ansible all -ba "systemctl status httpd"
   99  cat raham.yml
  100  cat /etc/ansible/hosts
  101  cat raham.yml
  102  vim raham.yml
  103  ansible-playbook raham.yml
  104  ll
  105  vim raham.yml
  106  rm -rf *
  107  mkdir playbooks
  108  cd playbooks/
  109  mkdir roles
  110  touch master.yml
  111  vim master.yml
  112  tree
  113  sudo yum install tree -y
  114  tre
  115  tree
  116  mkdir roles/role1/
  117  mkdir roles/role1/tasks
  118  tree
  119  vim roles/role1/tasks/main.yml
  120  tree
  121  vim master.yml
  122  cat master.yml
  123  ansible-playbook master.yml
  124  tree
  125  mkdir roles/role2/
  126  mkdir roles/role2/tasks
  127  vim roles/role2/tasks/main.yml
  128  tree
  129  vim master.yml
  130  ansible-playbook master.yml
  131  cat roles/
  132  cat master.yml
  133  tree
  134  cd
  135  ll
  136  rm -rf *
  137  vim raham.yml
  138  ansible-playbook raham.yml
  139  cat raham.yml
  140  ansible all -ba "yum remove httpd docker git -y"
  141  ll
  142  vim abc.yml
  143  cat abc.yml
  144  vim abc.yml
  145  cat abc.yml
  146  ansible-playbook abc.yml --tags a,b
  147  cat abc.yml
  148  ansible-playbook abc.yml --tags d
  149  ansible -m setup 3.231.151.78
  150  ansible -m setup 172.31.14.202
  151  ansible all -ba "yum remove docker java-1.8.0-openjdk git -y"
  152  ll
  153  cat raham.yml
  154  cat abc.yml
  155  ansible-playbook abc.yml --skip-tags "c"
  156  cat raham.yml
  157  cat abc.yml
  158  vim abc.yml
  159  cat abc.yml
  160  vim abc.yml
  161  ll
  162  cat abc.yml
  163  ansible-vault create creds
  164  cat creds
  165  ansible-vault edit creds
  166  cat creds
  167  ansible-vault rekey creds
  168  cat creds
  169  ansible-vault decrypt creds
  170  cat creds
  171  ansible-vault encrypt creds
  172  cat creds
  173  ansible-vault view creds
  174  cat creds
  175  ll
  176  cat raham.yml
  177  ansible-vault encrypt raham.yml
  178  ll
  179  cat raham.yml
  180  ansible-playbook raham.yml
  181  ansible-playbook decrypt raham.yml
  182  ansible-vault decrypt raham.yml
  183  ps
  184  kill -9 4665
  185  kill -9 4665ps
  186  ps
  187  cd /home/
  188  ll
  189  sudo useradd raham
  190  ll
  191  cd
  192  ll
  193  rm -rf *
  194  ll
  195  ansible-galaxy init raham
  196  ll
  197  tree
  198  cat raham/handlers/main.yml
  199  rm -rf *
  200  ansible-galaxy search java
  201  ansible-galaxy search elasticsearch
  202  ansible-galaxy init alikins.elasticsearch
  203  ll
  204  tree
  205  mazer install alikins.top_geerlingguy
  206  ansible-galaxy collection install alikins.collection_inspect
  207  history
