# API ScreenSound

**Descrição:**

Este repositório é uma extensão do projeto ScreenSound, iniciado em https://github.com/WesleySchuab/csharpWeb-screensound-curso1. Aqui, focamos no desenvolvimento da API RESTful para o sistema, permitindo a interação com os dados do banco de dados de forma mais flexível e escalável.

**Pré-requisitos:**

* Visual Studio 2022 ou superior
* .NET 7 SDK
* SQL Server Express LocalDB (geralmente instalado junto com o Visual Studio)
* Clonar o repositório https://github.com/WesleySchuab/csharpWeb-screensound-curso1

**Configuração do banco de dados:**

1. **Abra o projeto inicial:** Abra o projeto clonado do curso anterior no Visual Studio.
2. **Gerenciador de Pacotes NuGet:**
   * Abra o Console do Gerenciador de Pacotes.
   * Execute os seguintes comandos:
     ```powershell
     Add-Migration PreparandoBanco
     Update-Database
     ```
3. **Verificação:**
   Verifique a criação do banco de dados e das tabelas no Explorador de Objetos do SQL Server.

**Estrutura do projeto:**

* **Shared.Modelos:** Contém os modelos de dados utilizados em toda a aplicação.
* **Banco:** Contém a classe de contexto do Entity Framework e as configurações do banco de dados.
* **Migrations:** Contém as migrações para o banco de dados.
* **API:** Contém os controladores e os serviços da API RESTful.

**Criando a API:**

1. **Adicionar novo projeto:**
   * Adicione um novo projeto do tipo "Biblioteca de Classes" ao seu solução.
   * Mova as pastas `Banco` e `Migrations` para o novo projeto.
2. **Referenciar o projeto de modelos:**
   * No projeto da API, adicione uma referência ao projeto `Shared.Modelos`.
3. **Criar controladores:**
   * Crie controladores para as diferentes entidades (artistas, álbuns, músicas).
   * Utilize atributos como `[HttpGet]`, `[HttpPost]`, etc. para definir as rotas e os métodos HTTP.
   * Utilize serviços para encapsular a lógica de negócios.

**Exemplo de controlador:**

```csharp
[ApiController]
[Route("api/[controller]")]
public class ArtistasController : ControllerBase
{
    private readonly ScreenSoundContext _context;

    public ArtistasController(ScreenSoundContext context)
    {
        _context = context;
    }

    [HttpGet]
    public ActionResult<IEnumerable<Artista>> GetArtistas()
    {
        return _context.Artistas.ToList();
    }
}


# Aqui está uma descrição mais informal onde narro o passo a passo do projeto.


Esse repositório é para continução do curso de persistencia no banco de dados do repositório: https://github.com/WesleySchuab/csharpWeb-screensound-curso1. Para seguir esse projeto precisa ter o Visual Studio e instalar os pacotes mencionados no repositório anterior. Caso não tenha o banco de dados na sua máquina após clonar esse execute os seguintes passos: Abra o projeto inicial no Visual Studio;

No menu superior, vá em Ferramentas, encontre a opção Gerenciador de Pacotes do NuGet e, em sequência, abra o Console do Gerenciador de Pacotes;

No console aberto digite o comando Add-Migrations PreparandoBanco para adicionar as alterações existentes no seu projeto;

Depois de finalizado o processo, ainda no console, digite Update-Database para atualizar o banco de dados com as alterações e informações mapeadas.

Finalizadas essas etapas você pode acessar o Pesquisador de Objetos do SQL Server para conferir se o banco e as tabelas foram criados corretamente.
após o commit: movendo a pasta modelo par ao projeto shared.Modelos 23f431ee26d8e4883af7a181ab8dd5762688c2b1. É Nescessário Referenciar o projeto de biblioteca no projeto console
Clicamos com o botão direito em "Dependências", depois clicamos em "Adicionar Referência de Projeto...". Na janela suspensa, escolhemos o ScreenSound.Shared.Modelos e confirmamos clicando em "OK". Agora o nosso projeto ScreenSound reconhece os modelos.
O nosso objetivo agora é também compartilhar o acesso aos dados em um novo tipo de projeto. Para isso, vamos adicionar um novo projeto de biblioteca de classes e levar para esse projeto tudo referente ao acesso aos dados, ou seja, a pasta Banco e a pasta Migrations.

