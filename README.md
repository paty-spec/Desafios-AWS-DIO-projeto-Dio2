# DIO | Projetos AWS - Aprendendo a usar a nuvem.☁️

"Repositório com anotações, insights e tutoriais do AWS. Material de apoio para estudos em AWS Cloud."

🚀Desafio gerenciamento de instâncias EC2.
_______________________________________________________________

📚 Contéudos estudados

🗺️ Introdução AWS e sua infraestrutura 

• Amazon fundada em 1994 como loja de livro sna internet. FundadorJeff Bezos.

• AWS Amazon Web Services foi lançada pela Amazon em 2006,uma resposta para as necessidadesde oferecer serviços de infraestrutura em nuvem.

• A Aws possui uma extensa rede global de data centers chamados de Regions e Availability Zones.

💵 Modelos de Negócios da AWS

• Pricing Flexível AWS oferece um modelo de pagamentoconforme o uso, permitindo que os clientes paguem apenas pelos recursos usados.

🗺️ Regiões e Zonas de disponibilidade.

• São as areas geograficas contendo várias Availability Zones.

• Availability Zones são data centers independentes fisicamente, mas conectados logicamente para garantir alta disponibilidade.

📝 Criação e Configuração da Conta AWS 
• Cadastro e ativação da conta.

• Configuração de MFA 🔑 para segurança.

• Organização de usuários 👤 e grupos 👥 no IAM com permissões bem definidas.

🖥️ Instância EC2 e Otimização de Recursos

• EC2 = máquinas virtuais na AWS.

• Diferentes famílias de instância: compute ⚡, memory 🧠, storage 💾 optimized.

• Otimização: Auto Scaling 📈, Elastic Load Balancer ⚖️, tipos de instância adequados.

☁️ Armazenamento em Nuvem 
• EBS (Elastic Block Store): discos persistentes ligados a EC2.

• S3 (Simple Storage Service): armazenamento de objetos 📂, barato 💸 e altamente escalável 🚀.

👥 IAM: Grupos e Usuários Criados.

Grupos configurados no laboratório:

• GPO-AWS-DataBase 🛢️

• GPO-AWS-Developer 👨‍💻

• GPO-AWS-Linux 🐧

• GPO-AWS-Network 🌐

• GPO-AWS-SuperUsers 🦸

• GPOAdministradorAccess 🛡️

👉 Usuários adicionados via script/CLI 💻, otimizando administração.



## Processo de Implementação e Documentação

Esta seção detalha o processo de criação, configuração e gerenciamento de uma instância EC2, servindo como material de apoio e guia para futuras implementações.

💻 Projeto gerenciando uma instância EC2.

🧪 Objetivos deste laboratório

Aplicar conceitos aprendidos.Organizar e documentar todo o processo técnico.Criar um repositório que sirva de guia para estudos. Preparar para a certificação AWS Cloud Practitioner.



### 1. Preparação: Configuração de Segurança e Rede

Antes de iniciar a instância, foram definidos os seguintes pré-requisitos:

1.  **Criação do Par de Chaves (Key Pair):**
    * **Objetivo:** Garantir o acesso SSH seguro.
    * **Passo a Passo:** Naveguei até EC2 > Network & Security > Key Pairs e criei a chave `minha-chave-ec2.pem`.
    * **Anotação/Insight:** *É crucial proteger o arquivo `.pem` e garantir que ele tenha permissões restritas para evitar acessos não autorizados.*

2.  **Configuração do Grupo de Segurança (Security Group):**
    * **Objetivo:** Atuar como um firewall virtual.

    * **Configurações:** Criado o Security Group `sg-web-access` com regras de entrada (Inbound) liberando as portas:
        * **Porta 22 (SSH):** Acesso liberado apenas para o meu IP  para maior segurança na administração.
        * **Porta 80 (HTTP):** Acesso liberado para (todos) para que o serviço web seja acessível publicamente.
    * **Insight Adquirido:** *Sempre aplicar o princípio do menor privilégio (least privilege) nos Security Groups. Nunca liberar SSH para `0.0.0.0/0` em ambientes de produção.*

🛠️ Atividades Práticas

* Criação e configuração da conta AWS 
* Organização de usuários e grupos no IAM 
* Implementação de instâncias EC2 
* Configuração de volumes EBS e buckets S3 
* Testes de políticas de acesso e permissões 
* Documentação de todo o processo neste repositório 
* Criação de um diagrama de arquitetura no Draw.io para representar a solução.





Explicação do Diagrama

User(Usuário final): envia arquivos para a AWS.

EC2 (Instância de Computação): processa e gerencia as operações, conectado a EBS e RDS.

EBS 💾:
* D-EBS: volume principal.
* E-EBS: volume adicional ou backup.
RDS : banco de dados gerenciado, conectado à EC2.
Fluxos: caminhos de comunicação: Usuário → EC2 → EBS, EC2 → RDS, EC2 ↔ EBS.