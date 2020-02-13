# Zabbix Ansible dev
Automatização da instalação do zabbix agent, utilizando Ansible.

## Estrutura do repositório:

```
├── main.yml                                >> Chama as tarefas
├── README.md
└── roles                                   >> Estrutura do Ansible
    ├── files                               >> Arquivos/Pacotes
    │   ├── zabbix_agentd.conf
    │   └── zabbix-api-0.5.3.tar.gz
    └── tasks                               >> Tarefas
        ├── agent-zabbix.yml
        └── main.yml                        >> Chama as tarefas
```

## Modificando arquivos

Dois arquivos precisam ser alterados:

**1. zabbix_agentd.conf**

**2. agent-zabbix.yml**

## Executando playbook

Para executar o playbook iremos chamar o arquivo main (arquivo que chama as tasks), através dos comandos mostrados abaixo.
**!: É necessário adicionar --extra-vars ao final da chamada, onde será colocado o grupo ou nome do host que foi definido no arquivo de hosts do Ansible.**

```
$ cd ansible-zabbix-agent

$ ansible-playbook main.yml --extra-vars "hosts=[grupodehosts]"
```

Após executar o playbook, basta checar se no frontend do Zabbix o host foi inserido. 
