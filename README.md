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

    (venv)$ pip install "molecule[docker,lint]" pytest-testinfra

## Executando

    (venv)$ molecule test

Para realizar teste rápido após alguma modificação

    molecule create
    molecule converge
    molecule verify

Ao termino do teste, destrua o ambiente

    molecule destroy
