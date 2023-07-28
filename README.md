import java.util.Random;
import java.util.Scanner;
public class LuckyNumber{
    public static void main(String[] args) {
        final int MAX= 100;
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int totalGames = 0;
        int totalGuess = 0;
        boolean continuePlaying = true;
        while (continuePlaying) {
            int luckyNumber = random.nextInt(MAX + 1);
            int guess;
            int count = 0;
            System.out.println("Bạn hãy đoán một số từ 0 đến " + MAX + ".");

            do {
                System.out.print("Nhập số đoán của bạn: ");
                guess = scanner.nextInt();
                count++;
                if (guess == luckyNumber) {
                    System.out.println("Chúc mừng bạn đã đoán đúng con số may mắn sau " + count + " lần dự đoán.");
                    totalGames++;
                    totalGuess += count;
                    break;
                } else if (guess < luckyNumber) {
                    System.out.println("Số may mắn lớn hơn số dự đoán của bạn.");
                } else {
                    System.out.println("Số may mắn nhỏ hơn số dự đoán của bạn.");
                }
            } while (true);
            System.out.print("Bạn có muốn tiếp tục chơi không?");
            String playAgain = scanner.next();
            if (playAgain.equalsIgnoreCase("No")||playAgain.equalsIgnoreCase("N")) {
                continuePlaying = false;
            }
        }
        System.out.println("Tổng số lần chơi: " + totalGames);
        System.out.println("Tổng số lần dự đoán: " + totalGuess);
        System.out.println("Số lần dự đoán trung bình mỗi lượt: " +(double) (totalGuess / totalGames));
        System.out.println("Best game (số lần dự đoán ít nhất trong các game): ");
    }
}
