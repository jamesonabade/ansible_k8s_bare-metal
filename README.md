<h1 align="center">
    Repositório Ansible-Kubernetes
</h1>

<p align="center">
    Automatiza a provisionamento de um novo cluster Kubernetes multi-nó em bare-metal com Ansible.
    Utiliza todas as ferramentas padrão para um cluster de nível empresarial.
</p>

## Índice

- **[Ferramentas](#ferramentas)**
- **[Requisitos](#requisitos)**
- **[Uso](#uso)**

## Ferramentas

- **Ansible**: uma engine de automação de TI de código aberto.
- **ContainerD**: run time de execução de contêineres.
- **Kubernetes**: um sistema de código aberto para automação de implantação, dimensionamento e gerenciamento de aplicações em contêineres.
- **Calico**: uma solução de código aberto para rede e segurança de rede para contêineres.
- **MetalLB**: um balanceador de carga em bare-metal para Kubernetes.
- **Nginx**: um controlador de Ingress.
- **Cert-Manager**: adiciona e emite certificados como tipos de recursos no cluster Kubernetes.

## Requisitos

1. Uma máquina Linux com privilégios de superusuário e Ansible pré-instalado.
2. Máquinas Ubuntu que serão os nós e control-plane.
Certifique-se de que sua chave SSH já está instalada nas máquinas executando o seguinte comando:
```
ssh-copy-id <usuario>@<ip da maquina remota>
```

## Uso

1. Clone este repositório Git para sua estação de trabalho local:
```
git clone https://github.com/JamesonAbade/ansible_k8s_bare-metal.git
```

2. Mude o diretório para o diretório raiz do projeto:
```
cd ansible_k8s_bare-metal
```

3. Edite os valores das variáveis padrão de acordo com suas necessidades:
```
nano defaults/main.yaml
```

4. Edite o arquivo de inventário do Ansible de acordo com suas necessidades:
```
nano inventory/hosts.ini
```

5. Execute o Playbook do Ansible:
```
ansible-playbook -i inventory/hosts.ini -K playbooks/cluster.yaml
```