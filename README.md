# Deliverable_One
class Program
{
    static void Main()
    {
        // Initial stock and restock values
        int sodaStock = 100;
        int sodaRestock = 40;

        int chipsStock = 40;
        int chipsRestock = 20;

        int candyStock = 60;
        int candyRestock = 40;

        // Function to update stock and check for restock
        void UpdateStock(string itemName, ref int currentStock, int restockValue)
        {
            try
            {
                Console.Write($"How many {itemName}s have been sold today? {currentStock} in stock: ");
                int soldToday = int.Parse(Console.ReadLine());

                if (soldToday <= currentStock)
                {
                    int remainingStock = currentStock - soldToday;
                    Console.WriteLine($"Remaining {itemName}s in stock: {remainingStock}");

                    if (remainingStock <= restockValue)
                    {
                        Console.WriteLine($"Restock {itemName}s!");
                    }
                }
                else
                {
                    Console.WriteLine("Too high. Stock not adjusted.");
                }
            }
            catch (FormatException)
            {
                Console.WriteLine("Invalid input. Please enter a valid number.");
            }
        }

        // Update and check stock for each item
        UpdateStock("Soda", ref sodaStock, sodaRestock);
        UpdateStock("Chips", ref chipsStock, chipsRestock);
        UpdateStock("Candy", ref candyStock, candyRestock);
    }
}
