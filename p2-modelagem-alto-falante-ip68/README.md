# Modelagem SysML: Alto-Falante Bluetooth IP68

Este projeto documenta a arquitetura e o comportamento de um produto embarcado: um alto-falante portátil (caixa de som) com conectividade Bluetooth 5.0 e certificação de resistência IP68 (à prova de poeira e submersão).

## Objetivo da Modelagem

O foco da modelagem foi detalhar a interação contínua entre os subsistemas de Hardware (I/O, conectividade, bateria) e Software (Firmware de controle), garantindo que os requisitos de usabilidade, eficiência energética e segurança física fossem atendidos.

## Fluxos e Máquinas de Estado (SysML)

A modelagem SysML descreve os seguintes fluxos críticos de operação:

* **Ciclo de Vida da Conexão Bluetooth:** Máquina de estados priorizando a reconexão automática (30 segundos) antes de transitar para o modo de pareamento.
* **Gerenciamento de Energia e Segurança:** Monitoramento contínuo da bateria de Li-ion, com alertas de nível crítico (<15%) e desligamento seguro (<5%). Inclui a lógica de validação de tensão e temperatura durante a carga via USB-C.
* **Lógica de Auto-Shutdown:** Temporizador de inatividade que corta a alimentação após 15 minutos sem conexão ou áudio, garantindo a autonomia mínima de 10 horas.
* **Integridade Física (Certificação IP68):** Modelagem dos estados da porta de vedação USB ("Vedado", "Conectado" e "Exposto"), mapeando os riscos de falha crítica de hardware em caso de submersão incorreta.
* **Feedback Visual (Interface):** Padronização das respostas do sistema através de um LED RGB multifuncional (ex: Azul Piscando para pareamento, Vermelho para bateria fraca).

## Conteúdo da Pasta

* `/diagrama-screenshots`: Imagens exportadas dos diagramas SysML da máquina de estados e arquitetura.
* `documento-contexto.pdf`: Documento de visão geral do sistema, detalhando o hardware, o firmware e o comportamento esperado.
* `projeto-alto-falante.vpp`: Arquivo fonte do projeto para ser aberto no Visual Paradigm.
