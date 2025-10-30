# -Minha-Primeira-Stack-AWS

Este repositório foi criado como parte dos estudos e desafios do Santander Code Girls - Implementando sua Primeira Stack com AWS CloudFormationn

🚀 Desafio DIO: Infraestrutura como Código (IaC) com AWS CloudFormation

 Este repositório documenta a implementação de uma infraestrutura básica na AWS utilizando o AWS CloudFormation , conforme proposto no desafio de Cloud Foundation da DIO.

O objetivo foi criar um “Stack” (conjunto de recursos) a partir de um arquivo de template declarativo, demonstrando a capacidade de provisionar infraestrutura como código (IaC).

💡 O Conceito Central: Por que IaC?
O CloudFormation é como uma “planta baixa” específica de sua infraestrutura na AWS. Ao provisionar recursos manualmente pelo console (o que é lento e propenso a erros!), nós declaramos exatamente o que queremos (EC2, S3, IAM, etc.) em um arquivo de texto (YAML ou JSON).

O grande benefício é a repetibilidade e a segurança . Sua infraestrutura se torna previsível, auditável e pode ser recriada com um clique, em qualquer região.

Termo Chave	Sem CloudFormation
Modelo	O arquivo YAML/JSON: A planta específica do projeto de infraestrutura.
Pilha	O conjunto de recursos (EC2, S3, etc.) que é gerenciado como uma única unidade.
Reverter	O "Botão Desfazer": Se algo falha durante a criação, a Stack é revertida para o estado anterior.

🏗️ Minha Stack Implementada
O template principal deste desafio ( templates/infrastructure-stack.yaml) declarou a criação de um ambiente fundamental para qualquer aplicação na nuvem:

🎯 Recursos Provisionados
Máquina Virtual (EC2): Uma instância base ( t2.micro).
Segurança de Rede ( SecurityGroup): Firewall simples que permite acesso SSH (Porta 22) .
Armazenamento de Objetos (S3): Um balde simples.
Identidade e Acesso (IAM): Criação de um IAMUsere IAMGroup.

🧩 Funcionalidades e Aprendizados do Template
Seção do YAML	O que aprendi a usar	Por que é Importante?
Parameters	Variáveis ​​de entrada ( InstanceType).	Torna o template flexível, permitindo alterar o tipo de máquina sem mexer no código base.
Mappings	Tabela de busca de valores (ex: UbuntuMap).	Garanta que o modelo funcione em diferentes regiões, pois o ID da AMI é pesquisado corretamente via !FindInMap.

!Ref(Referência)	Conecta recursos (ex: !Ref EC2SecurityGroup).	Garantir que os recursos sejam criados na ordem correta, resolvendo dependências automaticamente.
UserData+Fn::Base64	Scripts de inicialização.	Permite a automação de comandos (ex: apt-get install python3-pip) no primeiro boot do EC2.

📄 Exemplo Extra: Servidor Web Rápido
O arquivo webserver-apache.yamlilustra como a orquestra CloudFormation para a criação de um servidor web funcional:

Criação do Grupo de Segurança (firewall).

✅ Conclusão do Desafio
Este desafio me permitiu consolidar a teoria sobre os serviços AWS e transformá-la na prática usando uma poderosa ferramenta de IaC, o CloudFormation.

Estou pronto(a) para construir e gerenciar ambientes de nuvem de forma escalável, repetível e confiável !

Fontes
[AWS CloudFormation](https://docs.aws.amazon.com/pt_br/AWSCloudFormation/latest/UserGuide/gettingstarted.walkthrough.html) 
– Documentação Oficial
🔗 Desafio proposto por
https://docs.aws.amazon.com/pt_br/AWSCloudFormation/latest/UserGuide/gettingstarted.walkthrough.html
