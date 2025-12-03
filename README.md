🟦 AWS API Route Consultant – Java CLI

Um projeto didático desenvolvido para treinar lógica de programação, manipulação de strings, boas práticas REST e fundamentos de cloud AWS usando Java.
Inspirado na rotina de um consultor que organiza API routes, padroniza nomenclaturas e orienta o time sobre qual serviço AWS utilizar em diferentes cenários.

📌 🎯 Objetivo do Projeto

O sistema foi construído com três funcionalidades principais:

1️⃣ Converter endpoints CamelCase em rotas RESTful padronizadas

Entrada:

GetUserProfile


Saída:

/api/v1/get-user-profile

2️⃣ Validar se uma rota segue o padrão REST exigido

Regras:

Deve começar com /api/v1/

Não pode terminar com /

Após o prefixo, deve conter apenas letras minúsculas e hífens

Exemplo (válido):

/api/v1/create-invoice

3️⃣ Sugerir serviço AWS com base em uma descrição de demanda

Exemplos:

"armazenar arquivos" → S3

"subir um servidor" → EC2

"função sob demanda" → Lambda

"banco de dados relacional" → RDS

“rota HTTP, eventos” → API Gateway

Tudo isso simula a visão de um consultor que padroniza rotas e orienta arquiteturas.

🧩 Estrutura do Código
aws-api-route-consultant-java/
 └── src/
     └── main/
         └── java/
             └── awsconsult/
                 ├── Main.java
                 ├── EndpointConverter.java
                 ├── RoutePatternValidator.java
                 ├── AwsService.java
                 └── AwsRouteAdvisor.java

📁 Arquivos Principais
Main.java

Interface CLI com três funcionalidades:

(1) Converter CamelCase → rota RESTful

(2) Validar rota

(3) Sugerir serviço AWS

EndpointConverter.java

Converte nomes CamelCase para o padrão RESTful /api/v1/....

RoutePatternValidator.java

Valida se a rota segue o padrão indicado.

AwsRouteAdvisor.java

Implementa lógica simples para sugerir serviços AWS.

AwsService.java

Enum com 6 opções:

EC2

LAMBDA

API_GATEWAY

S3

RDS

SERVICO_DESCONHECIDO

▶️ Como Rodar o Projeto
1) Compile o código

No diretório raiz:

javac -d out $(find src -name "*.java")

2) Execute
cd out
java awsconsult.Main

📘 Exemplos de Uso
🔹 1. CamelCase → RESTful

Entrada:

GetInvoiceStatus


Saída:

/api/v1/get-invoice-status

🔹 2. Validar rota

Entrada:

/api/v1/list-orders


Saída:

Rota válida

🔹 3. Sugerir serviço AWS

Entrada:

preciso armazenar imagens na nuvem


Saída:

Serviço sugerido: S3

🚀 Possíveis Evoluções

Migrar o projeto para Spring Boot

Criar endpoints reais de validação e conversão

Subir para AWS:

Lambda

API Gateway

DynamoDB para histórico

Criar versão com interface web (HTML/JS)

🏆 Tecnologias Utilizadas

Java 17+

Lógica de Strings e Padrões REST

Enum e Regras de Negócio

Fundamentos AWS (EC2, S3, RDS, Lambda, API Gateway)
