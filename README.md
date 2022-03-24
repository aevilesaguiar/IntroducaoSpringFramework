# Introdução ao Spring Framework

1 - Entendendo o Core do Spring.
2 - Inversão de Controle

## Entendendo o Core do Spring.


- Introdução ao Spring Framework
O Spring Framework é uma plataforma Java que fornece suporte abrangente de infraestrutura para o desenvolvimento de aplicativos Java. O Spring lida com a infraestrutura para que você possa se concentrar em seu aplicativo.

O Spring permite que você crie aplicativos a partir de "objetos Java antigos simples" (POJOs) e aplique serviços corporativos de forma não invasiva a POJOs. Esse recurso se aplica ao modelo de programação Java SE e ao Java EE total e parcial.

Exemplos de como você, como desenvolvedor de aplicativos, pode se beneficiar da plataforma Spring:

    - Faça um método Java executar em uma transação de banco de dados sem ter que lidar com APIs de transação.
    - Torne um método Java local um endpoint HTTP sem ter que lidar com a API do Servlet.
    - Torne um método Java local um manipulador de mensagens sem ter que lidar com a API JMS.
    - Faça de um método Java local uma operação de gerenciamento sem ter que lidar com a API JMX.


## Injeção de Dependência e Inversão de Controle

Um aplicativo Java — um termo solto que varia de aplicativos incorporados restritos a aplicativos corporativos de n camadas no lado do servidor — geralmente consiste em objetos que colaboram para formar o aplicativo adequado. Assim, os objetos em um aplicativo têm dependências entre si.

Embora a plataforma Java forneça uma grande variedade de funcionalidades de desenvolvimento de aplicativos, ela carece de meios para organizar os blocos básicos de construção em um todo coerente, deixando essa tarefa para arquitetos e desenvolvedores. Embora você possa usar padrões de projeto como Factory , Abstract Factory , Builder , Decorator e Service Locator para compor as várias classes e instâncias de objetos que compõem um aplicativo, esses padrões são simplesmente isso: melhores práticas com um nome, com uma descrição de o que o padrão faz, onde aplicá-lo, os problemas que ele aborda e assim por diante. Os padrões são práticas recomendadas formalizadas que você mesmo deve implementar em seu aplicativo.

O componente Spring Framework Inversion of Control (IoC) aborda essa preocupação fornecendo um meio formalizado de compor componentes distintos em um aplicativo totalmente funcional pronto para uso. O Spring Framework codifica padrões de design formalizados como objetos de primeira classe que você pode integrar em seu(s) próprio(s) aplicativo(s). Várias organizações e instituições usam o Spring Framework dessa maneira para projetar aplicativos robustos e de fácil manutenção 



## Módulos da Estrutura

![image](https://user-images.githubusercontent.com/52088444/159912165-f0617a94-2058-458a-8469-eba2deaf11b5.png)

- Resumo o Core Container é o nucleo principal do Spring. O core e o beans eles fornecem a estrutura/partes principais do Spring, dentro delas temos o IoC(É a inversão de controle) e injeção de dependencias, Beanfactory implementação do designer partner. Context (Internacionalização e aplicationContext, ele pega a beans factory e extende a bean factory). Expression language define através de xml ou anotações em tempo de execução, valores e comportamentos do beans.

![image](https://user-images.githubusercontent.com/52088444/159928669-b46941b7-0397-4bb6-ab59-b97d0b66365a.png)


As seções a seguir listam os módulos disponíveis para cada recurso junto com seus nomes de artefatos e os tópicos que eles cobrem. Os nomes dos artefatos são correlacionados aos IDs dos artefatos usados nas ferramentas de Gerenciamento de Dependência .

**Contêiner Principal**

O Core Container consiste nos módulos spring-core, spring-beans, spring-context, spring-context-supporte spring-expression (Spring Expression Language).

Os módulos spring-coree fornecem as partes fundamentais da estrutura , incluindo os recursos de IoC e injeção de dependência. O é uma implementação sofisticada do padrão de fábrica. Ele elimina a necessidade de singletons programáticos e permite desacoplar a configuração e a especificação de dependências da lógica real do programa.spring-beansBeanFactory

O módulo Context ( spring-context) baseia-se na base sólida fornecida pelos módulos Core e Beans : é um meio de acessar objetos em um estilo de estrutura semelhante a um registro JNDI. O módulo Context herda seus recursos do módulo Beans e adiciona suporte para internacionalização (usando, por exemplo, pacotes de recursos), propagação de eventos, carregamento de recursos e criação transparente de contextos por, por exemplo, um contêiner Servlet. O módulo Context também suporta recursos Java EE, como EJB, JMX e comunicação remota básica. A ApplicationContextinterface é o ponto focal do módulo Contexto. spring-context-supportfornece suporte para integrar bibliotecas comuns de terceiros em um contexto de aplicativo Spring para armazenamento em cache (EhCache, Guava, JCache), correspondência (JavaMail), agendamento (CommonJ, Quartz) e mecanismos de modelo (FreeMarker, JasperReports, Velocity).

O spring-expressionmódulo fornece uma linguagem de expressão poderosa para consultar e manipular um gráfico de objeto em tempo de execução. É uma extensão da linguagem de expressão unificada (EL unificado) conforme especificado na especificação JSP 2.1. A linguagem suporta definir e obter valores de propriedade, atribuição de propriedade, invocação de método, acesso ao conteúdo de arrays, coleções e indexadores, operadores lógicos e aritméticos, variáveis ​​nomeadas e recuperação de objetos por nome do contêiner IoC do Spring. Ele também suporta projeção e seleção de listas, bem como agregações de listas comuns.


**AOP e Instrumentação**

O spring-aopmódulo fornece uma implementação de programação orientada a aspectos compatível com AOP Alliance, permitindo que você defina, por exemplo, interceptores de método e pontos de corte para desacoplar de maneira limpa o código que implementa a funcionalidade que deve ser separada. Usando a funcionalidade de metadados de nível de origem, você também pode incorporar informações comportamentais em seu código, de maneira semelhante à dos atributos .NET.

O spring-aspectsmódulo separado fornece integração com o AspectJ.

O spring-instrumentmódulo fornece suporte de instrumentação de classe e implementações de carregador de classe para serem usados ​​em determinados servidores de aplicativos. O spring-instrument-tomcat módulo contém o agente de instrumentação do Spring para Tomcat.


**Mensagens**

O Spring Framework 4 inclui um spring-messagingmódulo com abstrações-chave do projeto Spring Integration , como Message, MessageChannel, MessageHandler, e outros para servir como base para aplicativos baseados em mensagens. O módulo também inclui um conjunto de anotações para mapeamento de mensagens para métodos, semelhante ao modelo de programação baseado em anotações Spring MVC.

**Acesso/Integração de Dados**

A camada Acesso/Integração de Dados consiste nos módulos JDBC, ORM, OXM, JMS e Transação.

O spring-jdbcmódulo fornece uma camada de abstração JDBC que elimina a necessidade de codificação JDBC tediosa e análise de códigos de erro específicos do fornecedor do banco de dados.

O spring-txmódulo suporta gerenciamento de transações programáticas e declarativas para classes que implementam interfaces especiais e para todos os seus POJOs (Plain Old Java Objects) .

O spring-ormmódulo fornece camadas de integração para APIs de mapeamento objeto-relacional populares, incluindo JPA , JDO e Hibernate . Usando o spring-ormmódulo, você pode usar todas essas estruturas de mapeamento O/R em combinação com todos os outros recursos que o Spring oferece, como o recurso de gerenciamento de transação declarativo simples mencionado anteriormente.

O spring-oxmmódulo fornece uma camada de abstração que suporta implementações de mapeamento Object/XML como JAXB, Castor, XMLBeans, JiBX e XStream.

O spring-jmsmódulo ( Java Messaging Service ) contém recursos para produzir e consumir mensagens. Desde o Spring Framework 4.1, ele fornece integração com o spring-messagingmódulo.

**Web**

A camada da Web consiste nos módulos spring-web, spring-webmvc, spring-websockete .spring-webmvc-portlet

O spring-webmódulo fornece recursos básicos de integração orientados para a web, como a funcionalidade de upload de arquivos de várias partes e a inicialização do contêiner IoC usando ouvintes de Servlet e um contexto de aplicativo orientado para a web. Ele também contém um cliente HTTP e as partes relacionadas à web do suporte remoto do Spring.

O spring-webmvcmódulo (também conhecido como módulo Web-Servlet ) contém o model-view-controller ( MVC ) do Spring e a implementação de serviços Web REST para aplicativos da web. A estrutura MVC do Spring fornece uma separação clara entre o código do modelo de domínio e os formulários da Web e se integra a todos os outros recursos do Spring Framework.

O spring-webmvc-portletmódulo (também conhecido como módulo Web-Portlet ) fornece a implementação MVC para ser usada em um ambiente Portlet e espelha a funcionalidade do spring-webmvcmódulo baseado em Servlet.

**A camada da Web consiste nos módulos spring-web, spring-webmvc, spring-websockete .spring-webmvc-portlet

O spring-webmódulo fornece recursos básicos de integração orientados para a web, como a funcionalidade de upload de arquivos de várias partes e a inicialização do contêiner IoC usando ouvintes de Servlet e um contexto de aplicativo orientado para a web. Ele também contém um cliente HTTP e as partes relacionadas à web do suporte remoto do Spring.

O spring-webmvcmódulo (também conhecido como módulo Web-Servlet ) contém o model-view-controller ( MVC ) do Spring e a implementação de serviços Web REST para aplicativos da web. A estrutura MVC do Spring fornece uma separação clara entre o código do modelo de domínio e os formulários da Web e se integra a todos os outros recursos do Spring Framework.

O spring-webmvc-portletmódulo (também conhecido como módulo Web-Portlet ) fornece a implementação MVC para ser usada em um ambiente Portlet e espelha a funcionalidade do spring-webmvcmódulo baseado em Servlet.**

**Cenário de Uso**

Os blocos de construção descritos anteriormente fazem do Spring uma escolha lógica em muitos cenários, desde aplicativos incorporados que são executados em dispositivos com recursos limitados até aplicativos corporativos completos que usam a funcionalidade de gerenciamento de transações do Spring e a integração da estrutura da web.

**Aplicativo Web Spring completo típico**

![image](https://user-images.githubusercontent.com/52088444/159926474-f8e28a1b-defd-4b55-8658-a4ca3b6d43d2.png)

Os recursos de gerenciamento de transações declarativas do Spring tornam o aplicativo da Web totalmente transacional, assim como seria se você usasse transações gerenciadas por contêiner EJB. Toda a sua lógica de negócios personalizada pode ser implementada com POJOs simples e gerenciada pelo contêiner IoC do Spring. Serviços adicionais incluem suporte para envio de e-mail e validação independente da camada da web, que permite escolher onde executar as regras de validação. O suporte ORM do Spring é integrado com JPA, Hibernate e JDO; por exemplo, ao usar o Hibernate, você pode continuar usando seus arquivos de mapeamento existentes e a SessionFactoryconfiguração padrão do Hibernate. Os controladores de formulário integram perfeitamente a camada da Web com o modelo de domínio, eliminando a necessidade deActionFormsou outras classes que transformam parâmetros HTTP em valores para seu modelo de domínio.

**Camada intermediária do Spring usando uma estrutura da Web de terceiros**

![image](https://user-images.githubusercontent.com/52088444/159926589-76d1b216-f17d-4c79-b183-e6dbb6eec1cb.png)

Às vezes, as circunstâncias não permitem que você mude completamente para uma estrutura diferente. O Spring Framework não força você a usar tudo dentro dele; não é uma solução de tudo ou nada . Front-ends existentes construídos com Struts, Tapestry, JSF ou outras estruturas de interface do usuário podem ser integrados a uma camada intermediária baseada em Spring, que permite usar recursos de transação Spring. Você simplesmente precisa conectar sua lógica de negócios usando um ApplicationContexte usar um WebApplicationContextpara integrar sua camada da web.

**Cenário de uso remoto**

![image](https://user-images.githubusercontent.com/52088444/159926699-310da02f-2713-463b-854d-83e314126dd3.png)

Quando você precisar acessar o código existente por meio de serviços da Web, poderá usar as classes Hessian-, Burlap-, Rmi-ou do Spring. JaxRpcProxyFactoryHabilitar o acesso remoto a aplicativos existentes não é difícil.

**EJBs - Envolvendo POJOs existentes**

![image](https://user-images.githubusercontent.com/52088444/159926794-0a00eb0b-2c73-45bb-9f4d-4320dd8b1994.png)

O Spring Framework também fornece uma camada de acesso e abstração para Enterprise JavaBeans, permitindo que você reutilize seus POJOs existentes e os envolva em beans de sessão sem estado para uso em aplicativos da Web escaláveis ​​e à prova de falhas que possam precisar de segurança declarativa.




