9
import java.util.Random;

public class Task9 {
    public static void main(String[] args) {
        // Створення масиву випадкових чисел
        int[] numbers = new int[20];
        Random random = new Random();
        int negativeCount = 0, positiveCount = 0, zeroCount = 0;
        int min = Integer.MAX_VALUE, max = Integer.MIN_VALUE;

        // Заповнення масиву випадковими числами від -10 до 10
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = random.nextInt(21) - 10; // Числа від -10 до 10
        }

        // Обробка масиву
        for (int num : numbers) {
            if (num < 0) negativeCount++;
            else if (num > 0) positiveCount++;
            else zeroCount++;

            // Оновлюємо мінімум і максимум
            if (num < min) min = num;
            if (num > max) max = num;
        }

        // Виведення результатів
        System.out.println("Мінімальне значення: " + min);
        System.out.println("Максимальне значення: " + max);
        System.out.println("Кількість від'ємних значень: " + negativeCount);
        System.out.println("Кількість додатних значень: " + positiveCount);
        System.out.println("Кількість нулів: " + zeroCount);
    }
}
10
import java.util.ArrayList;
import java.util.Random;

public class Task10 {
    public static void main(String[] args) {
        // Створення масиву випадкових чисел
        int[] numbers = new int[20];
        Random random = new Random();

        // Заповнення масиву випадковими числами від -10 до 10
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = random.nextInt(21) - 10; // Числа від -10 до 10
        }

        // Створення масивів для парних, непарних, від'ємних та додатних чисел
        ArrayList<Integer> evenNumbers = new ArrayList<>();
        ArrayList<Integer> oddNumbers = new ArrayList<>();
        ArrayList<Integer> negativeNumbers = new ArrayList<>();
        ArrayList<Integer> positiveNumbers = new ArrayList<>();

        // Перевірка кожного числа і додавання в відповідний масив
        for (int num : numbers) {
            if (num % 2 == 0) evenNumbers.add(num);
            else oddNumbers.add(num);

            if (num < 0) negativeNumbers.add(num);
            else if (num > 0) positiveNumbers.add(num);
        }

        // Виведення результатів
        System.out.println("Парні числа: " + evenNumbers);
        System.out.println("Непарні числа: " + oddNumbers);
        System.out.println("Від'ємні числа: " + negativeNumbers);
        System.out.println("Додатні числа: " + positiveNumbers);
    }
}
11
public class Task11 {
    public static void main(String[] args) {
        // Виклик методу для горизонтальної лінії
        drawLine(10, "horizontal", "*");

        // Виклик методу для вертикальної лінії
        drawLine(5, "vertical", "#");
    }

    // Метод для малювання лінії
    public static void drawLine(int length, String direction, String symbol) {
        if (direction.equals("horizontal")) {
            // Малюємо горизонтальну лінію
            for (int i = 0; i < length; i++) {
                System.out.print(symbol);
            }
            System.out.println(); // Перехід на новий рядок
        } else if (direction.equals("vertical")) {
            // Малюємо вертикальну лінію
            for (int i = 0; i < length; i++) {
                System.out.println(symbol);
            }
        } else {
            System.out.println("Невірний напрямок лінії.");
        }
    }
}
