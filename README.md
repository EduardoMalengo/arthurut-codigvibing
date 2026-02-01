# arthurut-codigvibing

using System;

enum Nivel { viado, gay, boiola }

class escolher
{
    static void Main(string[] args)
    {
        Random rng = new Random();
        Nivel NivelAtual = Nivel.viado;

        Console.WriteLine("Esolha o Nivel: ");
        Console.WriteLine("1 - Viado ");
        Console.WriteLine("2 - gay ");
        Console.WriteLine("3 - boiola: ");

        string EscolhaONivel = Console.ReadLine();
        string escolher;

        if (EscolhaONivel == "1") escolher = "viado";
        else if (EscolhaONivel == "2") escolher = "gay";
        else if (EscolhaONivel == "3") escolher = "boiola";
        else escolher = "Moreu";

        Console.WriteLine($"\n Você é um {escolher} !");
        Console.WriteLine("==AGORA SOU EU E VC MEU GOSTOSO==");

        while (true)
        {
            string caracteristica = "LGBT";
            if (NivelAtual == Nivel.gay) caracteristica = "PABLO VITAR";
            else if (NivelAtual == Nivel.boiola) caracteristica = "ANA CASTELLO";

            Console.WriteLine($"\n Você é um {NivelAtual} + ({caracteristica})! UIIIII");

            Console.WriteLine("ILUMINATION ROSA... ");
            Console.WriteLine("Ilumination Roxa... ");

            int chance = (NivelAtual == Nivel.viado) ? 30 :
                         (NivelAtual == Nivel.gay) ? 40 : 90;

            bool ViadoApareceu = rng.Next(0, 100) < chance;

            if (ViadoApareceu)
            {
                Console.WriteLine("O Viado apareceu! Cuidado! ");
                Console.WriteLine($"Escolha sua ação: ");
                Console.WriteLine($" 1 - Fugir para algum lugar do {escolher} ! ");
                Console.WriteLine($" 2 - Se esconda do Monstro em {escolher} !");

                string depois_de_escolher = Console.ReadLine();

                int dificuldade = (NivelAtual == Nivel.viado) ? 30 :
                                  (NivelAtual == Nivel.boiola) ? 60 : 70;

                bool sucesso = rng.Next(0, 100) > dificuldade;

                if (depois_de_escolher == "1")
                {
                    Console.WriteLine(sucesso
                       ? $"Sucesso, {escolher} escapou !"
                       : $"Você tentou mas... {escolher}, infelizmente o monstro te pegou ! FIM DE JOGO");
                    if (!sucesso) break;
                }
                else if (depois_de_escolher == "2")
                {
                    Console.WriteLine(sucesso
                        ? $"Sucesso ! {escolher}, o Boiola não te achou ! Ufa"
                        : $"A não! {escolher}, o monstro te pegou!");
                    if (!sucesso) break;
                }
                else
                {
                    Console.WriteLine("Você morreu pelo Boiola...");
                    break;
                }
            }
            else
            {
                Console.WriteLine("Ta safe irmão continue...");
            }

            if (NivelAtual == Nivel.viado)
            {
                NivelAtual = Nivel.gay;
                Console.WriteLine("Avançou para o Nivel gay");
            }
            else if (NivelAtual == Nivel.gay)
            {
                NivelAtual = Nivel.boiola;
                Console.WriteLine("Vc avançou de Nivel para o nivel boiola!");
            }
            else
            {
                Console.WriteLine("===\nParabens! Você Ganhou !===");
                break;
            }
        }

        Console.WriteLine("\n==Fim de Jogo===");
    }
}
