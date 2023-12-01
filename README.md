# ittalent-devops-terraform
Praticas para Terraform - Curso IT Talent

# Objetivo

Olá jovens! conforme praticamos e vimos os conceitos de terraform nas aulas hoje trago para vocês um desafio prático para levantarem uma infraestrutura em Cloud de forma automatizada na AWS via terraform.
Durante nossas aulas de AWS montamos uma infraestrutura simples para comportar um site estático que era composto por um Bucket S3, EC2 e Load balancer. Porém nas aulas fizemos tudo manual através do console web da AWS, então a ideia é automatizamos tudo isso via Terraform :)    (caso você não tenha feito essa atividade de AWS procure no classroom as atividades III e IV do módulo de AWS)

# Atividade Prática

Bom, vindo para atividade teremos os seguintes critérios a serem atendido:

- Subir 2 instancias EC2
- Via terraform realizar instalação e configuração automatica do nginx para servir como proxy reverso e mandar as requisições para o bucket s3
- Subir 1 Bucket S3
- Via terraform deixar o bucket publicamente acessivel e pronto para hospedar um site estático
- subir os arquivos do site estático dentro dentro do bucket iguais os que fizemos na atividade prática de aws (https://github.com/heltonlima20/ittalent-devops-aws)
- No final subir infraestrutura e acessar o site estático através do DNS público da Ec2

Desafio Extra!
-
Não é obrigatório e nem vale nota essa parte porém quem se sentir confortável com a atividade pode ir um pouco acima e nessa mesma infraestrutura implementar um Load Balancer para ficar acima das Ec2 e receber requisições. Quanto mais praticarem melhor vão ficar !

Dicas e Anotações
-
- Sinta-se a vontade para usar a criativade! não existe uma regra para fazer algo, a mesma coisa pode ser feito de várias formas diferentes.
- Utlize a documentação oficial do terraform, lá tem tudo :) https://developer.hashicorp.com/terraform/docs https://registry.terraform.io/providers/hashicorp/aws/latest
- Revisem a gravação das aulas
- Não esqueçam de revisar para que cada bloco de código do terraform serve
- Vou deixar listado abaixo todos os blocos que vocês precisam para configurar essa atividade

EC2
-
- resource "aws_instance" (recurso para usar EC2)
- provisioner "file" (opcional para subir arquivos para ec2)
- provisioner "remote-exec" (Para executar comandos remotos)
- connection (Para atribuir acesso remoto a ec2)

S3
-
- resource "aws_s3_bucket" (recurso para usar S3)
- resource "aws_s3_bucket_website_configuration" (ativar hospedagem estatica do s3)
- resource "aws_s3_bucket_public_access_block" (liberar ou bloquear acesso publico s3)
- resource "aws_s3_bucket_acl" (configurações e ACL)
