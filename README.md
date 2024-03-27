# Projeto de conexão de Banco de Dados no Visual Studio usando FireBase

## Connecting to Firebase using Firesharp C# Application

O primeiro passo é entrar no site do FireBase (basta pesquisar FireBase no Google), crie uma conta ou use a própria conta do Google mesmo.

Em seguida clique em começar e adicione um projeto.

Insira um nome para o projeto e crie o seu projeto.

Com o projeto já criado vamos na aba de Criação (no canto esquerdo da tela) e escolhemos por Realtime Database.

Em Realtime Database clicamos em "Criar banco de dados", e para configurarmos nosso banco de dados escolhemos a opção "Estados Unidos (us-central1)", depois escolhemos a opção "Iniciar no modo teste" e pronto, está configurado nosso Banco de Dados e já podemos mexer.

Agora no Visual Studio, vamos criar um projeto:

Escolha pelo seguinte modelo: Aplicativo do Windows Forms (.NET Framework) C#, escolha um nome para seu projeto e crie.

Com nosso projeto criado, vamos na opção "Projeto" lá em cima do nosso programa e clicamos em "Gerenciar Pacotes do NuGet..." e lá pesquisamos por firesharp e escolhemos por "FireSharp.Serialization.JsonNet" e instalamos.

Depois de instalarmos essa extensão vamos no nosso código e "exportamos" três usings: 

using FireSharp.Config;
using FireSharp.Interfaces;
using FireSharp.Response;

Logo após isso, precisamos configurar a conexão com o Firebase, que vai ser dado por:

public partial class Form1 : Form
{

    IFirebaseConfig config = new FirebaseConfig
    {
        AuthSecret = "",
        BasePath = ""
    };

No nosso projeto do FireBase,
