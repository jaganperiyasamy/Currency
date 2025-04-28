import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class CurrencyConverter {

    private static Map<String, Double> exchangeRates = new HashMap<>();

    // Initialize some sample exchange rates
    static {
        exchangeRates.put("USD", 1.0);       // Base currency USD
        exchangeRates.put("EUR", 0.85);
        exchangeRates.put("INR", 83.2);
        exchangeRates.put("GBP", 0.75);
        exchangeRates.put("JPY", 110.5);
        exchangeRates.put("AUD", 1.5);
        exchangeRates.put("CAD", 1.35);
    }

    public static double convertCurrency(String fromCurrency, String toCurrency, double amount) {
        if (!exchangeRates.containsKey(fromCurrency) || !exchangeRates.containsKey(toCurrency)) {
            throw new IllegalArgumentException("Currency code not supported.");
        }

        double amountInUSD = amount / exchangeRates.get(fromCurrency); // Convert from source to USD
        return amountInUSD * exchangeRates.get(toCurrency);            // Convert USD to target
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Available currencies: " + exchangeRates.keySet());
        System.out.print("Enter source currency code: ");
        String fromCurrency = scanner.nextLine().toUpperCase();

        System.out.print("Enter target currency code: ");
        String toCurrency = scanner.nextLine().toUpperCase();

        System.out.print("Enter amount to convert: ");
        double amount = scanner.nextDouble();

        try {
            double convertedAmount = convertCurrency(fromCurrency, toCurrency, amount);
            System.out.printf("%.2f %s = %.2f %s%n", amount, fromCurrency, convertedAmount, toCurrency);
        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }

        scanner.close();
    }
}
