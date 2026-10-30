# Laboratório de Cibersegurança — Kali Linux e Medusa

## Sobre o projeto

Este repositório documenta meu aprendizado no desafio prático de cibersegurança da **Digital Innovation One (DIO)**, utilizando Kali Linux, Medusa e ambientes vulneráveis para compreender ataques de força bruta e medidas de prevenção.

O projeto está sendo desenvolvido em um ambiente virtual controlado, com máquinas destinadas exclusivamente a testes educacionais.

Além da execução dos experimentos, o objetivo é registrar os comandos utilizados, compreender seus parâmetros, interpretar resultados e identificar medidas de mitigação.

## Objetivos

- Aprender os fundamentos de autenticação e ataques de força bruta.
- Utilizar ferramentas de segurança em ambientes controlados.
- Compreender os conceitos de enumeração e identificação de serviços.
- Identificar riscos relacionados a credenciais fracas ou previsíveis.
- Documentar experimentos e evidências técnicas.
- Desenvolver conhecimentos práticos de cibersegurança e gestão de riscos.

## Ambiente do laboratório

| Componente | Configuração |
|---|---|
| Sistema de testes | Kali Linux 2026.3 |
| Máquina vulnerável | Metasploitable 2 |
| IP do Kali Linux | 10.0.0.9 |
| IP do Metasploitable 2 | 10.0.0.10 |
| Rede | Ambiente virtual privado de laboratório |
| Ferramentas | Nmap e Medusa 2.3 |
| Acesso | Interface gráfica remota |

Os endereços apresentados são privados e pertencem exclusivamente ao ambiente didático.

## Etapas do projeto

- [x] Criar repositório no GitHub.
- [x] Verificar a configuração do Kali Linux.
- [x] Confirmar a instalação do Medusa.
- [x] Verificar a conectividade entre as máquinas do laboratório.
- [x] Identificar o serviço FTP utilizando Nmap.
- [x] Criar uma wordlist simples para testes.
- [x] Executar o primeiro teste controlado com Medusa.
- [x] Analisar o resultado e identificar medidas de mitigação.
- [ ] Adicionar capturas de tela dos experimentos.
- [ ] Realizar os próximos cenários práticos, conforme disponibilidade do laboratório.
- [ ] Finalizar a documentação e entregar o projeto na DIO.

## Experimentos realizados

Este projeto reúne experimentos práticos de cibersegurança executados em um laboratório virtual controlado, utilizando Kali Linux e Metasploitable 2.

| Experimento | Ferramentas | Resultado |
|---|---|---|
| [01 — Auditoria de autenticação FTP](experimentos/01-ftp-medusa.md) | Nmap e Medusa | Identificação de credencial válida em serviço FTP vulnerável |
| [02 — Análise de autenticação web no DVWA](experimentos/02-dvwa-bruteforce.md) | Kali Linux, Firefox e DVWA | Comparação entre tentativas manuais de autenticação válidas e inválidas |

### Experimento 01 — Autenticação FTP

Foi realizada a identificação do serviço FTP na porta 21/TCP e uma simulação controlada de tentativas de autenticação com o Medusa.

**Resultado:** uma credencial de laboratório foi identificada, demonstrando os riscos associados ao uso de senhas previsíveis.

[Consultar documentação e evidências](experimentos/01-ftp-medusa.md)

### Experimento 02 — Autenticação web no DVWA

Foi utilizada a aplicação DVWA, configurada no nível de segurança `low`, para observar o comportamento de um formulário web diante de credenciais válidas e inválidas.

**Resultado:** foram documentadas as respostas da aplicação durante testes manuais de autenticação.

[Consultar documentação e evidências](experimentos/02-dvwa-bruteforce.md)

### Experimento 03 — Análise de requisições HTTP no DVWA

Foi realizada uma análise das requisições e respostas HTTP utilizando Firefox Developer Tools, cURL e grep, em ambiente de laboratório autorizado.

O experimento permitiu identificar parâmetros de formulários HTML, interpretar códigos de resposta HTTP (`200 OK` e `302 Found`) e compreender os riscos associados à transmissão de credenciais por parâmetros de URL.

**Resultado:** identificação do funcionamento das requisições HTTP, dos redirecionamentos e dos campos de autenticação.

[Consultar documentação e evidências](experimentos/03-dvwa-http.md)

### Próximas atividades

- [x] Criar o repositório e organizar a documentação.
- [x] Configurar e validar o ambiente de laboratório.
- [x] Realizar auditoria de autenticação FTP com Medusa.
- [x] Documentar testes manuais de autenticação no DVWA.
- [ ] Executar teste automatizado no formulário web do DVWA.
- [ ] Estudar password spraying em SMB no ambiente autorizado.
- [ ] Consolidar recomendações de segurança.
- [ ] Finalizar a documentação e entregar o projeto na DIO.

Os procedimentos, resultados e evidências estão organizados individualmente na pasta `experimentos`, com as capturas de tela armazenadas na pasta `images`.

## Diário de aprendizagem

### Etapa 1 — Organização do projeto

Criei um repositório público no GitHub para registrar as atividades práticas, os conceitos estudados e as evidências obtidas durante o curso.

Optei por manter um documento individual para cada experimento, facilitando a organização e a consulta posterior.

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

### Etapa 5 — Aprendizados durante a execução

Durante o laboratório, identifiquei e corrigi erros de sintaxe nos comandos.

Entre os aprendizados estão:

- A utilização de `>` para redirecionar a saída de um comando para um arquivo.
- A diferença entre as opções `-p` e `-P` no Medusa.
- A utilização de `-M` para selecionar o módulo de autenticação.
- A interpretação das mensagens de erro e dos resultados das ferramentas.
- A importância de executar testes de maneira controlada e documentada.

Também passei a utilizar o editor Mousepad para organizar anotações e comandos, facilitando a revisão dos conteúdos estudados.

## Recomendações de segurança

Os experimentos reforçam a importância de:

- Eliminar credenciais padrão em ambientes de produção.
- Utilizar senhas fortes e exclusivas.
- Aplicar políticas de limitação de tentativas de autenticação.
- Monitorar registros de acesso e tentativas malsucedidas.
- Utilizar protocolos criptografados para transferência de arquivos.
- Realizar auditorias de segurança periódicas e autorizadas.

## Boas práticas e segurança

Todos os testes são realizados exclusivamente em ambientes próprios ou autorizados, sem utilização de credenciais reais de terceiros ou exposição de sistemas de produção.

As ferramentas e os procedimentos apresentados possuem finalidade educacional e de avaliação defensiva.

## Conclusão

O primeiro experimento demonstrou, na prática, como uma ferramenta de auditoria de autenticação pode identificar credenciais previsíveis em um ambiente vulnerável.

A continuidade do projeto permitirá aprofundar conhecimentos sobre autenticação, identificação de riscos, medidas de proteção e documentação técnica.

*Projeto em desenvolvimento como parte do desafio de cibersegurança da DIO.*
