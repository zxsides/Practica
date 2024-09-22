public partial class MainWindow : Window
{
public List<Product> Products { get; set; }

public MainWindow()
{
InitializeComponent();
Products = new List<Product>();
ProductsDataGrid.ItemsSource = Products;
}

private void AddProductButton_Click(object sender, RoutedEventArgs e)
{
string productName = ProductNameTextBox.Text;
string productPrice = ProductPriceTextBox.Text;
string productQuantity = ProductQuantityTextBox.Text;


if (!int.TryParse(productQuantity, out int year) || year > 1990)
{
MessageBox.Show("Год выпуска не может быть старше 1990 года.", "Ошибка валидации", MessageBoxButton.OK, MessageBoxImage.Error);
return;
}


Products.Add(new Product
{
ProductName = productName,
ProductPrice = productPrice,
ProductQuantity = productQuantity,
});


ProductNameTextBox.Clear();
ProductPriceTextBox.Clear();
ProductQuantityTextBox.Clear();
}
}

public class Product
{
public string ProductName { get; set; }
public string ProductPrice { get; set; }
public string ProductQuantity { get; set; }
}
}

Белозеров А.А. 360гр
