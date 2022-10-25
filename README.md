# SCRIPT YAML PARA USO NO CLOUDFORMARTION
## vpc.yaml

O script vpc.yaml tem como objetivo criar uma VPC na região em que estiver.

São criadas duas subnets nas duas primeiras zonas de disponibilidade da região.
Por exemplo, caso esteja na região de São Paulo (sa-east-1), as subnets serão criadas nas zonas de disponibilidade sa-east-1a e sa-east-1b.

 - Mapa da rede criada:
    - Bloco de endereço da VPC: 10.0.0.0/16
    - Subnet Publica 1: 10.0.1.0/24
    - Subnet Publica 2: 10.0.2.0/24
    - Subnet Privada 1: 10.0.11.0/24
    - Subnet Privada 2: 10.0.12.0/24

Além da VPC e das subnets criadas, é criado também um Internet Gateway e feita duas tabelas de roteamento, uma para a rede privada e outra para a rede pública.
Na tabela de roteamento pública é criada uma rota para o Internet Gateway.

Por questões de custo e devido o script ser apenas para laboratório inicial, não foi criado o NAT Gateway para associar na tabela de roteamento privada.


## ec2.yaml

O script ec2.yaml cria um instância do tipo t2.micro com a imagem do Ubuntu Server 20.04 LTS. No script possui alguns comentários referente a instruções.

É criado um grupo de segurança liberando as portas HTTP (80) e SSH (22).

Também é feita a criação de um segundo volume, um disco com tamanho de 10 GiB.