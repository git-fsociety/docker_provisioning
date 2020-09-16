Descrição:
---------------

  Atrávez do arquivo Vagrantfile é possível provisionar (N) VMs com docker engine usando a integração com ansible.

Requerimento:
---------------

  Instalação Virtualbox >= 5.2
  Instalação ansible    >= 2.9
  Instalação python     >= 3.6


Variaveis
--------------

  compose_arch: Recebe a arquitetura do sistema operacional x86_64
  gpg_oficial_key: Recebe a chave GPG oficial do docker
  compose_version: Recebe versão declarada para o docker compose
  compose_path: Define o path padrão de instalação do docker compose
  username: Define uma lista de usuários
  user_password: Define senha padrão para o usuario. Essa senha e encryptada pelo script {{ my_password_ansible.py }} deve ser executado separadamente
e incluído nesse campo.

Exemplo de execução:
  ./my_password_ansible.py 123456

  OUT > $6$/Z8SkCAw.TR8xZnm$B9uGvVrm19TTphdR/SU0S1SEObx08u4zfU8cqjpKTdqlfZTWa48S4mlnd.FZXYkwTWGYfrRN.uDpVLmgzK62Y1




Playbook
----------------
 No arquivo Vegrantfile no campo que corresponde a network configurar um range de IP da rede local.
 Para execução do playbook ajuste a senha da variável {{ user_password }} para o valor que corresponde sua senha encryptada pelo {{ my_password_ansible.py }}, no arquivo de hosts (inventario) pode ser definido um ou mais IPs. ajuste conforme necessidade.

Exemplo arquivo hosts:

 [node]
  xxx.xxx.xxx.xxx ansible_user=vagrant ansible_ssh_private_key_file=".vagrant/machines/node2/virtualbox/private_key" ansible_python_interpreter=/usr/bin/python3
  xxx.xxx.xxx.xxx ansible_user=vagrant ansible_ssh_private_key_file=".vagrant/machines/node3/virtualbox/private_key" ansible_python_interpreter=/usr/bin/python3
  xxx.xxx.xxx.xxx ansible_user=vagrant ansible_ssh_private_key_file=".vagrant/machines/node4/virtualbox/private_key" ansible_python_interpreter=/usr/bin/python3

 [teste]
  xxx.xxx.xxx.xxx ansible_user=vagrant ansible_ssh_private_key_file=".vagrant/machines/node1/virtualbox/private_key" ansible_python_interpreter=/usr/bin/python3


License
-------

BSD

Author Information
------------------

Author: Flávio Ferreira
E-mail: flavio1605@gmail.com
Twitter:
Github:
Linkdin:
