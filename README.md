# Template Role Ansible

Esse projeto tem a finalidade de ser um template para futuras criações de projetos que usem [ansible](https://docs.ansible.com/) e [molecule](https://molecule.readthedocs.io/en/latest/) (para teste do playbook).

## Dependências
Para realizar os teste localmente é necessário a instalação das seguintes dependências:

* [Python](https://www.python.org/downloads/)
* [Molecule](https://molecule.readthedocs.io/en/latest/installation.html)

## Preparando o ambiente

Crie um ambiente python

    $ python3 -m venv .venv

Ative o ambiente

    $ source .venv/bin/active

Instale dentro do ambiente o molecule (e suas dependencias) e o [pytest-testinfra](https://testinfra.readthedocs.io/en/latest/)

    (venv)$ python3 -m pip install "molecule[docker,lint]" pytest-testinfra

## Criando a role

A role precisa ser criada e você pode fazer com o comando abaixo:

```
molecule init role nome_da_role --driver-name docker
```

## Executando

    (venv)$ molecule test

Para realizar teste rápido após alguma modificação

    (venv)$ molecule create
    (venv)$ molecule converge
    (venv)$ molecule verify

Ao termino do teste, destrua o ambiente

    (venv)$ molecule destroy
