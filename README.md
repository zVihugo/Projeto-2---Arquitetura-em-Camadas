# Projeto 2 - Estudo de Caso: Análise e Proposta de Melhoria do Apache OFBiz
### Projeto 2   RA:2503581, Victor Hugo Fávaro Moreira, RA2: 2503514, Leandro Henrique Oliveira Neves

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

### 2.3 Frameworks do Sistema

#### 2.3.1 MVC
- **Descrição:** Apache OFBiz utiliza o classíco frameworkd web MVC (Model View Controller), desginado para requisições básicas de rotas web.

#### 2.3.2 SOA
- **Descrição:** O sistema foi desenvolvido especialmente ao redor do SOA (Service Oriented Architeture), onde os serviços são unidades lógicas de negócio, obtendo a entrada de valores e devolvendo outros valores.

#### 2.3.3 Componentes do framework
- **Descrição:** Todos os arquivos principais de cada componente estão inclusos no arquivo developer-manual.adoc (excendendo-se às webtools, que estão inclusas em user-manuel.adoc).

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

#### informações estas que foram retiradas direto da documentação no site oficial: https://nightlies.apache.org/ofbiz/trunk/ofbiz/html5/user-manual.html#CORE_APPLICATION_COMPONENTS, https://nightlies.apache.org/ofbiz/trunk/ofbiz/html5/user-manual.html, https://cwiki.apache.org/confluence/display/OFBIZ/Scaling+and+Performance+Plan

