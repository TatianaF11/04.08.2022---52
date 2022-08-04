{
    //Задача 52. Задайте двумерный массив из целых чисел. Найдите среднее арифметическое элементов в каждом столбце.
    //Например, задан массив:
    //1 4 7 2
    //5 9 2 3
    //8 4 2 4
    //Среднее арифметическое каждого столбца: 4,6; 5,6; 3,6; 3.
    Console.WriteLine("Введите количество строк");
    int m = Convert.ToInt32(Console.ReadLine());
    Console.WriteLine("Введите количество столбцов");
    int n = Convert.ToInt32(Console.ReadLine());
    int[,] Array = new int[m,n];
    CreateIntArray(Array);
    PrintIntArray(Array); 
    AverageArray(Array);
    Console.WriteLine();
    Console.WriteLine("Среднее арифметическое элементов в каждом столбце");
    PrintArray(AverageArray(Array));
}

double[] AverageArray(int[,] arr)
{
    int m = arr.GetLength(0);
    int n = arr.GetLength(1);
    double[] arr2 = new double[n];
    double sum = 0;
    int index = 0;

    for (int i = 0; i < n; i++)
    {
        sum = 0;
        for (int j = 0; j < m; j++)
        {
            sum += arr[j,i];
        }
        arr2[index] = Math.Round(sum/m, 2);
        index++; 
    }
    return arr2;
}

void PrintArray(double[] arr)
{
    for (int i = 0; i < arr.Length; i++)
    {
        Console.Write(arr[i] + "\t");
    }
}
Zadacha52();
