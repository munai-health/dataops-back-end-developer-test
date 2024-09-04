![Logo MunAI](img/munai_logotipo.png)
***
# Desafio dataops-back-end-developer-test

Obrigado por participar de nosso processo seletivo.

## Instruções

### Crie um repositório no seu GitHub

Todos os artefatos e entregáveis produzidos deverão ser organizados em um repositório público no Github vinculado a sua conta pessoal.

### Faça seus commits descritivos e específicos no seu repositório

Atenção, avaliaremos o conteúdo de seus commits, bem como a frequência de envio. Também é importante que a descrição dos commits esteja de acordo com o conteúdo.

### Configurar ambiente docker para rodar a aplicação

Ao final do desenvolvimento, o projeto deve rodar com o commando:

```bash
docker compose up
```

## O Desafio

**Resumo:** O objetivo deste desafio é configurar um servidor FHIR localmente, desenvolver uma API para receber dados de pacientes em formato CSV, e criar um serviço assíncrono para processar esses dados e enviá-los ao servidor FHIR. Tudo deve ser implementado utilizando **Python** ou **Java**, com foco em eficiência e boas práticas de desenvolvimento.
### Configuração do Servidor FHIR (Arquitetura)
O primeiro passo é configurar um servidor FHIR no seu ambiente local (sem usar soluções _cloud_). Recomendamos o uso de containers Docker configurados via um arquivo Docker Compose. O servidor FHIR deve ser baseado em uma solução _Open Source_, como o [HAPI FHIR](https://hapifhir.io/) ou uma alternativa similar. Além disso, você deverá desenvolver uma API RESTful utilizando **Python** ou **Java** que receba arquivos CSV e seja responsável por armazenar temporariamente os dados, antes que outro serviço os processe de forma assíncrona.

### Integração e Carga de Dados para o _Resource Patient_ (Integração de Dados)
Após a configuração do servidor FHIR e da API, você deve criar um serviço assíncrono, também em **Python** ou **Java**, que consuma os dados recebidos via CSV pela API. Esse serviço será responsável por transformar os dados e enviá-los para o servidor FHIR para persistir as informações.

Os dados a serem carregados estão disponíveis em [data/patients.csv](data/patients.csv) e devem ser mapeados para o _Resource Patient_ no servidor FHIR. A coluna "observação", que contém informações adicionais sobre o estado de saúde do paciente, deve ser carregada para o _Resource_ correspondente (como _Observation_ ou _Condition_, dependendo do conteúdo).

Para realizar a carga e integração dos dados, você deve utilizar **Python** ou **Java** como linguagem principal, garantindo que o sistema funcione de maneira eficiente e assíncrona. A integração com o servidor FHIR deve ser feita respeitando a estrutura dos _Resources_ FHIR.

### Restrições
- O desafio deve ser implementado exclusivamente em **Python** ou **Java**.

### Bônus
- Fique à vontade para utilizar **Python** em um serviço (como a API) e **Java** no outro (como o processamento assíncrono), ou vice-versa. Isso incentivará o uso das melhores práticas de ambas as linguagens no desafio.

### Entregáveis
- Documentação de configuração do servidor FHIR
- Arquivo Docker Compose e configuração de containers
- API RESTful em Python ou Java para recebimento do CSV
- Serviço assíncrono em Python ou Java que processa e insere os dados no servidor FHIR
- Documentação detalhada dos serviços desenvolvidos, incluindo arquitetura, configuração e exemplos de uso.

## Critérios de Avaliação

Além dos requisitos levantados acima, iremos considerar os seguintes critérios durante a avaliação do desafio:

- **Extensibilidade do projeto:** O código deve permitir a fácil inclusão de novas funcionalidades e mudanças na arquitetura ou banco de dados;
- **Gestão de dependências:** Organização clara e eficiente de dependências do projeto (bibliotecas, pacotes, etc.);
- **Estrutura de API:** O design da API deve seguir boas práticas, ser bem documentado e fácil de usar;
- **Manutenção de estado:** O sistema deve ser capaz de gerenciar o estado de maneira eficiente, principalmente em operações assíncronas;
- **Preocupação com segurança:** Aplicação de boas práticas de segurança, como autenticação, autorização e proteção contra vulnerabilidades comuns (por exemplo, SQL Injection, CSRF, XSS);
- **Escalabilidade:** Solução com arquitetura que suporte o aumento do volume de dados e acessos;
- **Boas práticas de performance:** Otimização de consultas ao banco de dados, processamento de dados e resposta da API;
- **Testes automatizados:** Implementação de testes unitários e de integração cobrindo cenários essenciais do sistema;
- **Utilização de variáveis de ambiente:** Configuração adequada para ambientes de desenvolvimento, teste e produção;
- **Padrões de design de código:** Adoção de design patterns adequados como SOLID, Clean Architecture, ou DDD (Domain-Driven Design);
- **Padronização de commits:** Utilização de [commits convencionais](https://www.conventionalcommits.org/pt-br/v1.0.0/);
- **Documentação clara:** A aplicação deve conter documentação completa e clara, explicando o processo de instalação, configuração, uso da API, e qualquer dependência necessária para rodar o projeto;
- **Código em inglês:** Código e documentação devem estar em inglês, facilitando a compreensão global.
- **Racional Técnico e Decisões de Desenvolvimento:** Inclua um passo a passo detalhado das decisões tomadas ao longo do desenvolvimento, com explicações claras sobre os motivos técnicos que justificaram cada escolha. Isso deve abranger aspectos como a arquitetura adotada, design de banco de dados, seleção de tecnologias, padrões de código e práticas de segurança. O objetivo é demonstrar o raciocínio técnico por trás de cada decisão, evidenciando a compreensão das melhores práticas e a adequação ao escopo do projeto.

---

_O desafio acima foi cuidadosamente construído para propósitos de avaliação apenas._
