# AWS-CodeGirls-Desafio-6


---
### 🚀 Visão Geral

Este projeto apresenta um fluxo automatizado de processamento de arquivos utilizando serviços **AWS simulados com o LocalStack**.
A ideia central é demonstrar como um **upload no Amazon S3** pode acionar uma **função AWS Lambda**, que processa as informações e as grava no **Amazon DynamoDB**.

Todo o ambiente foi executado **localmente**, garantindo testes rápidos, sem custos e com total integração entre os serviços emulados.

---

### 🧩 Funcionamento do Fluxo

👤 O **usuário**  realiza o envio de um arquivo para o **bucket S3.**
☁️ **O evento de upload** vaciona automaticamente uma **função Lambda** configurada como trigger.
⚙️ A função **processa o conteúdo** e grava os dados estruturados no DynamoDB.
🔗 O **API Gateway** é utilizado para expor os **dados armazenados** permitindo que um **cliente** (como o Postman ou uma aplicação externa) consulte os registros de forma prática.

---

### 📚 Conceitos Aplicados

 
Este projeto aborda na prática diversos tópicos importantes de computação em nuvem:

**☁️ Amazon S3:** armazenamento e gestão de arquivos.
**⚙️ AWS Lambda** funções serverless para processamento automatizado.
**🗄️ Amazon DynamoDB:** banco de dados NoSQL escalável e de alta performance.
**🔗 Amazon API Gateway:** interface para exposição de dados via endpoints REST.
**🧩 LocalStack:** simulação de serviços AWS em ambiente local para testes e desenvolvimento.
**💻 AWS CLI:** criação e gerenciamento de recursos AWS de forma automatizada.

---


### 🛠️ Requisitos e Ferramentas

Para executar o projeto, são necessárias as seguintes ferramentas:

**🐳 Docker:**para rodar o container do LocalStack.
**🐍 Python 3.x:** linguagem usada na função Lambda.
**📦 Pipenv ou venv:** para controle de dependências.
**☁️ AWS CLI:** linha de comando para gerenciar recursos.
**⚙️ LocalStack CLI:** instalação via pip install localstack.   

---



###🧰 Comandos para Configuração###

---

### ⚙️ Passo a Passo de Execução

| **1-Iniciar o LocalStack:**|
|----------------|------------------------|---------------|
localstack start


| **2-Criar os recursos AWS simulados:**|
|----------------|------------------------|---------------|
aws s3api create-bucket --bucket arquivos-projeto --endpoint-url=http://localhost:4566

-Configure também a **função Lambda** e a **tabela DynamoDB**, vinculando a trigger do S3 à Lambda.


**3-Implementar o código da Lambda:**
-O script (exemplo: lambda_function.py) é responsável por ler o arquivo recebido, extrair e tratar dados, e registrar o resultado no DynamoDB.

**4-Testar o fluxo:**

-Faça upload de um arquivo para o bucket S3.
-Verifique a execução automática da função Lambda.
-Confirme os registros gravados no DynamoDB.
-Utilize o API Gateway ou o Postman para consultar os dados processados.


---

### ✅ Conclusão ###

O projeto demonstrou, de forma prática, como integrar S3, Lambda e DynamoDB para criar uma arquitetura serverless automatizada e escalável.
O uso do LocalStack permitiu simular os serviços da AWS localmente, facilitando o aprendizado e os testes sem custos.
Assim, foi possível compreender todo o fluxo de automação — do upload de arquivos ao acesso dos dados via API.
