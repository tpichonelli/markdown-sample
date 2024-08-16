# **SAST - Qualidade de Código**  

<br/>

A Análise Estática, é um Processo executado durante a Integração Contínua (*CI*) das Aplicações para Inspeção da Qualidade do Código-fonte.

No Projeto, utilizamos uma Ferramenta para essa finalidade, o **SonarQube**.

<br/>

## **1. SonarQube para Qualidade de Códigos-fonte**

![sonarqube-image](/attachments/sonarqube-image.png "SonarQube Image")
O [SonarQube](https://docs.sonarqube.org/latest/ "Documentação sobre o SonarQube"), é uma Plataforma para Inspeção Contínua da Qualidade de Código, afim de executar Revisões Automáticas com Análise Estática do Código-fonte para detectar possíveis *Bugs*, *Code smells* e vulnerabilidades de segurança.

<br/>

### **1.1. *Quality Gates***
O *Quality *Gate*, é um Conjunto de Métricas configuradas para Medir a Qualidade dos Códigos-fonte. E para o Projeto, foi criado o ***ProjetoExemplo_Way*** e nele estão presentes as seguintes Métricas:

Métrica|Operador|Erro
-|-|-
*Coverage* | é menor que | 80%
*Coverage on New Code* | é menor que | 80%
*Maintainability Rating* | é pior que | A
*Maintainability Rating on New Code* | é pior que | A
*Reliability Rating* | é pior que | A
*Reliability Rating on New Code* | é pior que | A
*Security Rating* | é pior que | A
*Security Rating on New Code* | é pior que | A

> **Nota:** caso qualquer Pontuação Listada acima não seja atingida durante uma Análise, o *Pipeline* de *Build* da Aplicação em questão falhará.

<br/>

### **1.2. *Quality Profiles***
O *Quality Profile*, é uma Coleção de Regras a serem aplicadas e validadas durante uma Análise. Para cada Linguagem de Programação, existe um Perfil Padrão.

O Perfil criado para Linguagem **Java**, se chama ***Java Way***, suas Regras foram herdadas do Perfil Padrão ***Sonar Way*** e o Projeto **ExemploProjetoClaro***, foi vinculado a esse Novo Perfil. Inicialmente, nenhuma Regra foi modificada, sua criação foi feita afim de facilitar futuras Modificações das Regras, caso haja necessidade.

> **Nota:** atualmente o *ExemploProjetoClaro*, é a única Aplicação que possui Código-fonte em Java.

<br/>

### **1.3. Funcionamento**
Para Inspecionar a Qualidade do Código da Aplicação, é necessário que haja o Pacote do [SonarScanner](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/ "Documentação sobre o SonarScanner") configurado na Imagem *Docker* de *CI*.

<br/>