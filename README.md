import java.util.Scanner;

public class VowelCounter {

    public static void main(String[] args) {
        String input = getUserInput();
        int[] vowelCounts = countVowels(input);
        displayResults(vowelCounts);
    }

    private static String getUserInput() {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter a string (max 20 characters):");
        String input = scanner.nextLine();
        scanner.close();

        if (input.length() > 20) {
            System.out.println("Input exceeds 20 characters. Truncating to 20 characters.");
            input = input.substring(0, 20);
        }
        return input;
    }

    
    private static int[] countVowels(String input) {
        int[] counts = new int[5]; 
        String lowerCaseInput = input.toLowerCase(); 

        for (char c : lowerCaseInput.toCharArray()) {
            switch (c) {
                case 'a': counts[0]++; break;
                case 'e': counts[1]++; break;
                case 'i': counts[2]++; break;
                case 'o': counts[3]++; break;
                case 'u': counts[4]++; break;
               
            }
        }
        return counts;
    }

   
   
    private static void displayResults(int[] vowelCounts) {
        System.out.println("Vowel counts:");
        System.out.println("A: " + vowelCounts[0]);
        System.out.println("E: " + vowelCounts[1]);
        System.out.println("I: " + vowelCounts[2]);
        System.out.println("O: " + vowelCounts[3]);
        System.out.println("U: " + vowelCounts[4]);
    }
}
