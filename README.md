# .net14.09
using System;

namespace OOPExamples
{
    class Program
    {
        static void Main(string[] args)
        {
            // Gọi các phương thức
            bai1();
            bai2();
           / bai3();
        }

        // Bài 1: Kế thừa
        public static void bai1()
        {
            Car myCar = new Car
            {
                Brand = "Toyota",
                Year = 2020,
                NumberOfDoors = 4
            };

            Console.WriteLine($"Brand: {myCar.Brand}, Year: {myCar.Year}, Doors: {myCar.NumberOfDoors}");
            myCar.Start();
            myCar.Honk();
            myCar.Stop();
        }
        // Vehicle là lớp cha với các thuộc tính Brand và Year, và các phương thức Start() và Stop().
        // Car là lớp con kế thừa từ Vehicle và có thêm thuộc tính NumberOfDoors và phương thức Honk().
        
        // Bài 2: Đa hình
        public static void bai2()
        {
            Animal myDog = new Dog();
            Animal myCat = new Cat();

            myDog.MakeSound();
            myCat.MakeSound();

            MathOperations mathOps = new MathOperations();
            Console.WriteLine("Add(2, 3): " + mathOps.Add(2, 3));
            Console.WriteLine("Add(2, 3, 4): " + mathOps.Add(2, 3, 4));
        }
        //Animal là lớp cơ sở với phương thức MakeSound().
        //Dog và Cat kế thừa từ Animal và ghi đè phương thức MakeSound().
        //MathOperations có các phương thức Add được nạp chồng(overloading).
        
        // Bài 3: Kế thừa và Đa hình trong phát triển phần mềm
        public static void bai3()
        {
            // Ví dụ về kế thừa
            Car myCar = new Car
            {
                Brand = "Toyota",
                Year = 2020,
                NumberOfDoors = 4
            };

            Console.WriteLine($"Brand: {myCar.Brand}, Year: {myCar.Year}, Doors: {myCar.NumberOfDoors}");
            myCar.Start();
            myCar.Honk();
            myCar.Stop();

            // Ví dụ về đa hình
            Animal myDog = new Dog();
            Animal myCat = new Cat();

            myDog.MakeSound();
            myCat.MakeSound();

            MathOperations mathOps = new MathOperations();
            Console.WriteLine("Add(2, 3): " + mathOps.Add(2, 3));
            Console.WriteLine("Add(2, 3, 4): " + mathOps.Add(2, 3, 4));
        }

        // Lớp cha và lớp con (Kế thừa)
        public class Vehicle
        {
            public string Brand { get; set; }
            public int Year { get; set; }

            public void Start()
            {
                Console.WriteLine("Vehicle is starting.");
            }

            public void Stop()
            {
                Console.WriteLine("Vehicle is stopping.");
            }
        }

        public class Car : Vehicle
        {
            public int NumberOfDoors { get; set; }

            public void Honk()
            {
                Console.WriteLine("Car is honking.");
            }
        }

        // Đa hình (Phương thức ghi đè)
        public class Animal
        {
            public virtual void MakeSound()
            {
                Console.WriteLine("Animal makes a sound.");
            }
        }

        public class Dog : Animal
        {
            public override void MakeSound()
            {
                Console.WriteLine("Dog barks.");
            }
        }

        public class Cat : Animal
        {
            public override void MakeSound()
            {
                Console.WriteLine("Cat meows.");
            }
        }

        // Đa hình (Phương thức nạp chồng)
        public class MathOperations
        {
            public int Add(int a, int b)
            {
                return a + b;
            }

            public int Add(int a, int b, int c)
            {
                return a + b + c;
            }
        }
    }
}
