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

Precisamos preencher o "AuthSecret" e o "BasePath", para isso, vamos fazer o seguinte: 

Em Realtime Database, vamos em Dados, copiamos o link que está e colamos em "BasePath" no nosso código do Visual Studio

![InkedScreenshot_6_LI](https://github.com/gustavo-cacador/poo2/assets/102495284/2a9304c0-b52c-4a80-9e8c-95c7f9296c9f)


E em seguida, criamos uma interface para interagir com o FireBase:

IFirebaseClient client;

Se estiver tudo ok, seu código estará assim:

using System;

using System.Collections.Generic;

using System.ComponentModel;

using System.Data;

using System.Drawing;

using System.Linq;

using System.Text;

using System.Threading.Tasks;

using System.Windows.Forms;

using FireSharp.Config;

using FireSharp.Interfaces;

using FireSharp.Response;

namespace Projeto_teste_git
{
    public partial class Form1 : Form
    {

        IFirebaseConfig config = new FirebaseConfig
        {
            AuthSecret = "eL7zyVVol0qh9StxyDU81NSQgr0YoqBGV0TQ7Nhu",
            BasePath = "https://projetoteste-e624c-default-rtdb.firebaseio.com/"
        };

        IFirebaseClient client;

        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }
    }
}
