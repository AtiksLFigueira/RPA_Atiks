# PAR | Programa de Automatizações RPA 

## Automações de Tarefas

A **ATIKS** é uma empresa de Gestão de Custos de Telecomunicações e TI que tem em seus processos uma sequencias de tarefas manuais. O objetivo do projeto é automatizar parte significativa destes processos para melhoria de produtividade, ganho de gestão e possibilidade de maior controle.
O programa foi desenvolvido em Phyton e estruturado em 4 diferentes fases, cada qual com seu prazo e escopo.

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

Desenvolvimento realizado em Phyton. Primeira versão com software desktop que roda somente na máquina destinada para automação.
O processo prevê interações manuais de um operador, conforme abaixo:

### 1.1 Processo

- Operador copiar o mapa de faturas atualizado da pasta do cliente no Google para a pasta local, onde o programa está instalado. O mapa não deve ser alterado até que finalize a execução.
- Operador abre o programa RPA Atiks no ícone, selecionar o Cliente, Portal e Mês. Clica no botão Baixar.
- Programa verifica no mapa quais as faturas estão pendentes para o Portal selecionado.
- Programa abre o Portal da Operadora e realiza login informações de usuário e senha. Cada Portal tem a sua particularidade.
- Programa busca as faturas para baixar e realiza o download em pasta Download pré-configurada.
- Programa renomeia o arquivo com o padrão RPA_Portal_NoFatura e altera para pasta Renomeado.
- Programa marca o mapa de faturas como Status Baixa = Concluído e Observações = "RPA"
- Operador seleciona outros cliente e outros portais caso necessário | Programa repete operações para opções selecionadas.
- Operador transfere os arquivos da pasta Renomeado para o Google Drive, na pasta correta de acordo com a organização atual.
- Operador transfere o mapa salvo e atualziado para a pasta do cliente no Google Drive.
- Operador fecha o programa.

### 1.2 Organização da Aplicação

O projeto está organizado em um único arquivo [main.py], em classes, conforme segue:
- App(tk.Tk): classe que cria a tela de acesso, interação e registro dos logs
  - class Content_Frame(ttk.Frame): classe que cria o frame de conteúdo, com os botões, listas e comandos
  - class LogInfo_Frame(ttk.Frame):
  - 
- def SearchList(cliente, portal, mes): lista os números de NRC que devem ser baixados do site

### 1.3 Portais das Operadoras
- Algar Telecom
- Meu Vivo Empresas
- BillManager
- Oi Empresas
- Claro Empresas
- Americanet

## 2. Planejamento e Status

Primeira Versão (01/11/22) >> Em desenvolvimento
- Versão desktop = roda somente na máquina destinada para automações
- Parte do processo manual

Curto Prazo (31/12/22) >> Não Iniciado
- Integração com o Google Drive: ler o Mapa direto da pasta do cliente e transferir as faturas baixadas direto para a pasta
- Automatizar a execução do programa RPA
- Expansão para todos os Portais disponíveis 

Médio Prazo (31/03/22) >> Não Iniciado
- Leitor do PDF para extrair informações da fatura e preencher o Mapa do Excel
- RPA Portal Atiks: inserir as faturas no Portal > Converter > Subir

Longo Prazo (30/06/23) >> Não Iniciado
- Interface Web = rodar de qualquer máquina (todos analistas tem acesso)
- Mapa de Faturas integrado com a ferramenta RPA


## 3. Funcionalidades e Demonstração da Aplicação


## 4. Acesso ao Projeto


## 5. Tecnologias utilizadas

O projeto utiliza Python junto com as seguintes bibliotecas:
- Pandas: 
- Openpyxl: 
- Tkinter: 
- Selenium:  


## 6. Equipe do Projeto

Contatos: Alessandro Vasques (avasques@Atiks.com.br) e Valdir Justra (vjustra@Atiks.com.br).
Líder: Luis Henrique Figueira (lfigueira@Atiks.com.br).
Equipe de Desenvolvimento: Luis Henrique Figueira, Vitor Reis (vreis@Atiks.com.br) e Gabriel Lemos (glemos@Atiks.com.br).


## 7. Licenças

Nenhuma licença necessária até o momento.
