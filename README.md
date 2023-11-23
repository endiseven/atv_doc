# atv_doc
Documentação da primeira atividade de Linux - PB - Compass UOL 

## AWS

### Criar VPC
- Em configurações da VPC:
  - Selecionar "VPC e muito mais"
    - Dessa forma internet gateway e tabelas de rotas são configurados automaticamente para os fins da atividade.
  - Definir como "2" o número de sub-redes públicas e privadas.

### Criar e Configurar Security group
- Adicionar regras de entrada:
  - 22/TCP, 111/TCP e UDP, 2049/TCP/UDP, 80/TCP, 443/TCP
  - Item:"Origem" deve estar "0.0.0.0/0" para acesso público. 
    
### Gerar Pares de Chaves para acesso por SSH
- Em serviço EC2, na aba "Rede e segurança", acessar "Pares de chaves":
  - "Criar par de chaves" com as seguinte configuração para acesso por SSH:
    - Tipo de par de chaves: RSA
    - Formato de arquivo de chave privada: .pem
  - Armazenar a chave privada gerada para acesso ao ambiente. 

### Instância EC2
- Criar Instância com as Tags necessárias para obter permissão. 
- Configurar a instância da seguinte forma:
  - Imagem de máquina da Amazon: Amazon Linux 2
  - Tipo de instância: t3.small
  - Par de chaves: selecionar um par de chaves.
  - Configurações de rede:
    - Rede: VPC configurada previamente
    - Sub-rede: Subnet pública
  - Firewall (grupos de segurança):
    - Selecionar grupo de segurança existente.
    - Selecionar o security group configurado previamente.
    - Configurar armazenamento: 16 GiB

### IP Elástico
- Em serviço EC2, na aba "Rede e segurança", acessar "IPs elásticos":
- Alocar endereço IP elástico
  - Em "ações" escolher "associar ip elástico" e selecionar a instância desejada.


## Linux

### Acesso Inicial a instância por SSH
- Com a instância iniciada, com a chave privada em meu computador e usando o WSL (Windows subsystem for linux):
  - Configurar permissões para o uso da chave 

```
    sudo chmod 400 /*/chaveprivada.pem
```

- Utilizar o seguinte comando para acessar a instância:

```
    ssh -i chaveprivada.pem ec2-user@34.236.193.66
```

### Configurando o NFS

#### Servidor

#### Cliente

### Instalando e configurando o servidor Apache

### Script

### Execução automática do script

### Github

