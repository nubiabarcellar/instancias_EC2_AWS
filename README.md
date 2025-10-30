# Instâncias EC2 na AWS

💻 Gerenciamento de Instâncias EC2 na AWS
🌐 Visão Geral

O Amazon EC2 (Elastic Compute Cloud) é um dos principais serviços da AWS e permite criar e gerenciar máquinas virtuais (chamadas de instâncias) na nuvem. Ele oferece poder de processamento sob demanda, escalabilidade e flexibilidade para rodar praticamente qualquer tipo de aplicação — de pequenos sites até grandes sistemas corporativos.

Com o EC2, é possível escolher o tipo de instância, o sistema operacional, a quantidade de CPU e memória, e também configurar redes e segurança. Tudo isso pode ser gerenciado facilmente pelo Console da AWS, CLI (Command Line Interface) ou infraestrutura como código (IaC), como o Terraform ou AWS CloudFormation.

⚙️ Gerenciamento de Instâncias EC2

O gerenciamento de instâncias EC2 envolve:

Criação e configuração: Escolher a AMI (Amazon Machine Image), tipo de instância, rede (VPC), grupos de segurança (firewalls) e pares de chaves (para acesso SSH).

Monitoramento: Utilizar o Amazon CloudWatch para acompanhar métricas como uso de CPU, memória e disco.

Escalabilidade: Com Auto Scaling Groups, é possível aumentar ou reduzir automaticamente o número de instâncias conforme a demanda.

Segurança: Controlar acessos com IAM Roles, Security Groups e Network ACLs, garantindo que apenas usuários e serviços autorizados possam interagir com a instância.

Automação: A criação, atualização e finalização de instâncias pode ser automatizada com scripts ou ferramentas como AWS Lambda e EventBridge.

💾 Armazenamento na Nuvem: EBS e S3
🧱 EBS (Elastic Block Store)

O Amazon EBS fornece volumes de armazenamento em blocos que podem ser anexados a instâncias EC2, funcionando como “discos virtuais”.

Armazenamento persistente: os dados permanecem mesmo após a parada da instância.

Permite snapshots (cópias de segurança) e restauração rápida.

Ideal para sistemas operacionais, bancos de dados e aplicações que exigem acesso constante a dados em disco.

☁️ S3 (Simple Storage Service)

O Amazon S3 é um serviço de armazenamento de objetos, usado para guardar e recuperar qualquer tipo de dado (imagens, vídeos, backups, logs, etc.).

Altamente escalável e durável.

Permite controle de acesso, versionamento e políticas de ciclo de vida dos objetos.

Muito usado em conjunto com EC2 para armazenar dados de entrada/saída de aplicações, backups automáticos e arquivos estáticos.

⚡ AWS Lambda e Integração com EC2 e S3

O AWS Lambda é um serviço de computação sem servidor (serverless) que executa código sob demanda — sem a necessidade de gerenciar servidores.

Você escreve apenas a função (em Python, Node.js, etc.) e define gatilhos (triggers) que a disparam, como o upload de um arquivo no S3, um evento no CloudWatch ou uma requisição HTTP via API Gateway.

Paga apenas pelo tempo de execução do código.

💡 Exemplo de Arquitetura Integrada

Uma arquitetura comum integrando EC2, EBS, S3 e Lambda pode funcionar assim:

Uma instância EC2 hospeda uma aplicação principal (ex: servidor web ou backend).

Essa instância utiliza EBS como armazenamento principal (sistema e banco de dados).

Os backups e arquivos de mídia são enviados para um bucket S3.

Sempre que um novo arquivo é enviado ao S3, uma função Lambda é acionada para processar ou validar o conteúdo.

O CloudWatch monitora o desempenho da EC2 e pode acionar outra Lambda para escalar recursos automaticamente ou enviar alertas.

Essa integração mostra como os serviços da AWS trabalham juntos para oferecer alta disponibilidade, automação e eficiência em aplicações na nuvem.

🧭 Conclusão

Gerenciar instâncias EC2 na AWS vai além de apenas criar servidores — envolve planejar armazenamento, automação, segurança e integração com outros serviços. Ao dominar EC2, EBS, S3 e Lambda, você constrói bases sólidas para arquiteturas modernas e escaláveis na nuvem.
