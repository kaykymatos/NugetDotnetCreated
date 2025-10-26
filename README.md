# DefaultReturn.Template

**Template C# para projetos web com configuração de SQL Server, Docker e OpenAPI.**  

Autor: Kayky Matos  
Classificações: C#, SQL Server, Backend  

Este template permite criar rapidamente um projeto C# configurado com:

- .NET 9.0  
- Estrutura de pastas organizada com todos os arquivos `.cs` e subpastas preservados  
- Conexão com SQL Server configurável via parâmetros  
- Dockerfile pronto para containers Linux  
- Arquivos `.http` para testes de API  
- Template pronto para ser publicado no NuGet  

---

## Arquivos principais

Os arquivos mais importantes do template estão dentro do projeto e devem ser revisados para entender o funcionamento:

- `DefaultReturn.Template.csproj` → define os arquivos incluídos no pacote NuGet e configurações de build/pack.  
- `.template.config/template.json` → define os parâmetros do template, substituições de placeholders e comportamento do `dotnet new`.  
- `appsettings.json` → contém placeholders para conexão com o banco de dados que serão substituídos pelos parâmetros fornecidos.  

> Recomenda-se abrir e revisar esses arquivos para personalizações avançadas ou alterações de comportamento.

---

## Como instalar o template localmente
1. Navegue até a pasta que contém o template:

```bash
cd /caminho/para/DefaultReturn.Template

2. Digite dotnet pack para criar o pacote NuGet:
dotnet pack -o pack

3. Instale o template localmente com o comando:
dotnet new -i pack/DefaultReturn.Template.1.0.0.nupkg

4. Verifique a instalação com:
dotnet new --list

5. Crie um novo projeto usando o template:
dotnet new DefaultReturn.Template -o MeuProjetoWeb -n MeuProjetoWeb --sqlServerName meuServidor --sqlDatabase meuBanco --sqlUser meuUsuario --sqlPassword minhaSenha
```
| Parâmetro       | Descrição                              |
| --------------- | -------------------------------------- |
| `-o`            | Pasta de saída do projeto              |
| `--projectName` | Nome do projeto, solution e namespaces |
| `--dbServer`    | Nome ou IP do servidor SQL Server      |
| `--dbName`      | Nome do banco de dados                 |
| `--dbUser`      | Usuário do banco de dados              |
| `--dbPassword`  | Senha do usuário do banco              |

Você pode editar o .csproj e outros arquivos para personalizar ainda mais o template conforme suas necessidades.