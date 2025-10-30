# Gerenciamento de Instâncias EC2 na AWS  

## 1. Introdução

Este repositório foi criado como parte do desafio de consolidação de conhecimentos sobre gerenciamento de instâncias EC2 na AWS.
O objetivo é documentar, de forma clara e organizada, os principais conceitos, práticas e integrações envolvendo o EC2, EBS, S3 e Lambda — compondo uma visão geral de como esses serviços se relacionam dentro de uma arquitetura na nuvem.  

## 2. O que é o Amazon EC2

O Amazon Elastic Compute Cloud (EC2) é um serviço de computação na nuvem que permite criar e gerenciar máquinas virtuais (instâncias) sob demanda. Ele oferece flexibilidade para escolher sistema operacional, capacidade de processamento, memória e configurações de rede, permitindo ajustar os recursos conforme a necessidade do projeto.

Com o EC2, é possível:

Criar e configurar instâncias rapidamente.

Controlar segurança e acesso através de Security Groups e IAM Roles.

Monitorar desempenho e eventos com CloudWatch.

Escalar recursos automaticamente com Auto Scaling Groups.

Automatizar operações utilizando scripts, Lambda ou EventBridge.

## 3. Armazenamento na Nuvem: EBS e S3  

**3.1 Amazon EBS (Elastic Block Store)**  

O Amazon EBS fornece volumes de armazenamento em blocos persistentes que podem ser anexados às instâncias EC2.
Esses volumes funcionam como “discos virtuais” e permanecem disponíveis mesmo após a parada ou reinicialização da instância.

Principais características:

Armazenamento persistente e confiável.

Possibilidade de criar snapshots para backup e restauração.

Ideal para sistemas de arquivos, bancos de dados e aplicações que exigem alta performance de I/O.

Pode ser facilmente redimensionado conforme a necessidade.  

**3.2 Amazon S3 (Simple Storage Service)**

O Amazon S3 é um serviço de armazenamento de objetos projetado para armazenar e recuperar grandes quantidades de dados de forma simples e segura.

Principais características:

Alta durabilidade e escalabilidade.

Armazenamento de qualquer tipo de dado (imagens, vídeos, logs, backups, etc.).

Suporte a versionamento e políticas de ciclo de vida.

Integração com outros serviços da AWS, como EC2 e Lambda.

O S3 é frequentemente utilizado em conjunto com EC2 para armazenar arquivos estáticos, backups de instâncias e dados de aplicações distribuídas.  

## 4. AWS Lambda e Integração com EC2 e S3

O AWS Lambda é um serviço de computação serverless que executa código em resposta a eventos, sem necessidade de gerenciar servidores.
Com ele, é possível automatizar fluxos e tarefas, pagando apenas pelo tempo efetivo de execução do código.

Possíveis integrações:

EC2 + Lambda: automatização de start/stop de instâncias, escalonamento ou manutenção programada.

S3 + Lambda: processamento automático de arquivos enviados ao bucket, como redimensionamento de imagens, análise de logs ou validação de dados.

CloudWatch + Lambda: monitoramento e execução de ações automáticas em resposta a métricas e alarmes.  

## 5. Exemplo de Arquitetura Integrada

Um cenário prático envolvendo EC2, EBS, S3 e Lambda pode ser estruturado da seguinte forma:

Uma instância EC2 hospeda a aplicação principal (exemplo: servidor web).

O EBS é utilizado como armazenamento primário para o sistema e banco de dados.

Backups e arquivos da aplicação são enviados para um bucket S3.

Sempre que um novo arquivo é carregado no S3, uma função Lambda é acionada para processá-lo (por exemplo, converter ou validar o conteúdo).

O CloudWatch monitora o desempenho da EC2 e pode acionar outra Lambda para executar ações automáticas, como escalar recursos ou enviar alertas.

Essa integração exemplifica como os serviços da AWS se complementam, oferecendo automação, alta disponibilidade e eficiência operacional.  

## 6. Conclusão

Gerenciar instâncias EC2 vai muito além de apenas criar servidores.
Envolve compreender e aplicar boas práticas de armazenamento, segurança, automação e integração com outros serviços da AWS.

Ao dominar o EC2 em conjunto com o EBS, S3 e Lambda, é possível construir arquiteturas robustas, escaláveis e otimizadas para diferentes tipos de aplicações em nuvem.  

## 7. Referências

[Documentação Oficial do Amazon EC2](https://docs.aws.amazon.com/ec2/)  
[Documentação Oficial do Amazon EBS](https://docs.aws.amazon.com/ebs/)  
[Documentação Oficial do Amazon S3](https://docs.aws.amazon.com/s3/)  
[Documentação Oficial do AWS Lambda](https://docs.aws.amazon.com/lambda/)  
[AWS CloudWatch](https://docs.aws.amazon.com/cloudwatch/)
