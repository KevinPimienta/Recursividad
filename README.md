# Recursividad
Primera tarea U2
class Proarmas
	{

		public void ConFor()
		{
			Random ran = new Random();
			int pup = 6;
			int[] Vektor = new int[pup];

			for (int r = 0; r < pup; r++)
			{
				Console.WriteLine("Numeros:");
				Vektor[r] = ran.Next(2, 9);
				Console.WriteLine(Vektor[r]);
			}
			for (int r = 0; r < pup; r++)
			{
				Vektor[r] = Vektor[r] * r;
				Console.WriteLine("El factorial es: " + Vektor[r]);
			}
		}

		public int Factorial(int n)
		{

			if (n == 0)
			{
				return 1;
			}
			else
			{
				return n + Factorial(n - 1);
			}
		}
		static void Main(string[] args)
		{
			Proarmas ren = new Proarmas();
			Random run = new Random();
            int op = 0;
			while (op != 9)
			{
				Console.WriteLine("1.-Por for. ");
				Console.WriteLine("2.-Por recurcividad.");
				op = int.Parse(Console.ReadLine());
				Console.WriteLine();
				Console.Clear();
				switch (op)
				{
					case 1:
						TimeSpan stop;
						TimeSpan start = new TimeSpan(DateTime.Now.Ticks);
						ren.ConFor();
						stop = new TimeSpan(DateTime.Now.Ticks);
						Console.Write(stop.Subtract(start).TotalSeconds); Console.WriteLine(" Segundos ");
						break;
					case 2:
                        
						
						TimeSpan starte = new TimeSpan(DateTime.Now.Ticks);
                        int f = ren.Factorial(8);
						Console.WriteLine("El resultado es:" + f);
						stop = new TimeSpan(DateTime.Now.Ticks);
						Console.Write(stop.Subtract(start).TotalSeconds); Console.WriteLine(" Segundos ");
						break;
				}
			}
			Console.ReadKey();
		}
	}
