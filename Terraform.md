
# AWS CLI version 2 Windows

### Links Instalação <br>
https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-windows.html <br>
https://awscli.amazonaws.com/AWSCLIV2.msi <br>
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html <br>

### Configuração Basicas <br>
Passo 1. Entrar em "My Security Credentials" <br>
Passo 2. Entrar em "Minha chave de acesso" <br>
Passo 3. Na sessão "Chaves de acesso (ID da chave..." clicar em "Criar nova chave de acesso" <br>
Passo 4. No Console digitar:  <br>
$ aws configure --profile "terraform" <br>
AWS Access Key ID [None]: AKIAIOAAODNN7EXAMPLE <br>
AWS Secret Access Key [None]: wJalrXUtnCRMI/K7MDENG/bPxRfiCYEXAMPLEKEY <br>
Default region name [None]: us-east-1 <br>
Default output format [None]: json <br>


# Instalando Serverless

### Passo 1. Install Serverless Globally <br>
$ npm install serverless -g <br>

### Passo 2. Create a serverless function <br>
$ serverless create --template aws-nodejs --path nodeless <br>
$ npm init -y <br>

### Passo 3. Configurar Key e SecretKey <br>
No Console da AWS criar usuário com acesso programatico e as devidas chaves de acesso <br>
$ serverless config credentials -o --provider aws --key={key} --secret {secret} <br>

### Passo 4. Deploy to cloud provider <br>
Para rodar o script de deploy localmente configurado no package.json <br>
$ npm run deploy <br>

Fazer o deploy manualmente para o Bucket S3 e criar a Function Lambda (-v de verboso) <br>
$ serverless deploy -v <br>

### Your function is deployed! <br>
$ http://xyz.amazonaws.com/hello-world <br>

### Invoke a Function Criada <br>
Parametro -f é a function e -l lista as operações no console <br>
$ serverless invoke -f hello -l <br>

### Remover todas as tarefas executadas <br>
O comando abaixo remove da aws o bucket s3, cloudInformatin e Function <br>
$ serverless remove <br>


# Instalando SAM - Serverless Application Model

### Step 1 - Download a sample application <br>
sam init <br>

### Step 2 - Build your application <br>
cd sam-app <br>
sam build <br>

### Step 3 - Deploy your application <br>
sam deploy –guided <br>

### Invoking function with event file <br>
$ sam local invoke "HelloWorldFunction" -e events/event.json <br>

### Invoking api gateway local <br>
$ sam local start-api <br>


# Terraform

Terraform Help: <br>
$ terraform -h <br>
$ terraform init -h <br>

Formatando Arquivos: <br>
$ terraform fmt <br>
$ terraform fmt -recursive <br>

Alterando Recursos: <br>
$ terraform plan -out="tfplan.out" <br>
$ terraform apply "tfplan.out" <br>

Aprovando Automaticamente o Plan: <br>
$ terraform apply -auto-approve <br>

Prescedencia de Variáveis: <br>
*auto.tfvars <br>
$ terraform plan -var-file="prod.tfvars" <br>
$ terraform apply -var-file="prod.tfvars" -auto-approve <br>
$ terraform destroy -var-file="prod.tfvars" -auto-approve <br>

Apresentar tfstate: <br>
$ terraform show <br>
$ terraform show -json <br>

Pesquisar Recursos e Atributos: <br>
$ terraform console <br>

Importar Recursos <br>
$ terraform import aws_s3_bucket.bucket bucket-name <br>

Apontar Arquivo de Backend <br>
$ terraform init -backend=true -backend-config="backend.hcl" <br>


# SSH Acesso Instance

Criar um arquivo `keyserver.pem` e colar a chave privada <br>
`$ nano keyserver.pem` > `Ctrl+O` e `Ctrl+X` > `$ ls` <br>

Dar permissão para acesso ao keyserver.pem <br>
`$ chmod 400 keyserver.pem` <br>

Conectar na instância utilizando a keyserver.pem <br>
`$ ssh ec2-user@{IP_PRIVADO_INSTANCIA} -i keyserver.pem` <br>
















































































