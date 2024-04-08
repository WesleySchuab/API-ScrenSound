# API-ScrenSound
O que que são APIS
https://aws.amazon.com/pt/what-is/api/

Esse repositório é para continução do curso de persistencia no banco de dados do repositório: https://github.com/WesleySchuab/csharpWeb-screensound-curso1. Para seguir esse projeto precisa ter o Visual Studio e instalar os pacotes mencionados no repositório anterior. Caso não tenha o banco de dados na sua máquina após clonar esse execute os seguintes passos: Abra o projeto inicial no Visual Studio;

No menu superior, vá em Ferramentas, encontre a opção Gerenciador de Pacotes do NuGet e, em sequência, abra o Console do Gerenciador de Pacotes;

No console aberto digite o comando Add-Migrations PreparandoBanco para adicionar as alterações existentes no seu projeto;

Depois de finalizado o processo, ainda no console, digite Update-Database para atualizar o banco de dados com as alterações e informações mapeadas.

Finalizadas essas etapas você pode acessar o Pesquisador de Objetos do SQL Server para conferir se o banco e as tabelas foram criados corretamente.
após o commit: movendo a pasta modelo par ao projeto shared.Modelos 23f431ee26d8e4883af7a181ab8dd5762688c2b1. É Nescessário Referenciar o projeto de biblioteca no projeto console
Clicamos com o botão direito em "Dependências", depois clicamos em "Adicionar Referência de Projeto...". Na janela suspensa, escolhemos o ScreenSound.Shared.Modelos e confirmamos clicando em "OK". Agora o nosso projeto ScreenSound reconhece os modelos.
O nosso objetivo agora é também compartilhar o acesso aos dados em um novo tipo de projeto. Para isso, vamos adicionar um novo projeto de biblioteca de classes e levar para esse projeto tudo referente ao acesso aos dados, ou seja, a pasta Banco e a pasta Migrations.

