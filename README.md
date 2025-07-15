# Student-Grade-Tracker
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        ArrayList<String> names = new ArrayList<>();
        ArrayList<Integer> marks = new ArrayList<>();

        System.out.print("How many students? ");
        int n = sc.nextInt();

        for (int i = 0; i < n; i++) {
            sc.nextLine(); // clear buffer
            System.out.print("Enter name of student " + (i+1) + ": ");
            String name = sc.nextLine();
            System.out.print("Enter marks of " + name + ": ");
            int mark = sc.nextInt();

            names.add(name);
            marks.add(mark);
        }

        int total = 0;
        int highest = marks.get(0);
        int lowest = marks.get(0);

        for (int m : marks) {
            total += m;
            if (m > highest) highest = m;
            if (m < lowest) lowest = m;
        }

        double average = (double) total / n;

        System.out.println("\n📊 Summary Report:");
        for (int i = 0; i < n; i++) {
            System.out.println(names.get(i) + " scored " + marks.get(i));
        }
        System.out.println("Total Marks: " + total);
        System.out.println("Average Marks: " + average);
        System.out.println("Highest Marks: " + highest);
        System.out.println("Lowest Marks: " + lowest);
    }
}
