Итоговая проверочная работа


Блок схема




![diagram](https://user-images.githubusercontent.com/106191604/196396097-e022e72f-4156-4e1a-87c2-adce0b8b1936.png)


Сначала объявляем два массива. Потом метод, в котором цикл соразмерен длине массива, внутри цикла проверка условия ( <=3 ), если условия выполняется то  элемент первого массива заносится в count элемента второго массива. После присвоения увеличивается переменная count на 1 и возвращается к циклу for в котором i увеличивается на 1. И так проверяется до конца.









![image](https://user-images.githubusercontent.com/106191604/197210805-73e4f355-44e5-4837-90f8-2c653dad95bd.png)
![image](https://user-images.githubusercontent.com/106191604/197210846-3c51fd1f-fe0d-48a0-9292-e48b4d579663.png)




string[] array = new string[] {};

string fromUser = ReadInput("Введите команду: ");
switch (fromUser)
{
    case "1":
        array = new string[] { "Hello", "2", "world", ":-)" };
        break;
    case "2":
        array = new string[] { "1234", "1567", "-2", "computer science" };
        break;
    case "3":
        array = new string[] { "Russia", "Denmark", "Kazan" };
        break;
    default:
        Console.WriteLine($"{fromUser} - Такой команды нет");
        break;
}


int lenNewArray = 0;
for (int i = 0; i <= array.Length - 1; i++)
{
    if (array[i].Length <= 3) lenNewArray++;
}

string[] newArray = new string[lenNewArray];
int idx = 0;

for (int i = 0; i <= array.Length - 1; i++)
{
    if (array[i].Length <= 3)
    {
        newArray[idx] = array[i];
        idx++;
    }
}

PrintArray(array);
Console.Write("→ ");
PrintArray(newArray);

void Commands()
{
    Console.WriteLine();
    Console.WriteLine("СПИСОК КОМАНД:");
    Console.WriteLine("1 – использовать массив: [“Hello”, “2”, “world”, “:-)”]");
    Console.WriteLine("2 – использовать массив: [“1234”, “1567”, “-2”, “computer science”]");
    Console.WriteLine("3 – использовать массив: [“Russia”, “Denmark”, “Kazan”]");
    Console.WriteLine();
}


string ReadInput(string msg)
{
    Console.Write(msg);
    return Console.ReadLine();
}

void PrintArray(string[] array)
{
    Console.Write("[ ");
    for (int i = 0; i < array.Length; i++)
    {
        Console.Write($"“{array[i]}”, ");
    }
    Console.Write("] ");
}

