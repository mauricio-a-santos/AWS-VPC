# Documentação: Criando uma cloud VPC com sub-redes pública e privada, gateway de internet e gateway NAT

Este repositório contém **prints** e um passo-a-passo para criar uma VPC preparada para receber instâncias do EC2 em redes pública e privada. Atividade prática de laboratório para preparação da certificação AWS Cloud Practitioner através do programa **AWS re/Start da Escola da Nuvem**.

---

## Estrutura do Repositorio


├── imagens-do-console-aws/

└──README.md

---

🧠 Habilidades adquiridas: 
- Criar e uma VPC no AWS Console
- Configurar a VPN para habilitar nomes DNS
- Criar de uma sub-rede pública e outra privada
- Configurar a sub-rede pública para atribuir IP público automaticamente
- Criar um gateway de internet e associar à VPC criada
- Criar um gatway NAT
- Criar uma tabela de rotas privada da VPC criada
- Criar uma tabela de rotas pública e configurar o tráfego vinculado à internet (0.0.0.0/0) para o gateway de internet 
- Associar a tabela de rotas pública à sub-rede pública criada 

---


🛠️ Tecnologias Utilizadas

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="80"/>


## Sumário
1. Criar uma VPC habilitando nomes DNS
2. Criar e configurar sub-redes pública e privada
3. Criar um gateway de internet
4. Criar e configurar tabelas de rotas
5. Acessar o endpoint do site

---

## Passo a passo (resumo)

### 1) Criar uma VPC habilitando nomes DNS
- Abra o Console AWS > VPC > Criar VPC

![Acessando o console](Imagens%20do%20console%20AWS/01-acessar-servico-vpc.jpg)

![Iniciando a criacao](Imagens%20do%20console%20AWS/02-iniciar-criacao-de-uma-vpc.jpg)

- Configurar nome e bloco CIDR IPv4. (Nome da VPC usado de exemplo `Lab VPC`)

![Configuracao da VPC](Imagens%20do%20console%20AWS/03-configuracoes-da-vpc.jpg)
![Criar VPC](Imagens%20do%20console%20AWS/04-criar-vpc.jpg)

![VPC criada](Imagens%20do%20console%20AWS/05-vpc-criada.jpg)

- Habilitar nomes DNS

![Acao VPC](Imagens%20do%20console%20AWS/06-editar-configuracoes-da-vpc.jpg)

![DNS](Imagens%20do%20console%20AWS/07-habilitar-nomes-de-hosts.jpg)

![DNS habilitado](Imagens%20do%20console%20AWS/08-nomes-de-hosts-habilitado.jpg)

### 2) Criar sub-redes
- Criar sub-rede pública

![acessar sub-redes](Imagens%20do%20console%20AWS/09-acessando-sub-rede.jpg)
![criar sub-redes](Imagens%20do%20console%20AWS/10-iniciar-criacao-de-sub-rede-publica.jpg)

- Configurar ID da VPC, nome e bloco CIDR IPv4 da sub-rede (OBS.: uma Zona de disponibilidade deve ser selecionada)

![configuracao da sub-rede](Imagens%20do%20console%20AWS/11-nome-da-sub-rede-publica.jpg)
![criar sub-rede](Imagens%20do%20console%20AWS/12-CIDR-e-criacao-da-sub-rede-publica.jpg)
![sub-rede criada](Imagens%20do%20console%20AWS/13-sub-rede-publica-criada.jpg)

- Configurar atribuição automática de IPs públicos na sub-rede pública

![Acao da sub-rede](Imagens%20do%20console%20AWS/14-editar-configuracoes-da-sub-rede.jpg)
![Ip publico](Imagens%20do%20console%20AWS/15-habilitar-ip-publico-automatico.jpg)

- Repita o mesmo processo de criação para a sub-rede privada (O CIDR IPv4 deve ser diferente da sub-rede pública)

![Acessar sub-redes](Imagens%20do%20console%20AWS/16-iniciar-criacao-de-sub-rede-privada.jpg)
![configuracao da sub-rede](Imagens%20do%20console%20AWS/17-nome-da-sub-rede-privada.jpg)
![criacao da sub-rede](Imagens%20do%20console%20AWS/18-CIDR-e-criacao-da-sub-rede-privada.jpg)
![Sub-rede criada](Imagens%20do%20console%20AWS/19-sub-rede-privada-criada.jpg)

### 3) Criar um gateway de internet
- Selecione **Gateways da Internet** para iniciar a criação

![Acessar gateways](Imagens%20do%20console%20AWS/20-acessando-servico-de-gateways-de-internet.jpg)
![iniciar criacao](Imagens%20do%20console%20AWS/21-iniciar-criacao-de-gateway-de-internet.jpg)

- Definir o nome do Gateway

![Nome do Gateway](Imagens%20do%20console%20AWS/22-nome-e-criacao-do-gateway-de-internet.jpg)
![Gateway criado](Imagens%20do%20console%20AWS/23-gateway-de-internet-criado.jpg)

- Associar o novo Gateway à VPC criada anteriormente

![Acao do Gateway](Imagens%20do%20console%20AWS/24-iniciar-associacao-do-gateway-de-internet-com-uma-vpc.jpg)
![Associar Gateway](Imagens%20do%20console%20AWS/25-associando-gateway-de-internet-com-uma-vpc.jpg)
![Gateway associado](Imagens%20do%20console%20AWS/26-gateway-de-internet-associado-com-a-vpc.jpg)

### 4) Criar e configurar tabelas de rotas
- Tabela de rotas privada

![Acessar tabelas de rotas](Imagens%20do%20console%20AWS/27-acessando-servico-de-tabelas-de-rotas.jpg)
![Iniciar criacao](Imagens%20do%20console%20AWS/28-iniciar-criacao-de-tabela-de-rotas-privada.jpg)

- Configure um nome e selecione a VPC criada anteriormente

![Criar tabela de rotas](Imagens%20do%20console%20AWS/29-nome-e-criacao-da-tabela-de-rotas-privada.jpg)
![Tabela de rotas criada](Imagens%20do%20console%20AWS/30-tabela-de-rotas-privada-criada.jpg)

- Repita o processo de criação para a Tabela de Rotas pública

![Iniciar criacao](Imagens%20do%20console%20AWS/31-iniciar-criacao-de-tabela-de-rotas-publica.jpg)
![Criar tabela de rotas](Imagens%20do%20console%20AWS/32-nome-e-criacao-da-tabela-de-rotas-publica.jpg)
![Tabela de rotas criada](Imagens%20do%20console%20AWS/33-tabela-de-rotas-publica-criada.jpg)

- Configurar a Tabela de Rotas Pública para direcionar o tráfego vinculado à internet (0.0.0.0/0) para o Gateway de Internet.

![Editar rotas](Imagens%20do%20console%20AWS/34-iniciar-edicao-da-tabela-de-rotas-publica.jpg)

- Direcione o destino (/0) para o Gateway de internet criado anteriormente

![Configuracao da rotas criada](Imagens%20do%20console%20AWS/35-configuracoes-da-tabela-de-rotas-publica.jpg)
![Tabela de rotas criada](Imagens%20do%20console%20AWS/36-tabela-de-rotas-publica-configurada.jpg)

- Associar a Tabela de Rotas Pública para a Sub-rede Pública criada anteriormente

![Acessar edicao de rotas](Imagens%20do%20console%20AWS/37-editar-associacoes-de-sub-rede.jpg)
![Selecionar a sub-rede](Imagens%20do%20console%20AWS/38-sub-rede-publica-selecionada-para-associacao.jpg)
![Tabela de rotas associada](Imagens%20do%20console%20AWS/39-sub-rede-publica-associacada.jpg)
![Tabelas de rotas](Imagens%20do%20console%20AWS/40-tabela-de-rotas-publica-e-privada-criadas.jpg)
