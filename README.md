# Pr_2
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace PR22
{
    enum days
    {
        Monday = 1,
        Tuesday,
        Wednesday,
        Thursday,
        Friday,
        Saturday,
        Sunday
    }
    enum sim
    {
        fitnessstation = 5,
        blockframe = 5,
        Smithmachine = 4,
        powertrainer = 6
    }


    class club
    {
        public string nameclub = "BodyBould";
        public string adress = "Пушкина 30";
        public string work = "5.00 - 10.00";
    }
    class gym : club
    {
        public string nameg;
        public int width;
        public int length;
        public gym(string n, int a, int b) { nameg = n; width = a; length = b; } // конструктор
        public virtual void GetInfo1()
        {
            Console.WriteLine($"Название: {nameclub},  адресс: {adress} Часы работы: {work}");
            Console.WriteLine("Залы:");
            Console.WriteLine($"Название зала: {nameg}");
        }

    }
    class instructor
    {
        public string name;
        public int age;

        public instructor(string n, int a) { name = n; age = a; } // конструктор
        public void GetInfo()
        {
            Console.WriteLine($"Имя: {name} Возраст: {age}");
        }

    }
    class visitors

    {
        public string name;
        public int age;
        public int vis;

        public visitors(string n, int a, int v) { name = n; age = a; vis = v; } // конструктор
        public void GetInfo()
        {
            Console.WriteLine($"Имя: {name} Возраст: {age} посещений: {vis} ");
        }

    }
    enum elit
    {
        Elit,
        noElit
    }
    interface Ivisits
    {

        void visits();

    }


    class Program
    {

        static void Main(string[] args)

        {
            //залы-------------------------------------------------------
            gym sec = new gym("first", 250, 250);
            sec.GetInfo1();
            //залы-------------------------------------------------------
            //тренажеры-------------------------------------------------------
            Console.WriteLine("");
            Console.WriteLine("Кол-во тренажеров:");
            foreach (var value in Enum.GetValues(typeof(sim)))
            {
                Console.WriteLine("{1} Количество: {0}",
                                  (int)value, ((sim)value));
            }
            // тренажеры через класс-------------------------------------------------------
            Console.WriteLine("");
            // посетители----------------------------------------------------------
            Console.WriteLine("Посетители:");

            visitors sam = new visitors("Sam", 20, 5);
            visitors tom = new visitors("Tom", 20, 20);
            visitors john = new visitors("John", 15, 26);

            sam.GetInfo();
            tom.GetInfo();
            john.GetInfo();
            // посетители-------------------------------------------------------      
            //Дни недели-------------------------------------------------------
            Console.WriteLine("");
            Console.WriteLine("Дни недели:");
            foreach (var value in Enum.GetValues(typeof(days)))
            {
                Console.WriteLine("{1}  - {0}",
                                  (int)value, ((days)value));
            }
            //Дни недели-------------------------------------------------------
            //инструктора-------------------------------------------------------
            Console.WriteLine("Введите номер дня недели");
            int day = Convert.ToInt32(Console.ReadLine());
            instructor clark = new instructor("Clark", 25);
            instructor petr = new instructor("Petr", 25);
            Console.WriteLine("Интсруктора работающие в этот день недели:");

            if (day > 0 && day < 5)
            {
                clark.GetInfo();
            }
            else
            {
                if (day > 4 && day < 8)
                {
                    petr.GetInfo();
                }
                else
                {
                    Console.WriteLine("Некорректный ввод дня недели");
                }
            }
            //инструктора-------------------------------------------------------



            Console.ReadKey();
        }
    }
}
