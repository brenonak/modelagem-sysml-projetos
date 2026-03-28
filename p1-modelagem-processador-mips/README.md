# Modelagem SysML: Processador MIPS Monociclo

Este projeto contém a especificação em SysML de um processador de 32 bits baseado na arquitetura MIPS. O sistema foi modelado com uma estrutura monociclo e organização de memória Harvard.

## Objetivo da Modelagem

O objetivo foi mapear e formalizar os requisitos e o comportamento de um conjunto reduzido de instruções RISC, integrando a Unidade de Processamento (UP), Unidade de Controle (UC) e as interfaces de I/O de um kit FPGA DE2-115.

## Diagramas Desenvolvidos (SysML)

A estrutura do modelo foi dividida em quatro áreas funcionais através de um **Diagrama de Pacotes** (Controle, Dados, Operações e I/O). Dentro de cada pacote, foram desenvolvidos:

* **Diagramas de Requisitos:** Formalização das especificações funcionais e de interface (ex: sinais da UC, armazenamento, operações suportadas).
* **Diagramas de Casos de Uso:** Mapeamento das interações entre componentes internos (Atores, como ULA e Memórias) e as funções do sistema.
* **Diagramas de Atividades:** Detalhamento do comportamento dinâmico e fluxos de trabalho, incluindo:
    * Lógica de seleção do próximo endereço do PC (Controle).
    * Processo de leitura da memória de dados para a instrução `Load Word` (Dados).
    * Interação com hardware externo e lógica de pausa (*stall*) para instrução de Input (I/O).
    * Execução de operações do Tipo-R na ULA (Operações).

## Conteúdo da Pasta

* `/diagrama-screenshots`: Imagens exportadas dos diagramas SysML.
* `descricao-sistema.pdf`: Documento detalhado com o contexto da arquitetura MIPS, datapath e formatos de instrução.
* `projeto-mips.vpp`: Arquivo fonte do projeto para ser aberto no Visual Paradigm.
