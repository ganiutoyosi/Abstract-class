# Abstract-class

class Program
    {
        static void Main(string[] args)
        {
            Shape[] shapes = new Shape[6]; // Creating an array of shapes
            shapes[0] = new Rectangle(5, 10); // Initalizing an array
            shapes[1] = new Triangle(15, 20);
            shapes[2] = new Circle(16);
            shapes[3] = new Rectangle(30, 40);
            shapes[4] = new Triangle(10, 5);
            shapes[5] = new Circle(6);


            double[] areas = new double[6]; // Creating an array for areas of each shape


            for(int i = 0; i < shapes.Length; i++)
            {
                areas[i] = shapes[i].CalculateSurface();
            }


            for (int i = 0; i < shapes.Length; i++) // Output areas
            {
                Console.WriteLine($"Area: {areas[i]}");
            }


            Console.ReadKey();
        }
    }
    public abstract class Shape
    {
        protected double width;
        protected double height;


        public Shape(double Width)
        {
            width = height = Width;
        }
        public Shape(double Width, double Height)
        {
            width = Width;
            height = Height;
        }
        public abstract double CalculateSurface();
    }


    public class Triangle : Shape
    {
        public Triangle(double Width, double Height) : base(Width, Height)
        {


        }
        public override double CalculateSurface()
        {
            return height * width / 2;
        }
    }


    public class Rectangle : Shape
    {
        public Rectangle(double Width, double Height) : base(Width, Height)
        {


        }
        public override double CalculateSurface()
        {
            return height * width;
        }
    }


    public class Circle : Shape
    {
        public Circle(double Radius) : base(Radius)
        {   


        }
        public override double CalculateSurface()
        {
            return Math.PI * Math.Pow(width, 2);
        }
    }
