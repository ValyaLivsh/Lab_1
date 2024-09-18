# Задание 1

'''
using System;
namespace lab1
{
    class lab1
    {
       static void Main(string[] args)
       {
            Console.WriteLine($"byte: min = {byte.MinValue}, max = {byte.MaxValue}");
            Console.WriteLine($"sbyte: min = {sbyte.MinValue}, max = {sbyte.MaxValue}");
            Console.WriteLine($"short: min = {short.MinValue}, max = {short.MaxValue}");
            Console.WriteLine($"ushort: min = {ushort.MinValue}, max = {ushort.MaxValue}");
            Console.WriteLine($"int: min = {int.MinValue}, max = {int.MaxValue}");
            Console.WriteLine($"uint: min = {uint.MinValue}, max = {uint.MaxValue}");
            Console.WriteLine($"long: min = {long.MinValue}, max = {long.MaxValue}");
            Console.WriteLine($"ulong: min = {ulong.MinValue}, max = {ulong.MaxValue}");
            Console.WriteLine($"float: min = {float.MinValue}, max = {float.MaxValue}");
            Console.WriteLine($"double: min = {double.MinValue}, max = {double.MaxValue}");
            Console.WriteLine($"decimal: min = {decimal.MinValue}, max = {decimal.MaxValue}");
            Console.WriteLine($"bool: true / false");
            Console.WriteLine($"char: min = {char.MinValue}, max = {char.MaxValue}");
            Console.WriteLine($"DateTime: min = {DateTime.MinValue}, max = {DateTime.MaxValue}");
            Console.WriteLine($"TimeSpan: min = {TimeSpan.MinValue}, max = {TimeSpan.MaxValue}");
       }
    }
}
'''

Вывод программы 
![image](https://github.com/user-attachments/assets/a8c0e096-aded-4b17-abb7-37f976789a12)
# Задание 2

'''
using System;
using System.Drawing;
using System.Runtime.InteropServices;

namespace lab1_2
{
    class Rectangle
    {
        private double sideA;
        private double sideB;

        public Rectangle(double sideA, double sideB)
        {
            this.sideA = sideA;
            this.sideB = sideB;
        }
        private double CalculateArea()
        { return sideA * sideB; }

        private double CalculatePerimeter()
        { return (sideA + sideB) * 2; }

        public double Area
        { get { return CalculateArea(); } }

        public double Perimeter
        { get { return CalculatePerimeter(); } }
    }

    class Prog
    {
        static void Main()
        {
            double a = double.Parse(Console.ReadLine());
            double b = double.Parse(Console.ReadLine());
            Rectangle rect = new Rectangle(a, b);
            Console.WriteLine($"Площадь прямоугольника: {rect.Area}");
            Console.WriteLine($"Периметр прямоугольника: {rect.Perimeter}");
        }
    }
}
'''
Вывод программы
![image](https://github.com/user-attachments/assets/a07c4868-287d-429a-9229-328e30288698)
# Задание 3

'''
using System;
using System.Numerics;
using System.Windows;
using System.Reflection.Metadata;
using System.Xml.Linq;

namespace lab1_3
{
    class Point
    {
        private int x, y;
        public int X { get { return x; } }
        public int Y { get { return y; } }
        public Point(int x, int y) { this.x = x; this.y = y;}
    }

    class Figure
    {
        private Point[] Points;
        private string name;
        public Figure(params Point[] points)
        {
            int k = points.Length;
            Points = new Point[k];
            for (int i = 0; i < k; i++) { Points[i] = points[i]; }
        }
        public string Name
        {
            get { return name; }
            set { name = value; }
        }
        public double LengthSide(Point p1, Point p2)
        {
            int dx = p1.X - p2.X;
            int dy = p1.Y - p2.Y;
            return Math.Sqrt(dx * dx + dy * dy);
        }
        public void PerimeterCalculator()
        {
            double sum = 0;
            for (int i = 0; i < Points.Length - 1; i++)
            {
                sum += LengthSide(Points[i], Points[i + 1]);
            }
            sum += LengthSide(Points[Points.Length - 1], Points[0]);
            Console.WriteLine($"Название фигуры: {name}");
            Console.WriteLine($"Периметр: {sum}");
        }
    }
    class Prog
    {
        static void Main(string[] args)
        {
            Point p1 = new Point(0, 0);
            Point p2 = new Point(0, 5);
            Point p3 = new Point(5, 5);
            Point p4 = new Point(5, 0);

            Figure rectangle = new Figure(p1, p2, p3, p4);  
            rectangle.Name = "rectangle";  
            rectangle.PerimeterCalculator();   
        }
    }
}
'''
Вывод программы
![image](https://github.com/user-attachments/assets/ab0320de-f48c-40d0-ac9e-0b8687493350)
