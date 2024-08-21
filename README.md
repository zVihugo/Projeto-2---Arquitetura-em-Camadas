# Projeto 2 - Estudo de Caso: Análise e Proposta de Melhoria do Apache OFBiz
### RA:2503581 Victor Hugo Fávaro Moreira, RA: 2503514 Leandro Henrique Oliveira Neves
### Código do sistema analisado: https://github.com/apache/ofbiz-framework

## 1. Introdução
Este projeto faz parte da disciplina de Arquitetura de software ministrada pelo professor Diego Addan, onde o objetivo é realizar um estudo de caso, documentação, e mapeamento de requisitos e processos de um sistema existente. O sistema escolhido para esta análise é o **Apache OFBiz**, um sistema de gestão empresarial (ERP) open source, modular e altamente escalável.

O Apache OFBiz foi escolhido devido à sua ampla utilização, documentação robusta, além de sua arquitetura modular que o torna um bom software para realizarmos o estudo de caso.

## 2. Arquitetura do Sistema

### 2.1 Tecnologias Utilizadas
- **Linguagem de Programação:**
  - **Java:** A linguagem principal do OFBiz, escolhida por sua compatibilidade multiplataforma e facilidade de integração com outros sistemas.

- **Frameworks:**
  - **Apache Tomcat:** Servidor de aplicação utilizado para hospedar o sistema.
  - **Apache Ant:** Ferramenta de build que gerencia a compilação e a implantação do projeto.
  - **FreeMarker:** Motor de template utilizado para renderização de páginas HTML dinâmicas.

- **Banco de Dados:**
  - **MySQL e PostgreSQL:** OFBiz oferece suporte para diversos bancos de dados, com MySQL e PostgreSQL sendo os mais comuns.

- **Web Framework:**
  - **Apache FreeMarker:** Usado para a geração de conteúdo dinâmico no frontend.
  - **Apache Velocity:** Utilizado em algumas partes específicas do sistema.

- **Libs e Ferramentas:**
  - **jQuery:** Biblioteca JavaScript utilizada para manipulação do DOM e interações AJAX.
  - **Groovy:** Linguagem dinâmica usada para scripts adicionais e complementares.
  - **Gradle:** Ferramenta de automação de build, alternativa ao Apache Ant, dependendo da configuração do projeto.

- **Serviços Web e Integração:**
  - **SOAP e REST:** OFBiz suporta ambas as abordagens para integração de serviços web.
  - **XML:** Amplamente utilizado para configuração e troca de dados entre os módulos do sistema.

### 2.2 Partes do Sistema

#### 2.2.1 Party Manager
- **Descrição:** Módulo responsável pelo gerenciamento de entidades como empregados, fornecedores e clientes, fornecendo ferramentas para cadastro e manutenção dessas entidades.

#### 2.2.2 Catálogo
- **Descrição:** Módulo que facilita a criação e acesso a informações sobre produtos, catálogos e categorias, com funcionalidades avançadas de pesquisa e navegação.

#### 2.2.3 Facility Manager
- **Descrição:** Gerencia armazéns e estoques, permitindo o controle detalhado de inventários em diferentes locais de armazenamento.

#### 2.2.4 Gerenciamento de Pedidos (Order Manager)
- **Descrição:** Sistema para inserção, manutenção e relatórios de pedidos, cotações e solicitações.

#### 2.2.5 Contabilidade
- **Descrição:** Baseado no padrão OMG GL, este módulo permite a gestão contábil de múltiplas organizações, incluindo funções de contas a pagar e a receber (AR/AP).

#### 2.2.6 Gerenciamento de Conteúdo (CMS/DMS)
- **Descrição:** Sistema de gerenciamento de documentos e conteúdo, permitindo a reutilização de dados em diferentes contextos dentro da aplicação.

#### 2.2.7 Componente de Manufatura
- **Descrição:** Gerencia o ciclo de fabricação de produtos, assegurando que os materiais necessários estejam disponíveis no momento adequado.

#### 2.2.8 SFA (Sales Force Automation)
- **Descrição:** Módulo de automação da força de vendas, suportando processos de criação de pedidos para leads.

#### 2.2.9 Recursos Humanos
- **Descrição:** Módulo de gestão de recursos humanos, com funcionalidades para a administração completa de funcionários.

#### 2.2.10 Marketing
- **Descrição:** Módulo de suporte a campanhas de marketing e gestão de leads, integrado aos outros módulos do sistema.

## 2.3 Padrões Arquiteturais

### 2.3.1 MVC (Model-View-Controller)
- **Descrição:** O Apache OFBiz utiliza o padrão arquitetural MVC para organizar a lógica de apresentação e a lógica de negócios, separando claramente as responsabilidades e facilitando a manutenção e escalabilidade do sistema.

### 2.3.2 SOA (Service-Oriented Architecture)
- **Descrição:** O sistema é baseado na arquitetura orientada a serviços (SOA), onde os serviços são unidades lógicas de negócio que interagem entre si para realizar as operações de negócio do sistema.

### 2.3.3 Componentização
- **Descrição:** A arquitetura do OFBiz é altamente modular, com cada componente do sistema encapsulando funcionalidades específicas. Esses componentes podem ser gerenciados e escalados de forma independente, facilitando a manutenção e a atualização do sistema.

## 3. Escalabilidade e Performace

### 3.1 Web Load

#### 3.1.1 Lidar com o carregamento Web
- **Descrição:** O OFBiz pode ser balanceado e acelerado em diferentes pontos entre o usuário e a database. Pode ser Feito através do cliente HTML, Como Edge Router (rota de borda, em tradução livre), 
Acelerador IP, HTTP Server - Apache, Servlet Engine - Tomcat e RDBMS.

#### 3.1.2 Escalabilidade X Performace
- **Descrição:** Os componentes do OFBiz são projetados tendo como foco a escalabilidade, até em momentos em que há de se decidir entre performace e escalabidade, em geral, a escalabilidade é preferida.
No entanto, se não houver nenhum problema de escalabilidade ou esta não for o foco, pode se focar no desempenho.

#### 3.1.2 Escalabilidade X Manutenibilidade
- **Descrição:** Algumas vezes, o design dos projetos podem afetar ou a capacidade de manutenção, ou o desempenho. Nestes casos rotineiros, a capacidade de manutenção tende a ser mais forte e mais escolhida.
Vale ressaltar que, em casos em que determinado design causa uma redução irracional no desempenho, a otimização pode ser feita posteriormente, para ajustar o aplicativo a fim de diminuir o impacto na 
manutenabilidade.

## 4. Propostas de melhorias:

### 4.1 Modernizar a interface (Front-end)

- **Como é feito:** Atualmente o front-end do Apache OFBiz utiliza tecnologias como FreeMarker(Motor de templates para gerar páginas HTML dinâmicas), jQuery(Lib de JS que facilita a manipulação de DOM) e JavaScript e CSS.
- **Proposta:** Atualizar a interface de usuário utilizando frameworks modernos como React, para melhorar a experiência do usuários, tornando a interface mais agradável de utilizar. Como o Apache OFBiz é uma arquitetura orientada a serviços, ele tem essa possibilidade de integrar com front-ends desenvolvidos utilizando essa tecnologia.
- **Base de consulta:** https://www.objective.com.br/insights/modernizacao-de-sistemas-legados/

### 4.2 Modernização da documentação

- **Como é feito**: De modo prático, a explicação documentada é demasiada teórica e sem exemplos práticos e visuais do framework em ação.
- **Proposta**: Atualização da organização do site, de forma a ser mais clara e com exemplos práticos de utilização do framework, a fim de afunilar o tempo de busca de determinadas informações, omitidas por tópicos maiores.

### 4.3 Suporte nativo à microsserviços

- **Como é feito**: Por ser desenvolvido em SOA, a arquitetura do Apache é monolítica, ou seja, não é dividida em serviços independentes. Com isso também, seus módulos possuem interdependências de uns aos outros, causando uma dificuldade em sua separação.
- **Proposta**: Separação do código em diferentes grupos, a fim de terem claras interfaces de comunicação e criação de APIs RESTfull, a fim de abranger ainda mais a integração de seus serviços.
- **Base de consulta:** https://aws.amazon.com/pt/compare/the-difference-between-monolithic-and-microservices-architecture/


#### informações estas que foram retiradas direto da documentação no site oficial: https://nightlies.apache.org/ofbiz/trunk/ofbiz/html5/user-manual.html#CORE_APPLICATION_COMPONENTS, https://nightlies.apache.org/ofbiz/trunk/ofbiz/html5/user-manual.html, https://cwiki.apache.org/confluence/display/OFBIZ/Scaling+and+Performance+Plan

