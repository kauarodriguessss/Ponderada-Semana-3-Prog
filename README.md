# Ponderada-Semana-3-Prog
Atividade Ponderada da Semana 3 de Design

# Ponderada Semana 3: Desenvolvimento de banco de dados relacionais
**Aluno: Kauã Rodrigues dos Santos**  
**Turma 11 / Grupo 3**  

## Índice
1. [Introdução aos bancos de dados](#1-introdução-aos-bancos-de-dados)
2. [Implementação do banco de dados](#2-implementação-do-banco-de-dados)
3. [Discussão final](#3-discussão-final)
4. [Fontes consultadas](#4-fontes-consultadas)

## 1. Introdução aos bancos de dados
Bancos de dados são sistemas organizacionais vitais para o armazenamento e gestão de dados. No nosso projeto do segundo módulo no Inteli, estamos desenvolvendo uma plataforma web que utiliza um banco de dados relacional, um formato amplamente utilizado globalmente.  
O conceito de um modelo relacional envolve armazenar os dados em tabelas estruturadas com colunas e linhas, similares a uma planilha, onde cada linha representa um registro ou uma instância de um objeto.

### 1.1 Modelo de Entidade e Relacionamento
A modelagem de um banco de dados começa com a definição do modelo de entidade e relacionamento, seguido pela construção do modelo físico. Esta fase é crucial, pois define as tabelas a serem usadas, os dados a serem armazenados e como as tabelas interagem entre si.  
Em relação aos tipos de relacionamentos, o 1:n (um para muitos) indica que um registro em uma tabela pode estar ligado a vários registros em outra. O relacionamento n:n (muitos para muitos) sugere uma interação mútua entre muitos registros de duas tabelas diferentes.

#### 1.1.1 Aplicação do Modelo no Projeto Atual
Neste projeto, estamos criando uma plataforma para facilitar o engajamento entre voluntários e ONGs. Com base nos requisitos dos nossos parceiros, identificamos alguns relacionamentos essenciais. Por exemplo, é necessário uma tabela para usuários e outra para ações sociais, configurando um típico relacionamento n:n.

#### 1.1.2 Desafios dos Relacionamentos n:n
O grande desafio dos relacionamentos n:n é o potencial crescimento exponencial das tabelas se conectadas diretamente. Para contornar isso, empregamos uma técnica de normalização criando uma tabela intermediária, chamada "usuários_por_acao".

## 2. Implementação do Banco de Dados
**Figura 1 - Estrutura do Banco de Dados**  
![image](https://github.com/kauarodriguessss/Ponderada-Semana-3-Prog/assets/159058128/23285f75-7d15-49bf-9105-bb7d04c5a179)
**Fonte: Produção própria (2024)**  

### 2.1 Estrutura das Tabelas
Inicialmente, projetamos cinco tabelas principais para atender às necessidades dos parceiros:  
- **usuarios**: Armazena dados de usuários da plataforma.  
- **acoes**: Registra informações sobre cada ação social disponível.  
- **acao_realizada**: Registra quais ações um usuário participou, incluindo anos e horas dedicadas.  
- **convite_para_projeto**: Permite que usuários convidem outros para participar de ações.  
- **usuario_por_acao**: A tabela de normalização que relaciona usuários a ações.

### 2.2 Relacionamentos
A principal relação n:n é gerenciada pela tabela "usuario_por_acao". A tabela "convite_para_projeto" utiliza três chaves estrangeiras para vincular usuários a ações específicas, e a "acao_realizada" segue o modelo 1:n, permitindo que um usuário registre múltiplas ações.

## 3. Discussão Final
Para uma visão detalhada das tabelas e relacionamentos, consulte o arquivo .xml no repositório, que pode ser visualizado no SQL Designer através da importação do conteúdo XML.

## 4. Fontes Consultadas:
- HARRINGTON, J. L. Design e implementação de bancos de dados relacionais: explicação clara. Amsterdam; Boston: Morgan Kaufmann/Elsevier, 2009.
