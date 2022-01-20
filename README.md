using System;

namespace DIO.Series
{
    class Program
    {
        static SerieRepositorio repositorio = new SerieRepositorio();
        static void Main(string[] args)
        {
            string opcaoUsuario = obterOpcaoUsuario();

            while (opcaoUsuario.ToUpper() != "X")
            {
                switch (opcaoUsuario)
                {
                    case "1":
                       ListarSeries();
                       break;
                    case "2":
                        InserirSerie():
                        break;
                    case "3":
                        AtualizarSerie():
                        break;
                    case "4":
                        ExcluirSerie():
                        break;
                    case "5":
                        VisualizarSerie():
                        break;
                    case "C":
                        Console.Clear();
                        break;
                    default:
                        throw new ArgumentOutOfRangeException():
                }
                opcaoUsuario = obterOpcaoUsuario();            
            }           

            Console.WriteLine("Obrigado por utilizar nossos serviços.");
            Console.ReadLine():            
        }
    private static void ListarSeries()
    {
        Console.WriteLine("Listar séries");

        var lista = repositorio.Lista();

        if (lista.count -- 0)
        {
            Console.WriteLine("Nenhuma série cadastrada.");
            return;
        }
        foreach (var serie in lista)
        {
            Console.WriteLine("#ID {0}: - {1}, serie.retornaId(), serie.retornaTitulo());
        }
    }  
    private static void InserirSerie()
    {
        Console.WriteLine("Inserir nova série");

        //https://docs.microsoft.com/pt-br/dotnet/api/system.enum.getvalues?viewnetcore-3.1
        //https://docs.microsoft.com/pt-br/dotnet/api/system.enum.getname?viewnetcore-3.1
    foreach (int i Enum.GetValues (typeof (Genero)));
    {
       Console.WritLine("{0}-{1}", i, Enum.GetName(typeof(Genero), i)); 
    }
    Console.Write("Digite o gênero entre as opções acima:");
    int entradaGenero = int.Parse(Console.ReadLine());
    Console.Write("Digite o título da série:");
    string entradaTitulo = Console.ReadLine();
    Console.Write("Digite a descrição da série:");
    string entradaDescrição = Console.ReadLine();
    Serie novaSerie = new Serie(Id: ((byte)SerieRepositorio.ProximoId(). 
                                genero: (Genero)entradaGenero,
                                título: entradaTitulo,
                                Ano: entradaAno,
                                descricao: entradaDescricao);
    repositorio.Insere(NovaSerie);

    private static string ObterOpcaoUsuario()
    {
        Console.WriteLine();
        Console.WriteLine("DIO Séries a seu dispor!");
        Console.WriteLine("Informe a opção desejada:");

        Console.WriteLine("1 - Listar séries");
        Console.WriteLine("2 - Inserir nova série");
        Console.WriteLine("3 - Atualizar nova série");
        Console.WriteLine("4 - Exclui série");
        Console.WriteLine("5 - Visualizar série");
        Console.WriteLine("C - Limpar Tela");
        Console.WriteLine("X - Sair");
        Console.WriteLine();

        string opcaoUsuario = Console.ReadLine() . ToUpper();
        Console.WriteLine();
        return opcaoUsuario;
        }
    }
}
