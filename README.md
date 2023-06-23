# ARPA | AUTOMAÇÃO ROBÓTICA DE PROCESSOS ATIKS

## Automações de Tarefas

A **ATIKS** é uma empresa de Gestão de Custos de Telecomunicações e TI que tem em seus processos uma sequencias de tarefas manuais e repetitivas. O objetivo do projeto é automatizar parte significativa destes processos para melhoria de produtividade, ganho de gestão e possibilidade de maior controle.
O programa foi desenvolvido em Phyton e estruturado em 4 fases.

## Índice

1. [Descrição do Projeto](#1-descri%C3%A7%C3%A3o-do-projeto) <br>
  1.1 [Processo](#11-processo) <br>
  1.2 [Organização da Aplicação](#12-organiza%C3%A7%C3%A3o-da-aplica%C3%A7%C3%A3o) <br>
  1.3 [Portais das Operadoras](#13-portais-das-operadoras)
2. [Planejamento e Status](#2-planejamento-e-status)
3. [Funcionalidades](#3-funcionalidades-e-demonstra%C3%A7%C3%A3o-da-aplica%C3%A7%C3%A3o)
4. [Acesso ao Projeto](#4-acesso-ao-projeto)
5. [Tecnologias utilizadas](#5-tecnologias-utilizadas)
6. [Equipe do Projeto](#6-equipe-do-projeto)
7. [Licenças](#7-licen%C3%A7as)


## 1. Descrição do Projeto

Desenvolvimento realizado em Phyton. Primeira versão com software desktop que roda somente na máquina destinada para automação. O processo prevê interações manuais de um operador. Existe uma planilha de Setup.xlxs que contém as informações dos clientes e dos portais. O software carrega a lista de opções da tela principal de acordo com a configuração da planilha Setup.xlxs.

### 1.1 Processo

- Operador copia o mapa de faturas atualizado da pasta do cliente no Google Drive para a pasta local na máquina .\clientes\[cliente]\mapa_de_faturas\mapa.xlsx, onde o programa está instalado. O mapa não deve ser alterado na rede até que finalize a execução e volte a versão atualizada.
- Operador abre o programa RPA Atiks, seleciona o Cliente, Portal e Mês. Clica no botão Baixar.
- Programa verifica no mapa quais as faturas estão pendentes para o portal e mês selecionado.
- Programa abre o Portal da Operadora e realiza o login com informações de usuário e senha.
- Programa busca as faturas para baixar e realiza o download em pasta .\clientes\[cliente]\download.
- Programa renomeia o arquivo com o padrão de cada cliente e altera para pasta Renomeado. (Fase 2)
- Programa marca o mapa de faturas como Status Baixa = Concluído e Observações = "RPA" (Fase 2)
- Operador transfere os arquivos da pasta Renomeado para o Google Drive, na pasta correta de acordo com a organização atual.
- Operador transfere o mapa salvo e atualziado para a pasta do cliente no Google Drive.

### 1.2 Organização da Aplicação

O projeto está organizado em um único arquivo [main.py], em classes e funções, conforme segue:
  - class App(tk.Tk): cria a tela de acesso e configura tamanho dos frames
  - class Content_Frame(ttk.Frame): cria o frame de conteúdo, com os botões, listas e comandos. Todas as funções da baixa das faturas estão contidas nesta classe.
    - def frameNRC(self): função que verifica no mapa quais faturas estão pendentes.
    - def driverSetUp(self): configura o driver do chrome e acessa o portal. Configura a pasta de download.
    - def acceptAllCookies(self): se o portal tiver um comunicado de aceitar os cookies, esta função trata.
    - def login(self): realiza o login no portal
    - def download(self, nfaturas): baixa as faturas de acordo com a lista pendente.
  - class LogInfo_Frame(ttk.Frame): cria o frame de log do software.


### 1.3 Portais das Operadoras
- BillManager: portal com autenticação em 2 fatores | precisa de interação manual.
- Algar Telecom: 
- Meu Vivo Empresas:
- Oi Empresas:
- Claro Empresas:

## 2. Planejamento e Status

Primeira Versão (01/11/22) >> Entregue
- Versão desktop = roda somente na máquina destinada para automações
- Parte do processo manual
- Somente o Portal BillManager >> CAOA, Raízen, HIAE

Fase 2 (xx/xx/xx) >> Não Iniciado
- Integração com o Google Drive: ler o Mapa direto da pasta do cliente e transferir as faturas baixadas direto para a pasta
- Automatizar a execução do programa RPA: criar programa executável em outras máquinas | Automatizar download e upload do mapa do Google Driver. 
- Expansão para todos os clientes no BillManager 

Médio Prazo (xx/xx/xx) >> Não Iniciado
- Leitor do PDF para extrair informações da fatura e preencher o Mapa de Faturas
- RPA Portal Atiks: inserir as faturas no Portal > Converter > Subir

Longo Prazo (xx/xx/xx) >> Não Iniciado
- Interface Web = rodar de qualquer máquina (todos analistas tem acesso)
- Mapa de Faturas integrado com a ferramenta RPA


## 3. Funcionalidades e Demonstração da Aplicação


## 4. Acesso ao Projeto


## 5. Tecnologias utilizadas

O projeto utiliza Python junto com as seguintes bibliotecas:
- [Pandas](https://pandas.pydata.org/docs/): ler o mapa de faturas e selecionar as faturas pendentes | Ler o arquivo de Setup
- [Openpyxl](https://openpyxl.readthedocs.io/en/stable/): ler e escerver no arquivo do mapa de faturas
- [Tkinter](https://tkdocs.com/): criar a tela do programa
- [Selenium](https://www.selenium.dev/documentation/): automatiza funções do driver do navegador | simula um operador mexendo no navegador


## 6. Equipe do Projeto

Contatos: Alessandro Vasques (avasques@Atiks.com.br) e Valdir Justra (vjustra@Atiks.com.br).
Líder: Luis Henrique Figueira (lfigueira@Atiks.com.br).
Equipe de Desenvolvimento: Luis Henrique Figueira, Vitor Reis (vreis@Atiks.com.br) e Gabriel Lemos (glemos@Atiks.com.br).


## 7. Licenças

Nenhuma licença necessária até o momento.
