# using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Лабораторная работа №4: Массивы и строки");
        Console.WriteLine("========================================");

        // Часть 1: Одномерные массивы
        Console.WriteLine("\nЧасть 1: Одномерные массивы");
        OneDimensionalArrayDemo();

        // Часть 2: Двумерные массивы
        Console.WriteLine("\nЧасть 2: Двумерные массивы");
        TwoDimensionalArrayDemo();

        // Часть 3: Строки
        Console.WriteLine("\nЧасть 3: Строки");
        StringOperationsDemo();
    }

    static void OneDimensionalArrayDemo()
    {
        int[] array = new int[10];
        Random random = new Random();

        // Заполнение массива случайными числами
        for (int i = 0; i < array.Length; i++)
        {
            array[i] = random.Next(1, 101);
        }

        // Вывод массива
        Console.WriteLine("Массив:");
        foreach (int num in array)
        {
            Console.Write(num + " ");
        }
        Console.WriteLine();

        // Вычисление характеристик массива
        int sum = 0;
        int max = array[0];
        int min = array[0];

        foreach (int num in array)
        {
            sum += num;
            if (num > max) max = num;
            if (num < min) min = num;
        }

        double average = (double)sum / array.Length;

        Console.WriteLine($"Сумма элементов: {sum}");
        Console.WriteLine($"Максимальный элемент: {max}");
        Console.WriteLine($"Минимальный элемент: {min}");
        Console.WriteLine($"Среднее арифметическое: {average:F2}");
    }

    static void TwoDimensionalArrayDemo()
    {
        int[,] matrix = new int[3, 3];
        Random random = new Random();

        // Заполнение матрицы
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                matrix[i, j] = random.Next(1, 10);
            }
        }

        // Вывод матрицы
        Console.WriteLine("Матрица 3x3:");
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 3; j++)
            {
                Console.Write(matrix[i, j] + " ");
            }
            Console.WriteLine();
        }

        // Сумма главной диагонали
        int diagonalSum = 0;
        for (int i = 0; i < 3; i++)
        {
            diagonalSum += matrix[i, i];
        }
        Console.WriteLine($"Сумма главной диагонали: {diagonalSum}");

        // Сумма элементов по строкам
        for (int i = 0; i < 3; i++)
        {
            int rowSum = 0;
            for (int j = 0; j < 3; j++)
            {
                rowSum += matrix[i, j];
            }
            Console.WriteLine($"Сумма строки {i + 1}: {rowSum}");
        }
    }

    static void StringOperationsDemo()
    {
        string text = "Программирование на C# — это интересно!";

        Console.WriteLine($"Исходный текст: {text}");

        // Подсчет слов
        string[] words = text.Split(new[] { ' ' }, StringSplitOptions.RemoveEmptyEntries);
        Console.WriteLine($"Количество слов: {words.Length}");

        // Замена пробелов
        string replacedText = text.Replace(' ', '-');
        Console.WriteLine($"Текст с заменой пробелов: {replacedText}");

        // Верхний регистр
        string upperText = text.ToUpper();
        Console.WriteLine($"Текст в верхнем регистре: {upperText}");

        // Поиск подстроки
        bool containsCSharp = text.Contains("C#");
        Console.WriteLine($"Содержит подстроку 'C#': {containsCSharp}");
    }
}
