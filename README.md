# Laboratório de Cibersegurança — Kali Linux, Medusa e DVWA

## Sobre o projeto

Este repositório documenta meu aprendizado no desafio prático de cibersegurança da **Digital Innovation One (DIO)**, utilizando Kali Linux, Nmap, Medusa e a aplicação Damn Vulnerable Web Application (DVWA).

O projeto tem como objetivo compreender, por meio de experimentos práticos, o funcionamento de mecanismos de autenticação, os riscos associados a credenciais previsíveis e os fundamentos das requisições HTTP.

As atividades são desenvolvidas em um laboratório virtual controlado, com máquinas destinadas exclusivamente a testes educacionais e autorizados.

Além da execução dos experimentos, procuro compreender os comandos utilizados, interpretar os resultados, registrar evidências técnicas e relacionar os conhecimentos adquiridos às boas práticas de segurança e gestão de riscos.

## Objetivos

- Aprender os fundamentos de autenticação e ataques de força bruta.
- Utilizar ferramentas de segurança em ambientes controlados.
- Compreender os conceitos de enumeração e identificação de serviços.
- Identificar riscos relacionados a credenciais fracas, previsíveis ou padronizadas.
- Compreender requisições HTTP, códigos de resposta e parâmetros de formulários web.
- Documentar experimentos, resultados e evidências técnicas.
- Identificar medidas de prevenção e mitigação de riscos.
- Desenvolver conhecimentos práticos de cibersegurança e gestão de riscos.

## Ambiente do laboratório

| Componente | Configuração |
|---|---|
| Sistema de testes | Kali Linux 2026.3 |
| Máquina vulnerável | Metasploitable 2 |
| Aplicação web | DVWA |
| IP do Kali Linux | 10.0.0.9 |
| IP do Metasploitable 2 | 10.0.0.10 |
| Rede | Ambiente virtual privado de laboratório |
| Ferramentas | Nmap, Medusa 2.3, Firefox Developer Tools, cURL e grep |
| Acesso | Interface gráfica remota |

Os endereços apresentados são privados e pertencem exclusivamente ao ambiente didático.

## Etapas do projeto

- [x] Criar repositório no GitHub.
- [x] Verificar a configuração do Kali Linux.
- [x] Confirmar a instalação do Medusa.
- [x] Verificar a conectividade entre as máquinas do laboratório.
- [x] Identificar o serviço FTP utilizando Nmap.
- [x] Criar uma wordlist simples para testes.
- [x] Executar um teste controlado de autenticação FTP com Medusa.
- [x] Analisar o resultado e identificar medidas de mitigação.
- [x] Realizar testes manuais de autenticação no DVWA.
- [x] Inspecionar requisições HTTP e parâmetros de formulários web.
- [x] Adicionar capturas de tela dos três experimentos.
- [x] Organizar a documentação técnica individual dos experimentos.
- [x] Executar os próximos cenários práticos previstos no laboratório.
- [x] Consolidar as recomendações de segurança.
- [x] Finalizar a documentação e entregar o projeto na DIO.

## Experimentos realizados

Este projeto reúne experimentos práticos de cibersegurança executados em um laboratório virtual controlado, utilizando Kali Linux e Metasploitable 2.

| Experimento | Ferramentas | Resultado |
|---|---|---|
| [01 — Auditoria de autenticação FTP](experimentos/01-ftp-medusa.md) | Nmap e Medusa | Identificação de credencial válida em serviço FTP vulnerável |
| [02 — Análise de autenticação web no DVWA](experimentos/02-dvwa-bruteforce.md) | Firefox e DVWA | Comparação entre tentativas manuais de autenticação válidas e inválidas |
| [03 — Análise de requisições HTTP no DVWA](experimentos/03-dvwa-http.md) | Firefox Developer Tools, cURL e grep | Identificação de parâmetros HTTP, redirecionamentos e campos de formulários |
| [04 — Teste automatizado no DVWA](experimentos/04-dvwa-hydra.md) | Hydra 9.7 | Execução automatizada com uma credencial conhecida do laboratório |
### Experimento 01 — Auditoria de autenticação FTP

Foi realizada a identificação do serviço FTP na porta 21/TCP e uma simulação controlada de tentativas de autenticação utilizando o Medusa.

**Resultado:** uma credencial válida de laboratório foi identificada, demonstrando os riscos associados ao uso de senhas previsíveis ou padronizadas.

[Consultar documentação e evidências](experimentos/01-ftp-medusa.md)

### Experimento 02 — Autenticação web no DVWA

Foi utilizada a aplicação DVWA, configurada no nível de segurança `low`, para observar o comportamento de um formulário web diante de credenciais válidas e inválidas.

**Resultado:** foram documentadas as respostas da aplicação durante testes manuais de autenticação, permitindo comparar situações de sucesso e falha.

[Consultar documentação e evidências](experimentos/02-dvwa-bruteforce.md)

### Experimento 03 — Análise de requisições HTTP no DVWA

Foi realizada uma análise de requisições e respostas HTTP utilizando Firefox Developer Tools, cURL e grep.

O experimento permitiu observar parâmetros de autenticação transmitidos em uma requisição GET do módulo Brute Force, interpretar códigos HTTP como `200 OK` e `302 Found` e identificar os campos HTML do formulário de login inicial do DVWA.

**Resultado:** compreensão do funcionamento das requisições HTTP, dos redirecionamentos e dos riscos relacionados à exposição de credenciais em parâmetros de URL.

[Consultar documentação e evidências](experimentos/03-dvwa-http.md)

## Próximas atividades

- [x] Criar o repositório e organizar a documentação.
- [x] Configurar e validar o ambiente de laboratório.
- [x] Realizar auditoria de autenticação FTP com Medusa.
- [x] Documentar testes manuais de autenticação no DVWA.
- [x] Analisar requisições HTTP e formulários web no DVWA.
- [x] Executar teste automatizado no formulário Brute Force do DVWA.
- [x] Estudar password spraying em SMB no ambiente autorizado.
- [x] Consolidar recomendações de segurança.
- [x] Finalizar a documentação e entregar o projeto na DIO.

Os procedimentos, resultados e evidências estão organizados individualmente na pasta `experimentos`, com as capturas de tela armazenadas na pasta `images`.

## Diário de aprendizagem

### Etapa 1 — Organização do projeto

Criei um repositório público no GitHub para registrar as atividades práticas, os conceitos estudados e as evidências obtidas durante o curso.

Optei por manter um documento individual para cada experimento, facilitando a organização, a consulta e a evolução do projeto.

### Etapa 2 — Preparação do laboratório

Acessei o Kali Linux por meio de sua interface gráfica remota.

Utilizei comandos do terminal para identificar a versão do sistema, verificar o endereço IP e confirmar a comunicação com a máquina Metasploitable 2.

A conectividade foi validada com o comando `ping`, sem perda de pacotes durante o teste realizado.

### Etapa 3 — Identificação do serviço FTP

Utilizei o Nmap para verificar a porta 21/TCP do Metasploitable 2.

O resultado identificou o serviço FTP ativo, utilizando `vsftpd 2.3.4`.

Esse procedimento permitiu compreender a importância da identificação de serviços antes da realização de uma auditoria de autenticação.

### Etapa 4 — Primeiro experimento com Medusa

Confirmei a instalação do Medusa e a disponibilidade de seus módulos.

Criei uma lista com quatro senhas de laboratório e executei um teste controlado de autenticação FTP.

O Medusa identificou uma credencial válida para a conta de laboratório `msfadmin`.

O resultado demonstrou o risco de manter credenciais previsíveis ou padronizadas em sistemas reais.

**Documentação completa:** [Experimento 01 — FTP com Medusa](experimentos/01-ftp-medusa.md).

### Etapa 5 — Testes manuais de autenticação web

Acessei a aplicação DVWA no ambiente de laboratório e configurei o nível de segurança `low`.

No módulo Brute Force, realizei tentativas manuais de autenticação com credenciais válidas e inválidas.

Observei as mensagens apresentadas pela aplicação e documentei os resultados com capturas de tela.

**Documentação completa:** [Experimento 02 — Autenticação web no DVWA](experimentos/02-dvwa-bruteforce.md).

### Etapa 6 — Análise de requisições HTTP

Utilizei as ferramentas de desenvolvedor do Firefox para observar uma requisição GET enviada pelo formulário Brute Force.

Posteriormente, utilizei comandos cURL para consultar respostas HTTP, identificar redirecionamentos e inspecionar o conteúdo HTML da página inicial de login.

Com o grep, localizei os campos `username`, `password` e `Login`.

Aprendi que uma resposta HTTP `200 OK` não significa necessariamente que a autenticação foi aceita. O código indica que o servidor respondeu à requisição.

Também observei que o uso de parâmetros de URL para transmitir credenciais pode provocar exposição de informações sensíveis.

**Documentação completa:** [Experimento 03 — Análise de requisições HTTP](experimentos/03-dvwa-http.md).

### Etapa 7 — Aprendizados durante a execução

Durante os experimentos, identifiquei e corrigi erros de sintaxe nos comandos.

Entre os principais aprendizados estão:

- A utilização de `>` para redirecionar a saída de um comando para um arquivo.
- A diferença entre as opções `-p` e `-P` no Medusa.
- A utilização de `-M` para selecionar o módulo de autenticação do Medusa.
- A utilização do Nmap para identificar portas e serviços.
- A diferença entre os métodos HTTP GET e POST.
- A interpretação dos códigos HTTP `200 OK` e `302 Found`.
- A utilização do cURL para consultar respostas HTTP.
- A utilização do grep para filtrar informações no terminal.
- A identificação de parâmetros e campos de formulários HTML.
- A importância de interpretar mensagens de erro e resultados das ferramentas.
- A necessidade de executar testes de maneira controlada, autorizada e documentada.

Também passei a utilizar o editor Mousepad para organizar anotações e comandos, facilitando a revisão dos conteúdos estudados.

## Recomendações de segurança

Os experimentos reforçam a importância das seguintes medidas:

### Proteção de credenciais

- Eliminar credenciais padrão em ambientes de produção.
- Utilizar senhas fortes e exclusivas.
- Aplicar autenticação multifator quando apropriado.
- Evitar a transmissão de credenciais por parâmetros de URL.

### Proteção dos mecanismos de autenticação

- Implementar limitação de tentativas de autenticação.
- Monitorar tentativas malsucedidas e comportamentos suspeitos.
- Evitar mensagens de erro que revelem informações desnecessárias sobre contas.
- Aplicar controles de acesso adequados.

### Proteção da comunicação e dos serviços

- Utilizar HTTPS para proteger dados transmitidos por aplicações web.
- Priorizar protocolos seguros, como SFTP ou FTPS, em vez de FTP sem criptografia.
- Manter serviços e aplicações atualizados.
- Realizar auditorias de segurança periódicas e autorizadas.

Essas recomendações representam medidas preventivas identificadas durante o estudo, não uma comprovação de que os controles foram implementados no laboratório.

## Boas práticas e segurança

Todos os testes são realizados exclusivamente em ambientes próprios ou autorizados, sem utilização de credenciais reais de terceiros ou exposição de sistemas de produção.

As ferramentas e os procedimentos apresentados possuem finalidade educacional e de avaliação defensiva.

As evidências publicadas são referentes ao laboratório e não contêm credenciais reais de usuários ou organizações.

## Conclusão

Os três experimentos realizados permitiram compreender diferentes aspectos da segurança de autenticação e das aplicações web.

O primeiro experimento demonstrou como credenciais previsíveis podem ser identificadas em um serviço FTP vulnerável.

O segundo permitiu observar o comportamento de um formulário web diante de tentativas manuais de autenticação válidas e inválidas.

O terceiro aprofundou a compreensão sobre requisições HTTP, redirecionamentos, parâmetros de formulários e possíveis riscos de exposição de credenciais.

Além do aprendizado técnico, o projeto contribuiu para desenvolver habilidades de documentação, interpretação de resultados, identificação de riscos e elaboração de recomendações de segurança.

A continuidade do laboratório permitirá aprofundar os conhecimentos sobre testes automatizados de autenticação, medidas de proteção e análise de riscos em ambientes controlados.
O quarto experimento permitiu aplicar o Hydra na automação de um teste de autenticação web, utilizando uma credencial conhecida em ambiente controlado. Durante sua execução, foi necessário consultar a documentação da ferramenta, corrigir erros de sintaxe e interpretar o resultado apresentado.

Com os quatro experimentos, o projeto reúne conhecimentos sobre identificação de serviços, auditoria de credenciais, autenticação web, comunicação HTTP e automação de testes, relacionando os resultados às práticas de prevenção e gestão de riscos.

*Projeto em desenvolvimento como parte do desafio de cibersegurança da DIO.*
