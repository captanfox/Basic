# Basic
Basic Calculator
using System;

namespace HelloWorldSample
{
    class program
    {
        private static string ChooseMethod()
        {            // Kullanıcıdan yapmasını istediğini sor
            Console.WriteLine("Listeden bir opsiyon seç.");
            Console.WriteLine("\ta - Toplama");
            Console.WriteLine("\ts - Çıkartma");
            Console.WriteLine("\tm - Çarpma");
            Console.WriteLine("\td - Bölme");
            Console.WriteLine("\tx - Çıkış");
            return Console.ReadLine();
        }
        static void Main(string[] args)
        {
            double num1 = 0;
            double num2 = 0;

            while (true)
            {
                var choosenMethod = ChooseMethod();
                if(choosenMethod == "x"){
                    break;
                }

                // Display title as the c# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("----------------------\n");

                while (true)
                {
                    // Ask user type first number
                    Console.WriteLine("Birinci sayı yaz ve Entera bas");
                    var num = Console.ReadLine();
                    if (!double.TryParse(num , out num1))
                    {
                        continue;
                    }
                    break;
                }

                while (true)
                {
                    // Ask user type first number
                    Console.WriteLine("Ikinci sayı yaz ve Entera bas");
                    var num = Console.ReadLine();
                    if (!double.TryParse(num , out num2))
                    {
                        continue;
                    }
                    break;
                }

                switch (choosenMethod)
                {
                    case "a":
                        Console.WriteLine($"Sonuç: {num1} Artı {num2}={num1 + num2}");
                        break;
                    case "s":
                        Console.WriteLine($"Sonuç: {num1} Eksi {num2}={num1 - num2}");
                        break;
                    case "m":
                        Console.WriteLine($"Sonuç: {num1} Çarpı {num2}={num1 * num2}");
                        break;
                    case "d":
                        Console.WriteLine($"Sonuç: {num1} Bölü {num2} ={num1 / num2}");
                        break;
                }

            }

            while (true)
            {
                Console.WriteLine("Çıkmak istiyorsan ESC ye bas");
                var escKey = Console.ReadKey();
                if (escKey.Key == ConsoleKey.Escape)
                {
                    break;
                }
            }
            Console.WriteLine("İyi gunler");
        }
    }
}
